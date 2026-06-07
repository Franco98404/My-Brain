# CLAUDE.md — Wiki Personal de Franco Cruz

Este archivo es el schema y manual operativo de la wiki. Lo lee el LLM al inicio de cada sesión para entender cómo está estructurada la base de conocimiento y qué workflows seguir.

---

## Propósito

Esta wiki es un **cerebro externo persistente**: una base de conocimiento estructurada en markdown que el LLM construye y mantiene incrementalmente. Franco aporta las fuentes (conversaciones, artículos, ideas, transcripciones). El LLM hace todo el bookkeeping: resumir, enlazar, actualizar, detectar contradicciones.

La wiki vive en esta carpeta (vault de Obsidian). El LLM escribe; Franco lee y dirige.

---

## Estructura de carpetas

```
My Brain/
├── CLAUDE.md              ← este archivo (schema y manual)
├── index.md               ← índice de todas las páginas de la wiki
├── log.md                 ← registro cronológico append-only
│
├── raw/                   ← fuentes originales (inmutables, el LLM solo lee)
│   ├── conversaciones/    ← transcripciones o resúmenes de chats con el LLM
│   ├── articulos/         ← artículos, posts, PDFs convertidos a markdown
│   ├── notas/             ← notas sueltas de Franco
│   └── assets/            ← imágenes descargadas localmente
│
└── wiki/                  ← páginas generadas y mantenidas por el LLM
    ├── overview.md        ← síntesis de alto nivel del conocimiento acumulado
    ├── entidades/         ← páginas de personas, empresas, proyectos
    ├── conceptos/         ← páginas de ideas, frameworks, temas
    ├── fuentes/           ← resúmenes de cada fuente procesada
    └── exploraciones/     ← análisis, comparaciones, respuestas a preguntas complejas
```

---

## Convenciones

### Nombres de archivo
- Todo en minúsculas, sin tildes, espacios reemplazados por guiones.
- Ejemplos: `eurekant.md`, `llm-wiki-pattern.md`, `reunion-cliente-2026-06-07.md`

### Frontmatter YAML
Todas las páginas de `wiki/` deben tener frontmatter:

```yaml
---
tipo: entidad | concepto | fuente | exploracion | overview
tags: [tag1, tag2]
creado: YYYY-MM-DD
actualizado: YYYY-MM-DD
fuentes: [nombre-fuente-1, nombre-fuente-2]   # páginas en wiki/fuentes/
---
```

### Wikilinks
Usar `[[nombre-de-pagina]]` para enlazar páginas. Nunca URLs relativas. Esto activa el graph view de Obsidian.

### Tamaño de páginas
- Páginas focalizadas y cortas (< 500 palabras) son preferibles a páginas monolíticas.
- Si una sección crece demasiado, extraerla a su propia página y enlazarla.

### Idioma
- El contenido de la wiki puede estar en español o inglés según el idioma de la fuente.
- Los metadatos (frontmatter, nombres de archivo) siempre en español/inglés consistente con el resto del archivo.

---

## Archivos especiales

### `index.md`
Catálogo de todas las páginas de la wiki. El LLM lo actualiza en cada ingesta. Formato:

```markdown
## Entidades
- [[eurekant]] — empresa de software de Franco; servicios de desarrollo a medida
- [[franco-cruz]] — perfil personal, objetivos, psicología

## Conceptos
- [[llm-wiki-pattern]] — patrón para construir wikis personales con LLMs

## Fuentes
- [[fuente-llm-wiki-2026-06-07]] — artículo sobre el patrón LLM Wiki de Tobi

## Exploraciones
- [[comparacion-rag-vs-wiki]] — análisis de RAG tradicional vs wiki persistente
```

El LLM lee `index.md` primero al responder preguntas para saber qué páginas existen.

### `log.md`
Registro cronológico append-only. Formato de cada entrada:

```markdown
## [YYYY-MM-DD] tipo | descripción breve

Detalle de lo que se hizo: qué fuente se procesó, qué páginas se crearon/actualizaron, qué se descubrió.
```

Tipos posibles: `ingesta`, `query`, `lint`, `exploracion`, `setup`.

Filtrar con: `grep "^## \[" log.md | tail -10`

---

## Workflows

### 1. Ingesta de nueva fuente

Cuando Franco comparte una fuente (texto, conversación, archivo):

1. Leer la fuente completa.
2. Discutir brevemente los puntos clave con Franco si hay ambigüedad.
3. Guardar la fuente original en `raw/` (subcarpeta apropiada).
4. Crear una página de resumen en `wiki/fuentes/`.
5. Crear o actualizar páginas de entidades y conceptos referenciados.
6. Actualizar `wiki/overview.md` si la fuente cambia el panorama general.
7. Actualizar `index.md` con todas las páginas nuevas/modificadas.
8. Agregar entrada a `log.md`.

**Regla:** nunca modificar archivos en `raw/`. Son inmutables.

### 2. Query / pregunta

Cuando Franco hace una pregunta:

