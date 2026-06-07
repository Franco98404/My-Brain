---
tipo: entidad
tags: [proyecto, cliente, flutter, supabase, odontologia]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07, memoria-exportada-2-2026-06-07]
---

# Comunidad Cima

**Cliente de [[eurekant]].** App para clínica odontológica.

## Stack

- Flutter + Supabase
- Firebase (push notifications) — `google-services.json` seguro de commitear según Firebase
- OneSignal (emails)
- Package ID: `com.eurekant.comunidadcima`

## Estado

- **Fase 1:** completa — release v1.2.0 documentada con skill `/release-docs`
- **Fase 2:** SRS generado (call de descubrimiento: 18 mayo 2026; 28 requerimientos funcionales en 10 módulos)

## Decisiones clave

- Recomendada capa de abstracción de notificaciones push (para independencia de proveedor)
- Templates de email en voseo argentino
- Matriz de notificaciones por grupo familiar (caso de uso: clínica odontológica con familias)

## Ver también

- [[eurekant]] — empresa desarrolladora
