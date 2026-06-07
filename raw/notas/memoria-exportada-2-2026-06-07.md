# Memoria de Claude — versión 2

**Fuente:** Memoria de Claude (copiada directamente por Franco)
**Fecha de ingesta:** 2026-06-07
**Nota:** archivo raw, inmutable. Complementa `memoria-exportada-2026-06-07.md`.

---

Contexto laboral
Franco es el CEO de Eurekant LLC, una consultora de desarrollo de software con base en Argentina que construye aplicaciones móviles y web a medida para clientes. También es CEO de Tasty Control, un producto SaaS. El stack tecnológico principal de Eurekant es Flutter + Supabase + OneSignal (notificaciones por email) + MercadoPago, y la empresa migró de FlutterFlow a Flutter puro + Cursor IDE a partir de marzo de 2026, con los proyectos existentes en FlutterFlow siendo migrados gradualmente.
Miembros clave del equipo incluyen a Joaquín Mendoza (Tech Lead), Agustín Alemán (Full Stack), Verónica Torres y Nerea Lepez (PMs), Rolando Cruz (base de datos) y Germán (QA).
El manejo de estado utiliza Riverpod, la navegación GoRouter y los modelos Freezed.

Contexto personal
Franco está basado en Argentina y se comunica en español argentino informal (voseo) en la mayoría de las conversaciones, aunque Eurekant opera principalmente en inglés. Tiene un background en Windows y migró a macOS.
Recibe ingresos en USD y gestiona activamente sus finanzas personales en el mercado argentino, incluyendo estrategias con plataformas cripto e instrumentos financieros locales.

En foco actualmente
Franco está resolviendo un problema en su setup multi-pantalla en macOS (MacBook Pro M4 con monitor HDMI + iPad vía Sidecar), donde el Dock aparece en la pantalla incorrecta debido a un bug conocido de Sidecar.
Recientemente generó documentación de release para Comunidad Cima v1.2.0 usando el skill /release-docs y produjo un SRS para el Eurekant Client Hub usando el skill /eurekant-srs-generator, con foco activo en workflows de documentación e integración con ClickUp.
También está investigando cargos de facturación en Firebase Cloud Functions en el proyecto Synergys, originados por una función v1 (ffPrivateApiCall) con minInstances: 1 que mantiene una instancia corriendo 24/7, y está trabajando en migrar la app a la función v2 y eliminar el deployment legacy.

Historial reciente
Franco ha estado fuertemente enfocado en tooling interno y desarrollo de skills.
El skill eurekant-preliminary-report tuvo múltiples iteraciones (versiones 2.0 a 5.x), con mejoras en:
- pricing
- estructura de incentivo Early Bird
- integración con ClickUp CRM (lista Opportunities ID: 901408852936)
- tono y posicionamiento premium
- generación de PDFs/Word vía eurekant-docx y eurekant-word-formatter

También desarrolló y refinó:
- eurekant-srs-generator (cumple IEEE 830 / ISO)
- release-docs
Ambos están en uso activo. El skill eurekant-company captura el contexto de la empresa.

Proyectos activos
Comunidad Cima: App de clínica odontológica (franquicia). Stack: Flutter + Supabase + Firebase push + OneSignal emails. Temas clave: seguridad de google-services.json, pipeline de notificaciones push, templates de email en voseo argentino, matriz de notificaciones por grupo familiar.
PadelGo: Integración MercadoPago marketplace (split 90/10), configuración de emulator Android para LATAM, workflow de publicación en stores, release notes.
Synergys: Plataforma de medicina laboral en GCP.

Estándares definidos
Git: Git Flow (main/develop/staging), Conventional Commits, referencias a tickets ClickUp en branches, GitHub Rulesets (5 reglas: protección de branches, tags, repos críticos).
ClickUp estados: OPEN → IN PROGRESS → CODE REVIEW → QA → CLOSED + BLOCKED/WAITING ON/REOPENED
Automatizaciones ClickUp: PR Linked → CODE REVIEW, PR Merged → QA

Automatizaciones
Integración Mercury → ClickUp operativa: mapeo de contrapartes, deduplicación por Transaction ID, mensaje resumen en canal de chat al finalizar.
Franco usa Mercury (3 cuentas). Workspace ClickUp: 9002039309.

Proyectos personales
Jarvis: OpenClaw + Claude API + Pipecat + Whisper + ElevenLabs. VPS Hetzner CX22. Investigado, no implementado.
Ripio Optimizer: App Flutter con SRS generado. Suscripciones en USDT (50% cashback), gastos en WARS (23% TNA + 0.5% cashback). SRS completo, sin desarrollo.

Workflow comercial completo:
Discovery call → Preliminary report → Creación de Opportunity en ClickUp → Generación Word/PDF → Entrega al cliente

Pricing Eurekant:
Baseline interno: ~$6,000/mes
Beta: Simple $7k/1mes, Intermediate $10k/1.5mes, Complex $13.5k/2mes
MVP: Simple $13.5k/2mes, Intermediate $20k/3mes, Complex $27k/4mes
Early Bird se activa con la entrega del SRS.

Decisiones técnicas clave:
- Migración a Flutter + Supabase (marzo 2026)
- Boilerplate + .cursorrules definidos
- Abstracción de NotificationService (para evitar lock-in con Firebase)

Infra y herramientas: ClickUp, GitBook (changelogs cliente), GitHub, Mercury, Stripe, 1Password.

Proceso de desarrollo: Descubrimiento → Diseño → Desarrollo → Revisión → Lanzamiento → Mantenimiento y Evolución.
Branding: Montserrat (docs formales), Debra PW Bold (display), paleta basada en azul.
