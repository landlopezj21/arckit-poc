# Comandos AI

ArcKit expone 125 comandos organizados por fase GDS, jurisdicción y categoría. Cada comando genera un artefacto completo basado en plantilla.

## Sintaxis por plataforma

| Plataforma | Sintaxis |
|---|---|
| Claude Code / OpenCode | `/arckit.comando` |
| Gemini CLI | `/arckit:comando` |
| Codex CLI | `$arckit-comando` |
| GitHub Copilot | `/arckit-comando` |

---

## Comandos de orientación y control

| Comando | Descripción |
|---|---|
| `arckit.start` | Estado del proyecto, herramientas conectadas, árbol de decisión y próximos pasos |
| `arckit.init` | Crea la estructura de directorios `projects/` |
| `arckit.navigator` | Navega por artefactos existentes y recomienda el siguiente comando |
| `arckit.health` | Diagnóstico del estado del proyecto; detecta artefactos faltantes o incompletos |
| `arckit.build` | Orquesta la generación completa en paralelo (solo Claude Code) |

---

## Fase Discovery

| Comando | Artefacto generado |
|---|---|
| `arckit.stakeholders` | Análisis y mapa de stakeholders |
| `arckit.risk` | Registro de riesgos |
| `arckit.sobc` | Strategic Outline Business Case (SOBC) |
| `arckit.value-chain` | Cadena de valor |

---

## Fase Alpha

| Comando | Artefacto generado |
|---|---|
| `arckit.requirements` | Catálogo de requisitos funcionales y no funcionales |
| `arckit.principles` | Principios de arquitectura |
| `arckit.wardley` | Mapa Wardley para decisiones build vs buy |
| `arckit.data-model` | Modelo de datos |
| `arckit.tech-options` | Informe de opciones tecnológicas |
| `arckit.adr` | Architecture Decision Records (ADRs) |

---

## Fase Beta

| Comando | Artefacto generado |
|---|---|
| `arckit.hld-review` | Revisión del High-Level Design |
| `arckit.diagram` | Diagramas de arquitectura C4 |
| `arckit.analyze` | Análisis de brechas (gap analysis) |
| `arckit.vendor-eval` | Evaluación de proveedores |
| `arckit.backlog` | Backlog de entrega |

---

## Fase Live / Operaciones

| Comando | Artefacto generado |
|---|---|
| `arckit.traceability` | Matriz de trazabilidad completa |
| `arckit.ops-readiness` | Evaluación de preparación operacional |
| `arckit.story` | Narrativa del proyecto para stakeholders |

---

## Comandos de gobernanza y cumplimiento (UK)

| Comando | Marco de referencia |
|---|---|
| `arckit.secure-by-design` | NCSC Secure by Design |
| `arckit.dpia` | Data Protection Impact Assessment (GDPR / UK GDPR) |
| `arckit.tcop` | Technology Code of Practice (TCoP) |
| `arckit.service-standard` | GDS Service Standard |

---

## Búsqueda de código gubernamental (UK)

| Comando | Descripción |
|---|---|
| `gov-code-search` | Búsqueda en lenguaje natural en 24.500+ repos del gobierno UK |
| `gov-reuse` | Evaluación sistemática de reusabilidad |
| `gov-landscape` | Mapa del paisaje de código gubernamental por dominio |

---

## Consultar la referencia completa

La referencia completa con filtros por jurisdicción, tier, estado y categoría está disponible en:
[arckit.org/commands.html](https://arckit.org/commands.html)
