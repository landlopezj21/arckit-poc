# Agentes autónomos

ArcKit incluye 10 agentes autónomos diseñados para orquestar la generación de artefactos de manera paralela y coordinada. Están disponibles principalmente a través de Claude Code, que ofrece soporte nativo para despacho de subagentes.

---

## ¿Qué son los agentes ArcKit?

Los agentes autónomos de ArcKit son configuraciones de agente que encadenan múltiples comandos ArcKit en flujos de trabajo coordinados. En lugar de ejecutar comandos uno a uno, un agente puede:

- Despachar múltiples comandos en paralelo (oleadas)
- Gestionar el estado entre comandos mediante `state.json`
- Hacer commit atómico de cada oleada al repositorio Git
- Reanudar desde el punto de fallo sin repetir trabajo completado

---

## El Build Harness (`/arckit.build`)

El agente más completo. Orquesta la generación de una arquitectura completa siguiendo una receta YAML.

### Flujo de ejecución

```
/arckit.build 001 --plan   →  Muestra el plan de oleadas sin ejecutar
/arckit.build 001           →  Ejecuta todas las oleadas
/arckit.build 001 --resume  →  Reanuda desde el punto de fallo
```

### Estructura de una oleada

Cada oleada:
1. Lee los targets del archivo YAML de receta
2. Despacha subagentes en paralelo por target
3. Valida los artefactos generados (hook `validate-arc-filename`)
4. Confirma los cambios con un commit atómico

### Estado persistente

El estado se guarda en `projects/{P}/.arckit/state.json`:

```json
{
  "recipe": "uk-saas",
  "project": "001",
  "completed_waves": ["wave-01-research", "wave-02-discovery"],
  "current_wave": "wave-03-alpha",
  "targets_completed": ["ORG_RESEARCH", "STAKEHOLDERS", "RISK_REGISTER"]
}
```

---

## Recetas de agente disponibles

### `uk-saas` (por defecto)

38 artefactos para proyectos SaaS del Gobierno del Reino Unido (sector civil).

**Oleadas incluidas:**
- Wave 01: Research (ORG_RESEARCH, GOV_REUSE, tech research)
- Wave 02: Discovery (stakeholders, riesgos, SOBC)
- Wave 03: Alpha (requisitos, ADRs, Wardley, modelo de datos)
- Wave 04: Beta (HLD, diagramas C4, vendor eval, backlog)
- Wave 05: Compliance (Secure by Design, DPIA, TCoP, Service Standard)
- Wave 06: Live (trazabilidad, ops-readiness, project story)

### `uk-mod-sovereign`

38 artefactos para proyectos MOD / entornos air-gapped con JSP 936 y MOD Secure by Design.

### `uae-federal-ai`

48 artefactos para cumplimiento del UAE Cabinet Agentic AI Decree, incluyendo los 12 comandos UAE.

### `ca-federal-fitaa`

~40 artefactos para cumplimiento federal canadiense FITAA, con todos los comandos `ca-*`.

---

## Personalizar recetas

Para crear una receta personalizada:

```bash
# Copia una receta base a tu proyecto
cp .claude/plugins/arckit/recipes/uk-saas.yaml .arckit/recipes/mi-receta.yaml

# Edita según tus necesidades
# Las recetas de proyecto tienen prioridad sobre las del plugin
# Tus cambios sobreviven actualizaciones del plugin
```

### Estructura básica de una receta YAML

```yaml
name: mi-receta
description: Mi receta personalizada
version: "1.0"

waves:
  - id: wave-01-discovery
    parallel: true
    targets:
      - id: STAKEHOLDERS
        command: arckit.stakeholders
      - id: RISK_REGISTER
        command: arckit.risk

  - id: wave-02-alpha
    parallel: true
    depends_on: [wave-01-discovery]
    targets:
      - id: REQUIREMENTS
        command: arckit.requirements
      - id: ADR_001
        command: arckit.adr
```

---

## Excluir targets específicos

```bash
# Omitir investigación de Azure
/arckit.build 001 --exclude AZURE_RESEARCH

# Omitir múltiples targets
/arckit.build 001 --exclude AZURE_RESEARCH --exclude GCP_RESEARCH
```

---

## Nota sobre Codex CLI

El Build Harness (`/arckit.build`) **no está disponible en Codex CLI**. Depende del despacho paralelo de agentes y el sistema de hooks de Claude Code. No existe un equivalente `$arckit-build`.

Para Codex, Gemini CLI, OpenCode CLI y GitHub Copilot, usa el flujo "Vibe Start" de 3 prompts descrito en [Primeros pasos](getting-started.md).