1. Leer `index.md` para identificar páginas relevantes.
2. Leer las páginas relevantes de `wiki/`.
3. Sintetizar respuesta con citas a páginas (`[[nombre]]`).
4. Si la respuesta es valiosa y no trivial, proponer guardarla como nueva página en `wiki/exploraciones/`.

### 3. Lint / health check

Cuando Franco pide revisar la wiki:

1. Buscar páginas sin inbound links (huérfanas).
2. Detectar contradicciones entre páginas.
3. Detectar conceptos mencionados frecuentemente sin página propia.
4. Detectar páginas desactualizadas respecto a fuentes más recientes.
5. Sugerir qué fuentes o temas buscar para fortalecer el conocimiento.
6. Reportar hallazgos y proponer correcciones.

---

## Contexto inicial: Franco Cruz

- CEO y fundador de Eurekant LLC, empresa de desarrollo de software a medida.
- Basado en Salta, Argentina. Recibe ingresos en USD.
- Usa Obsidian como IDE de la wiki, Claude (Cowork) como LLM principal.
- Idioma preferido: español para comunicarse, contenido de la wiki bilingüe según fuente.
- Esta wiki empieza el 2026-06-07.

Para información detallada leer: [[franco-cruz]], [[eurekant]], [[stack-tecnico-eurekant]].

---

## Preferencias de Franco — leer al inicio de cada sesión

### Comunicación
- Español argentino informal (voseo) en todas las conversaciones.
- Al redactar contenido para clientes: segunda persona en voseo ("vos"), no tercera persona.
- Ser conciso y directo. Evitar explicaciones innecesarias.

### Forma de trabajar con el LLM
- **Plan primero, ejecución después:** siempre presentar el plan completo y esperar aprobación antes de modificar archivos o ejecutar cambios.
- **Cambios mínimos:** solo modificar lo solicitado explícitamente. No agregar reglas, secciones o cambios no pedidos.
- **Pensamiento estratégico:** no ejecutar ciegamente — cuestionar cuando el enfoque pueda perjudicar a Eurekant o a Franco.
- **Inferencias:** nunca dar conclusiones seguras basadas solo en inferencias; aclarar qué es inferido vs. confirmado.
- **Documentación:** preferir fuentes oficiales sobre opiniones de comunidad.

### Formatos de salida
- Contenido relacionado a ClickUp: bloques de código en markdown, no artefactos (salvo indicación contraria).
- Contenido para WhatsApp: formato con asteriscos y guiones bajos, listo para copiar.
- Al editar skills: siempre actualizar número de versión y fecha antes de empaquetar.

### Stack y herramientas clave
- **Desarrollo:** Flutter + Supabase (stack principal), Riverpod, GoRouter, Freezed
- **PM:** ClickUp (Workspace ID 9002039309, User ID Franco: 61439463)
- **Git:** Git Flow, Conventional Commits con refs ClickUp (DEV-XXXX), squash merge
- **IDE:** Cursor + VS Code (Tokyo Night, JetBrains Mono)
- **Emulator Android:** Pixel 7a + API 34 + Play Store

---

## Git workflow

### Branches
No se usan branches. Todo va directo a `master`.

### Formato de commits

```
<tipo>(<scope opcional>): <descripción breve>
```

**Tipos:**
- `setup` — configuración de la wiki o del repo
- `ingesta` — nueva fuente procesada
- `update` — actualización de página existente
- `query` — exploración/respuesta guardada en `wiki/exploraciones/`
- `lint` — correcciones de estructura, links, limpieza

**Ejemplos:**
```
ingesta(eurekant): agrega fuente sobre modelo de negocio
update(franco-cruz): actualiza stack técnico
query: agrega exploración comparación RAG vs wiki
lint: corrige páginas huérfanas y actualiza index
setup: estructura inicial de la wiki
```

### Flujo al hacer un commit

Cuando Franco pide hacer un commit, el LLM debe:

1. **Mostrar el mensaje de commit propuesto** antes de ejecutar nada.
2. **Mostrar el resumen de cambios** con este formato:
   ```
   Archivos nuevos:     wiki/entidades/foo.md, wiki/fuentes/bar.md
   Archivos modificados: index.md, log.md
   Archivos eliminados: (ninguno)
   ```
3. **Esperar confirmación** de Franco.
4. Una vez confirmado: ejecutar `git add`, `git commit` y `git push` en secuencia.

**Regla:** nunca hacer commit sin mostrar primero el mensaje y el resumen de cambios.

---

## Notas para el LLM

- Al inicio de cada sesión, leer este archivo + `index.md` + las últimas 5 entradas de `log.md`.
- Nunca inventar información: si algo no está en la wiki ni en las fuentes, decirlo.
- Preferir páginas pequeñas y bien enlazadas sobre páginas grandes y monolíticas.
- Ser proactivo en detectar conexiones entre páginas existentes y nuevas fuentes.
- Antes de crear una página nueva, verificar en `index.md` que no exista ya algo equivalente.
