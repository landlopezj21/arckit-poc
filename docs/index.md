# ArcKit

**El sistema de gobernanza de la arquitectura empresarial**

ArcKit es un framework de comandos asistidos por IA que genera documentos de gobernanza completos y listos para auditoría. Cubre desde el análisis de stakeholders y registros de riesgos hasta revisiones de diseño y matrices de trazabilidad. Sigue el marco de entrega ágil GDS del Gobierno del Reino Unido, con overlays jurisdiccionales contribuidos por la comunidad.

---

## ¿Qué problema resuelve?

Producir documentación de arquitectura de calidad enterprise — plans de negocio, evaluaciones de riesgo, diseños técnicos, registros de trazabilidad — es costoso y lento. ArcKit envuelve tu asistente de codificación AI en un harness basado en plantillas y listo para auditoría, reduciendo semanas de trabajo de consultoría a horas.

## Características principales

| Característica | Detalle |
|---|---|
| **Comandos AI** | 125 comandos cubriendo todo el ciclo de entrega GDS |
| **Jurisdicciones** | UK, EU, Francia, Austria, Canadá, UAE, Australia, USA |
| **Agentes autónomos** | 10 agentes para generación en paralelo |
| **Dependencias mapeadas** | 47 dependencias entre artefactos |
| **Licencia** | MIT |
| **Compatibilidad** | Claude Code, Gemini CLI, Codex CLI, OpenCode CLI, GitHub Copilot |

## Instalación rápida (Claude Code)

```bash
# Instalar el core (UK Government + genérico enterprise)
claude plugin install arckit

# Instalar con overlays jurisdiccionales
claude plugin install arckit arckit-uae arckit-eu arckit-fr
```

## Primeros pasos

Una vez instalado, abre tu proyecto con `claude` y ejecuta:

```
/arckit.start   # Muestra estado del proyecto y siguientes pasos recomendados
/arckit.init    # Crea la estructura de directorios projects/
```

Para generar una arquitectura completa en una sola sesión (Claude Code):

```
/arckit.build 001
```

Esto orquesta la generación en paralelo de ~31 artefactos en oleadas atómicas con commit por oleada.

---

> ⚠️ **Importante:** ArcKit genera primeros borradores siguiendo plantillas. Siempre revisa, valida y refina el output de IA con criterio y experiencia humana.

## Links de referencia

- [Sitio oficial](https://arckit.org)
- [Repositorio GitHub](https://github.com/tractorjuice/arc-kit)
- [Referencia de comandos](https://arckit.org/commands.html)
- [Comunidad Discord](https://discord.gg/JqgjQSnD)
