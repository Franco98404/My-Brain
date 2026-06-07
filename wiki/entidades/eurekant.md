---
tipo: entidad
tags: [empresa, software, latam, flutter, supabase, consultora]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07, memoria-exportada-2-2026-06-07, memoria-chatgpt-2026-06-07]
---

# Eurekant LLC

Consultora de desarrollo de software enfocada en LATAM. Construye aplicaciones móviles y web a medida. Fundada por [[franco-cruz]].

## Datos legales

- **Tipo:** LLC registrada en Nuevo México, EE.UU.
- **EIN:** 98-1845067
- **Dirección comercial:** Orlando, FL
- **Fecha de incorporación:** 10 de febrero de 2025

## Estructura legal

- **Franco Cruz** es el único miembro formal de Eurekant LLC. Sin empleados, oficinas ni clientes en EE.UU.
- El equipo trabaja en Argentina como contratistas/colaboradores.

## Equipo

| Nombre | Rol |
|---|---|
| Franco Cruz | CEO / Fundador |
| Joaquín Mendoza | Tech Lead |
| Agustín Alemán | Full Stack |
| Verónica Torres | PM / Supervisora |
| Nerea Lepez | PM |
| Rolando Cruz | Base de datos |
| Germán | QA |
| Matías | Comercial |

Roles definidos en la empresa: diseñadora UX/UI, frontend, backend, especialista en bases de datos, DevOps, Project Manager.

## Stack principal

Ver [[stack-tecnico-eurekant]] para detalle completo.

- **Mobile/Web:** Flutter (migración desde FlutterFlow a Flutter puro + Cursor IDE desde marzo 2026)
- **Backend:** Supabase
- **Notificaciones:** OneSignal (email), Firebase (push)
- **Pagos:** MercadoPago, Stripe
- **State management:** Riverpod | **Navegación:** GoRouter | **Modelos:** Freezed

## Workflow comercial

**Discovery call → Preliminary report → Opportunity en ClickUp → Generación Word/PDF → Entrega al cliente**

- Lista ClickUp CRM Opportunities: `901408852936`
- Skill que genera el informe: `eurekant-preliminary-report` (v5.x+)
- Entregables: PDF/Word vía `eurekant-docx` y `eurekant-word-formatter`

## Herramientas y operaciones

- **PM:** ClickUp (Power User verificado, Workspace ID 9002039309)
- **Control de versiones:** GitHub con Rulesets (5 reglas: protección de branches, tags, repos críticos)
- **Docs cliente:** GitBook (changelogs)
- **Finanzas:** Mercury (3 cuentas), Stripe
- **Seguridad:** 1Password

## Proceso de desarrollo

**Descubrimiento → Diseño → Desarrollo → Revisión → Lanzamiento → Mantenimiento y Evolución**

## Branding

- **Tipografía docs:** Montserrat
- **Tipografía display:** Debra PW Bold
- **Color principal:** #137DC5 (azul, headers)

## Pricing

| Tipo | Bajo | Medio | Alto |
|---|---|---|---|
| Beta | $7,000 | $10,000 | $13,500 |
| MVP | $13,500 | $20,000 | $27,000 |

- Baseline: ~$6,000/mes
- Early Bird: se activa al entregar SRS

## Proyectos activos (clientes)

- [[comunidad-cima]] — app clínica odontológica
- [[padelgo]] — plataforma de pádel
- [[synergys]] — plataforma medicina laboral

## Proyectos internos

- [[eurekant-client-hub]] — portal de clientes (en desarrollo)
- [[tooling-eurekant]] — suite de skills de Claude
- [[automatizacion-mercury-clickup]] — sincronización financiera

## Ver también

- [[franco-cruz]] — fundador y CEO
- [[stack-tecnico-eurekant]] — tecnologías detalladas
- [[preferencias-y-workflow]] — workflow de desarrollo
