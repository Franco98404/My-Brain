---
tipo: entidad
tags: [proyecto, cliente, transporte, srs, relevamiento]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [fuente-clickup-workspace-2026-06-07]
---

# Ikigai

**Proyecto de [[eurekant]].** Plataforma de gestión de transporte laboral / colectivo de personal (transporte de empleados de empresas). Multi-tenant con roles: Empresas, Transporte particular, SuperAdmin, más Conductores y Pasajeros.

> Cliente final no figura explícito en los docs leídos (se menciona "Danone" como ejemplo). *Inferido:* rubro de transporte corporativo de personal.

## Funcionalidad (de SRS y relevamiento)

Gestión de empresas (CUIT, dominio, departamentos/CECO, logo), carga masiva/individual de usuarios y choferes, rutas y paradas geolocalizadas (Google Maps), reservas de asiento (diaria/semanal/mensual, lista de espera), validación de abordaje por **QR**, **tracking en tiempo real** (ubicación, velocidad, modo de manejo), scoring de choferes, mensajería bidireccional, encuestas post-viaje, reportes PDF/Excel.

## Estado

Etapa temprana: **0 sprints**, solo Product Backlog y Bug Tracking. En fase de relevamiento/SRS (4 relevamientos oct 2025; SRS v0.1.0 → v1.0.0 Draft 17-Dic-25).

## Requisitos no funcionales (confirmados)

Respuesta <2s, uptime 99.5%, cumplimiento Ley de Protección de Datos Personales. Auth JWT, cifrado de contraseñas. Recuperación de contraseña vía WhatsApp para usuarios sin email. Decisiones técnicas abiertas documentadas (solución de mapas, validación de vehículos).

## Documentos

- "Ikigai" (doc maestro `8c90e0d-16014`): Apuntes/relevamiento, Dudas técnicas, SRS (4 versiones).

## Ver también

- [[eurekant]] · [[stack-tecnico-eurekant]]
