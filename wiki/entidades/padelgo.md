---
tipo: entidad
tags: [proyecto, cliente, flutter, supabase, padel, mercadopago]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [memoria-exportada-2026-06-07, memoria-exportada-2-2026-06-07, fuente-clickup-workspace-2026-06-07]
---

# PadelGo

**Cliente de [[eurekant]].** Plataforma digital end-to-end para el ecosistema de pádel: app móvil (jugadores y profesores) + panel web admin (clubes y staff). Matchmaking, reserva de canchas, torneos, pagos, gamificación completa (ELO, XP, rankings, insignias). Cliente: **Samuel Han**. Modelo: freemium/premium + comisiones sobre reservas, torneos, campañas y ads.

## Stack

- Flutter + Supabase
- MercadoPago Marketplace (split 90/10)
- Emulator: Pixel 7a + API 34 + Play Store

## Estado

- Cerca de producción (~2 meses restantes al junio 2026)
- Release v1.1.0 generada el 29 mayo 2026
- **Madurez (ClickUp):** proyecto con más sprints del workspace — **19 sprints**; listas únicas Improvement Tracker y User Cases. Milestones: MVP target 15/Dic/25, "Software Completo" 15/Abr/26.
- **Docs:** doc maestro "Padel Go" (`8c90e0d-15794`) con Project Overview, SRS (v3.1.0) y **SRS Adenda** (fixture automático de torneos modalidad Americano, condicionado a contrato adicional).

## Decisiones clave

- **WhatsApp API:** Utility+Auth $0.04/msg, Marketing $0.10/msg
- Cliente Samuel preocupado por escalabilidad de costos de mensajería
- Workflow de publicación en stores definido
- Configuración de emulator Android para LATAM: Pixel 7a + API 34 + Play Store
- Release notes generadas con skill `/release-docs`

## Ver también

- [[eurekant]] — empresa desarrolladora
