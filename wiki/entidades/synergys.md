---
tipo: entidad
tags: [proyecto, cliente, gcp, medicina-laboral, cloud-functions, saas]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07, fuente-clickup-workspace-2026-06-07]
---

# Synergys

**Cliente de [[eurekant]].** Plataforma web SaaS multiempresa/white-label para gestión de exámenes médicos ocupacionales e historia clínica de colaboradores (salud laboral / RRHH). Se revende a otras empresas (logo personalizable por empresa).

- **Clientes confirmados** (Client informations): Eugenio Bonelli, Diego Zabala, Mauricio Piccini. Patricio Fernández fue quien los contactó.
- **Relación:** "Synergys & Eurekant" desde junio 2025.

## Estado (ClickUp)

8 sprints (Sprint 1 = 14/7/25 … Sprint 8 = 31/1–2/2/26), discontinuos al final. Entregado y en uso; los clientes mandan feedback vía la app. Doc "Documento de Ajustes y Observaciones" (oct 2025, `8c90e0d-13414`): 13 observaciones post-revisión (logo por empresa, permisos RRHH, renombre de módulos). Fuera de scope: exportación de historia clínica, dashboard de frecuencia.

## Stack

- Google Cloud Platform (proyecto fuera del org principal de Eurekant)
- Cloud Functions (FlutterFlow backend)

## Problema identificado

Cloud Function v1 `ffPrivateApiCall` con `minInstances: 1` generando ~$1.03/mes en idle innecesariamente.

## Solución

1. Migrar a Cloud Functions v2 con `minInstances: 0`
2. Actualizar la app para usar `ffPrivateApiCallV2`
3. Eliminar la función v1

## Ver también

- [[eurekant]] — empresa desarrolladora
