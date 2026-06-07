---
tipo: concepto
tags: [flutter, supabase, stack, tecnologia, eurekant]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07, memoria-exportada-2-2026-06-07, fuente-clickup-workspace-2026-06-07]
---

# Stack Técnico — Eurekant

Stack de tecnologías estándar usado por [[eurekant]] en proyectos de clientes.

> Confirmado por la doc técnica de ClickUp ("Base de conocimiento técnico" `8c90e0d-10194`): el stack real combina **FlutterFlow + Flutter** + **Supabase (Postgres, RLS, CLI, migraciones versionadas en GitHub)** + **Firebase (envío de emails)** + **OneSignal**. Incluye guías de **ARCA/AFIP** (facturación electrónica) y Guía de Inicialización de Claude Code. Trackers internos por herramienta (FlutterFlow, Supabase, ClickUp) en el folder Internal Tools.

## Mobile / Web

- **Framework:** Flutter (Dart) — migración desde FlutterFlow a Flutter puro + Cursor IDE desde marzo 2026
- **State management:** Riverpod
- **Navegación:** GoRouter
- **Modelos / serialización:** Freezed

## Backend

- **BaaS:** Supabase (base de datos PostgreSQL, auth, storage, edge functions)
- **Cloud alternativo:** GCP (usado por cliente Synergys)

## Notificaciones

- **Push:** Firebase (FCM) — `google-services.json` seguro de commitear
- **Email:** OneSignal

## Pagos

- **Principal:** MercadoPago (marketplace con split, ej. 90/10 en PadelGo)
- **Internacional:** Stripe

## DevOps y control de versiones

- **Git workflow:** Git Flow (main / develop / staging)
- **Commits:** Conventional Commits con referencias ClickUp (`DEV-XXXX`)
- **Merge strategy:** Squash merge
- **Reglas de repo:** GitHub Rulesets (5 reglas: protección de branches, tags, repos críticos)
- **IDE:** Cursor (principal), VS Code
- **Boilerplate:** definido con `.cursorrules` para proyectos Flutter nuevos

## Patrones de arquitectura

- **NotificationService:** capa de abstracción sobre Firebase/OneSignal para evitar lock-in con proveedor de push
- Proyectos existentes en FlutterFlow siendo migrados gradualmente a Flutter puro (desde marzo 2026)

## Configuración VS Code / Cursor

- **Tema:** Tokyo Night
- **Fuente:** JetBrains Mono con ligaduras
- **Plugins:** Material Icon Theme, Indent Rainbow

## Testing / QA

- **Emulator Android objetivo LATAM:** Pixel 7a + API 34 + Play Store

## Herramientas operativas

- **PM:** ClickUp (Workspace ID 9002039309)
- **Docs:** GitBook
- **Finanzas:** Mercury (3 cuentas), Stripe
- **Seguridad:** 1Password

## Estados de tareas en ClickUp

`OPEN → IN PROGRESS → CODE REVIEW → QA → CLOSED`
Adicionales: `BLOCKED`, `WAITING ON`, `REOPENED`

## Automatizaciones de ClickUp

- **PR Linked** → tarea pasa a `CODE REVIEW`
- **PR Merged** → tarea pasa a `QA`

## Ver también

- [[eurekant]] — empresa
- [[preferencias-y-workflow]] — preferencias y proceso de Franco
