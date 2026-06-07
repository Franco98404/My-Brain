---
tipo: entidad
tags: [proyecto, interno, eurekant, claude, skills, ai]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07, memoria-exportada-2-2026-06-07]
---

# Tooling Interno — Eurekant

Suite de skills de Claude en producción, desarrolladas y mantenidas por [[eurekant]]. Empaquetadas como archivos `.skill` vía la herramienta `skill-creator`.

## Skills en producción

| Skill | Versión | Descripción |
|---|---|---|
| eurekant-preliminary-report | v5.2.0+ | Informe preliminar post-call de discovery (evolucionó de v2.0 a v5.x) |
| eurekant-srs-generator | — | Genera documentos SRS (cumple IEEE 830 / ISO) |
| eurekant-word-formatter | — | Formatea docs con branding Eurekant |
| eurekant-company | — | Fuente de verdad sobre Eurekant |
| eurekant-docx | — | Generación de Word con formato oficial |
| flutter-publish | v2.2.0 | Publicación de apps Flutter en stores |
| release-docs | — | Changelogs y release notes |
| llm-council | — | Consejo de LLMs para decisiones complejas |

## Historial de eurekant-preliminary-report

Skill más iterado. Evolucionó de v2.0 a v5.x con mejoras en:
- Pricing y estructura de Early Bird
- Integración con ClickUp CRM (lista Opportunities ID: `901408852936`)
- Tono y posicionamiento premium
- Generación de entregables Word/PDF vía `eurekant-docx` y `eurekant-word-formatter`

## Convención de versioning

Al editar un skill: siempre actualizar número de versión y fecha antes de empaquetar.

## Automatizaciones relacionadas

- [[automatizacion-mercury-clickup]] — sync financiero Mercury → ClickUp

## Ver también

- [[eurekant]] — empresa
- [[eurekant-client-hub]] — portal de clientes (proyecto interno)
