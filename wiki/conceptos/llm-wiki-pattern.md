---
tipo: concepto
tags: [llm, wiki, knowledge-base, productividad, obsidian, memoria, karpathy]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [fuente-llm-wiki-pattern]
---

# LLM Wiki Pattern

Patrón de diseño propuesto por [[andrej-karpathy]] (abril 2026) para construir bases de conocimiento personales **persistentes y compuestas** usando LLMs como mantenedores automáticos de una wiki en markdown. El gist original acumuló 5,000+ stars en pocas semanas, generando un ecosistema de herramientas derivadas (ver [[ecosistema-llm-wiki]]).

## Idea central

La diferencia con RAG (el enfoque estándar):

| RAG tradicional | LLM Wiki |
|---|---|
| Re-descubre desde fuentes crudas en cada query | Compila el conocimiento una vez; lo mantiene actualizado |
| Sin acumulación entre sesiones | Cada fuente enriquece el grafo existente |
| LLM como buscador/respondedor | LLM como escritor/mantenedor |
| Conocimiento disperso | Conocimiento sintetizado y enlazado |

## Arquitectura (3 capas)

1. **Fuentes crudas** (`raw/`) — inmutables. El LLM solo lee.
2. **Wiki** (`wiki/`) — páginas markdown generadas y mantenidas por el LLM. Sumarios, entidades, conceptos, exploraciones.
3. **Schema** (`CLAUDE.md` / `AGENTS.md`) — instrucciones al LLM: estructura, convenciones, workflows. Co-evolucionado entre humano y LLM.

## Operaciones principales

- **Ingesta**: nueva fuente → LLM la lee, extrae info, actualiza 10-15 páginas de la wiki, actualiza index y log.
- **Query**: pregunta → LLM lee `index.md`, páginas relevantes, sintetiza con citas. Las buenas respuestas se archivan en `wiki/exploraciones/`.
- **Lint**: health check periódico → detectar páginas huérfanas, contradicciones, conceptos sin página, claims desactualizados.

## Por qué funciona

El bookkeeping (actualizar cross-references, mantener consistencia, detectar contradicciones) es lo que hace que los wikis mueran: los humanos se aburren de hacerlo. Los LLMs no se cansan, no olvidan actualizar un link, y pueden tocar 15 archivos en un solo paso.

> *"Obsidian es el IDE; el LLM es el programador; la wiki es el codebase."* — Andrej Karpathy

## Analogía histórica

Relacionado con el **Memex** de Vannevar Bush (1945): visión de un dispositivo de conocimiento personal con "trails" asociativos entre documentos. Bush nunca resolvió quién haría el mantenimiento. Los LLMs resuelven eso.

## Herramientas compatibles

- **Obsidian** — IDE para leer y navegar la wiki (graph view, wikilinks, Dataview, Marp)
- **Obsidian Web Clipper** — convierte artículos web a markdown
- **qmd** — motor de búsqueda local para wikis grandes (BM25 + vector, CLI + MCP)
- **Git** — versionado de la wiki
- **Marp** — slide decks desde markdown dentro de Obsidian
- **Dataview** — queries sobre frontmatter YAML

## Aplicaciones posibles

- Wiki personal (psicología, objetivos, salud, journaling)
- Research de un tema a lo largo del tiempo
- Acompañar la lectura de un libro (cf. Tolkien Gateway)
- Wiki de equipo/empresa (Slack, transcripciones, docs de proyecto)
- Análisis competitivo, due diligence, notas de curso

## Ver también

- [[fuente-llm-wiki-pattern]] — fuente original (gist de Karpathy)
- [[andrej-karpathy]] — autor
- [[ecosistema-llm-wiki]] — proyectos derivados del gist
- [[overview]] — estado actual del conocimiento acumulado
