# Log

Registro cronológico append-only de todas las operaciones sobre la wiki.
Filtrar entradas: `grep "^## \[" log.md | tail -10`

---

## [2026-06-07] ingesta | Memoria de ChatGPT — intereses personales, proyectos nuevos

Fuente: `raw/notas/memoria-chatgpt-2026-06-07.md`
Info nueva incorporada:
- Franco: intereses personales (ejercicio, fútbol, canto, guitarra, baile, rutina/sueño), rol CEO > developer, residente fiscal en Argentina
- Eurekant: Franco es único miembro formal de la LLC; equipo son contratistas en Argentina
- Tasty Control: ahora sabemos que es SaaS para gestión de negocios gastronómicos
- Proyectos nuevos: [[app-beneficios-tarjetas]], [[proyecto-inmobiliario-anelo]], [[estructura-comercial-eurekant]]
- SRS: naming convention SRS_<empresa>_DD-MM-YY, estilo Globant/Accenture/Thoughtworks
Páginas actualizadas: [[franco-cruz]], [[eurekant]], [[tasty-control]]
Páginas creadas: [[app-beneficios-tarjetas]], [[proyecto-inmobiliario-anelo]], [[estructura-comercial-eurekant]]
Total wiki: ~24 páginas.

---

## [2026-06-07] ingesta | Memoria de Claude versión 2 — gaps y actualizaciones

Fuente: `raw/notas/memoria-exportada-2-2026-06-07.md`
Info nueva incorporada (no duplicada):
- Eurekant: workflow comercial completo, lista Opportunities ClickUp (901408852936), GitHub Rulesets (5 reglas), automatizaciones PR→CODE REVIEW y PR MERGED→QA, boilerplate + .cursorrules, abstracción NotificationService, GitBook para changelogs cliente
- Comunidad Cima: release v1.2.0, templates email en voseo argentino, matriz de notificaciones por grupo familiar
- PadelGo: workflow de publicación en stores
- Tooling: historial de eurekant-preliminary-report v2.0→v5.x, integración ClickUp CRM
- Franco: bug Dock/Sidecar macOS (en foco jun 2026)
Páginas actualizadas: [[eurekant]], [[stack-tecnico-eurekant]], [[comunidad-cima]], [[padelgo]], [[tooling-eurekant]], [[franco-cruz]]

---

## [2026-06-07] ingesta | Memoria exportada de Claude — Franco Cruz y Eurekant

Fuente: exportación de memorias almacenadas en Claude (conversaciones pasadas).
Guardada en: `raw/notas/memoria-exportada-2026-06-07.md`
Páginas creadas (14):
- Entidades: [[franco-cruz]], [[eurekant]], [[tasty-control]]
- Proyectos clientes: [[comunidad-cima]], [[padelgo]], [[synergys]]
- Proyectos internos: [[eurekant-client-hub]], [[tooling-eurekant]], [[automatizacion-mercury-clickup]]
- Proyectos personales: [[jarvis]], [[ripio-optimizer]]
- Conceptos: [[stack-tecnico-eurekant]], [[preferencias-y-workflow]]
Index, overview y log actualizados. 18 páginas totales en la wiki.

---

## [2026-06-07] ingesta | Actualización fuente LLM Wiki con autoría de Karpathy + ecosistema

Se obtuvo el gist original de Andrej Karpathy (https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).
Metadatos confirmados: autor Karpathy, publicado 4 abril 2026, 5,000+ stars y forks.
Páginas actualizadas: [[fuente-llm-wiki-pattern]], [[llm-wiki-pattern]].
Páginas creadas: [[andrej-karpathy]], [[ecosistema-llm-wiki]] (5 proyectos derivados del gist).
Index y overview actualizados.

---

## [2026-06-07] setup | Inicialización de la wiki

Se creó la estructura base de la wiki:
- `CLAUDE.md` — schema y manual operativo completo
- `index.md` — índice vacío (listo para recibir páginas)
- `log.md` — este archivo
- Carpetas: `raw/`, `wiki/` con todas sus subcarpetas
- Primera ingesta: el documento fundacional del patrón LLM Wiki (ver [[fuente-llm-wiki-pattern]])
- Páginas creadas: [[llm-wiki-pattern]], [[fuente-llm-wiki-pattern]], [[overview]]
