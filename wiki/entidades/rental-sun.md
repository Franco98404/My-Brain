---
tipo: entidad
tags: [proyecto, cliente, flutter, supabase, mvp, playa]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [fuente-clickup-workspace-2026-06-07]
---

# Rental Sun

**Cliente de [[eurekant]].** App móvil (iOS + Android) MVP para que bañistas/turistas de playa pidan servicios y equipamiento (sombrillas, reposeras, etc.). Nombre anterior del proyecto: **"Repo Ya"**.

- **Cliente:** Fernando Javier Goias (confirmado en "Client informations"). Otros contactos: Nicolás Cordo, Fede Guzmán, Roma.
- **Flujo:** pedido simple en la app que termina redirigiendo a **WhatsApp** para cerrar la venta. En el MVP hay un único proveedor (el dueño de la app).

## Stack (confirmado)

- **Frontend:** Flutter
- **Backend / DB / Infra:** Supabase (Postgres)
- **Integraciones:** ninguna en el MVP

DB diseñada multi-empresa/multi-sucursal desde la base (tablas COMPANIES, BRANCHES, USERS, PRODUCTS, ORDERS, ORDER_DETAILS), preparada para escalar más allá del proveedor único.

## Estado

MVP en desarrollo. 4 sprints (Sprint 1 = 27/8/25 … Sprint 4 = 14/11–28/11/25), milestone MVP target 28/Nov/25. Objetivo estratégico: validar demanda antes de expandir a más proveedores/ubicaciones.

## Documentos

- "RentalSun → Project Overview" (`8c90e0d-13394`)
- "RentalSun → Base de datos_v1" — script SQL del esquema Postgres.

## Ver también

- [[eurekant]] · [[stack-tecnico-eurekant]]
