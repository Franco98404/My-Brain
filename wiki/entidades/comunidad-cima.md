---
tipo: entidad
tags: [proyecto, cliente, flutter, supabase, odontologia]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07, memoria-exportada-2-2026-06-07, fuente-clickup-workspace-2026-06-07]
---

# Comunidad Cima

**Cliente de [[eurekant]].** App de gestión para una red de clínicas odontológicas. Clientes: **Osvaldo Fadel** y **Augusto Ceballos** (sucursales en Buenos Aires y Tucumán). El paciente saca turnos, ve/paga créditos y cuotas, gestiona grupo familiar y recibe notificaciones; hay panel web / back office. Integración con **Dentalink** (software dental externo) — fuente recurrente de problemas. Pagos por Mercado Pago.

## Stack

- Flutter + Supabase
- Firebase (push notifications) — `google-services.json` seguro de commitear según Firebase
- OneSignal (emails)
- Package ID: `com.eurekant.comunidadcima`

## Estado

- **Fase 1:** completa — release v1.2.0 documentada con skill `/release-docs`
- **Fase 2:** en Discovery. Próxima etapa = **CRM propio** (cotización integral ~USD 10.000) para reemplazar Dentalink. El módulo de financiamiento queda pendiente porque los endpoints de Dentalink no lo permiten. SRS generado (call 18 mayo 2026; 28 requerimientos en 10 módulos).
- **Madurez (ClickUp):** el proyecto más maduro/activo — 15 sprints, con lista "Decisions, Questions & Risks Log". Ya publicado en App Store y Play Store.

## Decisiones clave

- Recomendada capa de abstracción de notificaciones push (para independencia de proveedor)
- Templates de email en voseo argentino
- Matriz de notificaciones por grupo familiar (caso de uso: clínica odontológica con familias)

## Ver también

- [[eurekant]] — empresa desarrolladora
