# Primeros pasos

Instala ArcKit en 5 minutos y empieza a generar artefactos de gobernanza de arquitectura.

## Elegir plataforma AI

ArcKit es compatible con cinco plataformas. La experiencia más completa (agentes, hooks, MCP, validación de output) se obtiene con **Claude Code**.

| Plataforma | Nivel de soporte | Comando de instalación |
|---|---|---|
| Claude Code | Premier (completo) | `claude plugin install arckit` |
| Gemini CLI | Completo | `gemini extensions install tractorjuice/arckit-gemini` |
| Codex CLI | Core | `codex plugin marketplace add tractorjuice/arckit-codex` |
| OpenCode CLI | Core | `arckit init my-project --ai opencode` |
| GitHub Copilot | Core | `arckit init my-project --ai copilot` |

---

## Instalación con Claude Code

### 1. Instalar Claude Code

```bash
# macOS, Linux y WSL
curl -fsSL https://claude.ai/install.sh | bash

# Windows (PowerShell)
irm https://claude.ai/install.ps1 | iex

# Actualizar a la última versión
claude install latest
```

> ArcKit v4.14.0+ requiere Claude Code **v2.1.121 o superior**.

### 2. Instalar los plugins de ArcKit

```bash
# Core (UK Government + genérico enterprise)
claude plugin install arckit

# Con overlay de la UE
claude plugin install arckit arckit-eu

# Con todos los overlays
claude plugin install arckit arckit-uae arckit-fr arckit-ca arckit-eu arckit-at arckit-au arckit-us
```

Para una instalación ligera (evita los ~100 MB del monorepo completo):

```bash
# Sparse checkout — solo lo que necesitas
claude plugin marketplace add tractorjuice/arc-kit --sparse .claude-plugin arckit-claude
```

### 3. Abrir tu proyecto

```bash
cd mi-proyecto
claude
```

### 4. Orientarse

```
/arckit.start
```

Muestra el estado del proyecto, herramientas conectadas, árbol de decisión de comandos y próximos pasos recomendados.

### 5. Inicializar la estructura del proyecto

```
/arckit.init
```

Crea el directorio `projects/` con la estructura base para los artefactos de arquitectura.

---

## Caminos rápidos

### Vibe Start — los 3 prompts

El camino más rápido para un repo nuevo. Encadena comandos automáticamente mediante los metadatos `handoffs:` de cada comando:

```
/arckit.init Este es un proyecto para {descripción en una línea}.

/arckit.principles

Ahora crea todos los artefactos. Tómate tu tiempo. No te detengas hasta completarlos.
```

**Cuándo usarlo:** proyectos nuevos, demos, pruebas de concepto.  
**Cuándo NO usarlo:** trabajo con regulación estricta (Secure by Design, MOD, EU AI Act) donde cada artefacto requiere aprobación de revisor.

### The GDS Harness — `/arckit.build` (solo Claude Code)

Disponible desde v4.13.0. Un solo comando orquesta la generación completa de la arquitectura en oleadas paralelas atómicas:

```
# Ver el plan antes de ejecutar
/arckit.build 001 --plan

# Ejecutar la receta por defecto (uk-saas, 38 artefactos)
/arckit.build 001

# Recetas alternativas
/arckit.build 002 --recipe uk-mod-sovereign
/arckit.build 003 --recipe uae-federal-ai
/arckit.build 004 --recipe ca-federal-fitaa
```

**Recetas incluidas:**

| Receta | Artefactos | Descripción |
|---|---|---|
| `uk-saas` | 38 | UK Government SaaS civil |
| `uk-mod-sovereign` | 38 | MOD / air-gapped con JSP 936 |
| `uae-federal-ai` | 48 | UAE Cabinet Agentic AI Decree |
| `ca-federal-fitaa` | ~40 | Canada Federal FITAA compliance |

El estado persiste en `projects/{P}/.arckit/state.json`. Si una oleada falla, ejecuta `/arckit.build 001 --resume` para continuar desde donde se detuvo.

---

## Siguientes pasos

- [Referencia de comandos AI](commands.md)
- [Jurisdicciones cubiertas](jurisdictions.md)
- [Fases GDS](gds-phases.md)
