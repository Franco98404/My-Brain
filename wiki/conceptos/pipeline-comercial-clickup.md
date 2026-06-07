---
tipo: concepto
tags: [comercial, crm, srs, pipeline, clickup, eurekant]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [fuente-clickup-workspace-2026-06-07]
---

# Pipeline comercial en ClickUp

Cómo [[eurekant]] gestiona el embudo comercial en el space CRM (folder Eurekant, `90144309637`). Complementa a [[estructura-comercial-eurekant]] y [[modelo-comercial-scoping]].

## Flujo

**Lead → Scheduled Call (descubrimiento) → Interaction → Opportunity → SRS**

- **Leads** (`901408003332`) — prospectos. Estados: new, pending rebooking, awaiting reservation, no response, not interested, unqualified, reengage later.
- **Scheduled Calls** (`901409433116`) — naming "Descubrimiento - Eurekant & <Nombre>". El bot `franco.cruz@eurekant.com` se invita para grabar y alimentar la IA que redacta el SRS.
- **Interactions** (`901408130420`) — registros puntuales (reuniones, WhatsApp).
- **Opportunities** (`901408852936`) — oportunidades calificadas, nombradas por proyecto.
- **SRS Documents** (`901408223609`) — ver abajo.

> Asignación observada: la mayoría de leads/calls a **Matias Molina** (comercial/SDR); SRS a **Sergio Muguruza** (PM/Tech Lead, hoy baja).

## SRS aprobados (9 — proyectos/clientes a medida)

Cima Dental · Bagó · Synergys · MDL Producciones · P2P Playa · Genelec · Gestoría 360 · Inmobiliaria · Destino Traful. Todos en estado `approved`.

## Proceso SRS (regla clave)

El SRS se construye **iterativamente después de cada reunión**, no al final. Naming obligatorio `<Project> - Fase <##> - Discovery <##>`. Regla **"No review → No meeting"**: no se agenda la próxima call hasta que el cliente lea la versión actual. Al cierre el SRS debe estar 90-95% completo. Basado en IEEE 830-1998.

## Otros embudos

- **Schoolfy 365** (CRM): lista Colegios (instituciones, Salta). Ver [[schoolfy-365]].
- **Tasty Control** (CRM): lista de leads con etapas de venta activas. Ver [[tasty-control]].

## Ver también

- [[eurekant]] · [[eurekant-core]] · [[modelo-comercial-scoping]] · [[estructura-comercial-eurekant]]
