# Fases GDS

ArcKit sigue el marco de entrega ágil GDS (Government Digital Service) del Gobierno del Reino Unido. Los comandos están mapeados a cada fase del ciclo de vida.

```
Phase 0      Discovery      Alpha      Beta      Live
Planning   →            →          →         →
```

---

## Phase 0 — Planning

Define los principios de arquitectura y crea la estructura del proyecto.

```
/arckit.init       # Estructura de directorios projects/
/arckit.principles # Principios de arquitectura del proyecto
```

**Artefactos típicos:**
- Principios de arquitectura
- Estructura de proyecto inicializada

---

## Discovery

Identifica stakeholders, evalúa riesgos y construye el Strategic Outline Business Case.

```
/arckit.stakeholders  Analiza stakeholders para [descripción del proyecto]
/arckit.risk          Crea registro de riesgos
/arckit.sobc          Genera Strategic Outline Business Case
/arckit.value-chain   Mapea la cadena de valor
```

**Artefactos típicos:**
- Análisis y mapa de stakeholders
- Registro de riesgos (risk register)
- Strategic Outline Business Case (SOBC)
- Cadena de valor

---

## Alpha

Recoge requisitos, modela datos, investiga opciones tecnológicas y mapea estrategia.

```
/arckit.requirements  Define requisitos
/arckit.wardley       Crea Wardley Map para decisiones build vs buy
/arckit.data-model    Modela datos
/arckit.tech-options  Investiga opciones tecnológicas
/arckit.adr           Registra Architecture Decision Records
```

**Artefactos típicos:**
- Catálogo de requisitos
- Wardley Maps
- Modelo de datos
- Informe de opciones tecnológicas
- ADRs (Architecture Decision Records)

---

## Beta

Adquiere servicios, evalúa proveedores, revisa diseños y genera el backlog de entrega.

```
/arckit.hld-review    Revisa el High-Level Design
/arckit.diagram       Genera diagramas C4
/arckit.analyze       Gap analysis integral
/arckit.vendor-eval   Evaluación de proveedores
/arckit.backlog       Genera backlog de entrega
```

**Artefactos típicos:**
- Revisión del High-Level Design
- Diagramas de arquitectura C4 (contexto, contenedor, componente)
- Análisis de brechas
- Informe de evaluación de proveedores
- Backlog priorizado

---

## Live

Verifica trazabilidad, asegura la preparación operacional y narra la historia del proyecto.

```
/arckit.traceability   Verifica trazabilidad completa
/arckit.ops-readiness  Evalúa preparación operacional
/arckit.story          Genera narrativa del proyecto
/arckit.health         Diagnóstico del estado del proyecto
```

**Artefactos típicos:**
- Matriz de trazabilidad
- Informe de preparación operacional
- Narrativa del proyecto (project story)

---

## Comandos de cumplimiento transversales

Estos comandos aplican a múltiples fases y se ejecutan según necesidad:

| Comando | Fase recomendada | Marco |
|---|---|---|
| `arckit.secure-by-design` | Alpha / Beta | NCSC Secure by Design |
| `arckit.dpia` | Alpha / Beta | GDPR / UK GDPR |
| `arckit.tcop` | Discovery / Alpha | Technology Code of Practice |
| `arckit.service-standard` | Beta / Live | GDS Service Standard |

---

## El harness completo en una sesión

Con `/arckit.build` (Claude Code) puedes generar todos los artefactos de las fases en oleadas paralelas:

```
/arckit.build 001 --plan   # Ver el plan primero
/arckit.build 001           # Ejecutar (~31 artefactos, <30 min)
```

Cada oleada se confirma con un commit atómico en Git, haciendo el proceso trazable y revisable.
