---
tipo: fuente
tags: [clickup, workspace, ingesta, handbook]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: []
---

# Fuente — Workspace de ClickUp de Eurekant (2026-06-07)

Ingesta de solo lectura del workspace de ClickUp de [[eurekant]] (ID `9002039309`). Se mapeó la estructura completa (espacios, folders, listas) y se leyeron los Documentos de ClickUp, empezando por el [[eurekant-handbook]]. **No se leyeron tareas individuales** (fuera de alcance). Procesada por 5 agentes lectores en paralelo.

## Estructura del workspace (6 espacios)

- **Development** — ~17 folders de proyecto (clientes + productos propios + internos).
- **CRM** — pipeline comercial de Eurekant, más leads de Schoolfy y Tasty.
- **Business Intel** — Growth, Competitors (81 entradas gastronómicas), Atención Comercial.
- **Human Resources** — Employees (19), Recruiting, Incidents, 1-on-1s.
- **Finance** — Transactions (ARS/USD, sync con Mercury).
- **Monitoring** — User Feedback (Bugs, Suggestions) e Internal (Errors, Logs, AI Negative Feedback).

## Documentos clave leídos

- [[eurekant-handbook]] (doc `8c90e0d-9514`) — hub central de procesos.
- Doc "Gestión de Proyectos & Liderazgo" (`8c90e0d-16834`, = "Eurekant Core").
- Doc "Procesos & Metodología" (`8c90e0d-14114`).
- Doc "Base de conocimiento técnico" (`8c90e0d-10194`, ~90 páginas).
- Doc "Aprendizaje" (`8c90e0d-22894`).
- "Client informations" (`8c90e0d-25054`) — directorio de clientes confirmado.

## Hallazgos que alimentaron la wiki

- Proyectos sin página creados: [[rental-sun]], [[ikigai]], [[schoolfy-365]], [[pikium]], [[eurekant-core]].
- Conceptos nuevos: [[eurekant-handbook]], [[pipeline-comercial-clickup]], [[equipo-eurekant]], [[finanzas-eurekant-clickup]].
- Clientes confirmados: Comunidad Cima (Osvaldo Fadel, Augusto Ceballos); Padel Go! (Samuel Han); Synergys (Eugenio Bonelli, Diego Zabala, Mauricio Piccini); Rental Sun (Fernando Goias).
- Stack real confirmado: FlutterFlow + Supabase (Postgres) + Firebase (emails), DB versionada en GitHub, facturación ARCA/AFIP.

## A aclarar con Franco (no confirmado por ClickUp)

1. **"Finance App"** (folder en Development) — no tiene doc propio; las búsquedas devolvieron material de Comunidad Cima. ¿Producto propio distinto o contenedor?
2. **"Portal Municipal"** (folder) — su doc describe módulos de reservas/membresías/pagos con DLocalGo (parece gimnasio/club), no un municipio. Aparte existe un discovery municipal real con Mariano Baquini (Innova IA GOV). Verificar si se reutilizó el folder.
3. **"Medify Plus"** (folder) — prácticamente vacío, solo una lista de competidores del rubro salud. ¿Producto en research/standby?

## Caveats de la ingesta

- El MCP de ClickUp tuvo timeouts intermitentes (reintentados).
- El doc "Base de conocimiento técnico" se listó pero no se leyó página por página.
- Nombre del cliente final de Ikigai no figura explícito en los docs leídos.

## Ver también

- [[eurekant]] · [[eurekant-handbook]] · [[pipeline-comercial-clickup]] · [[equipo-eurekant]]
