---
tipo: entidad
tags: [proyecto, cliente, gcp, medicina-laboral, cloud-functions]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07]
---

# Synergys

**Cliente de [[eurekant]].** Plataforma de medicina laboral en GCP.

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
