---
tipo: fuente
tags: [llm, wiki, knowledge-base, obsidian, productividad, karpathy]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: []
---

# Fuente: LLM Wiki Pattern — Andrej Karpathy

**Archivo original:** `raw/articulos/llm-wiki-pattern-original.md`
**URL:** https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
**Autor:** Andrej Karpathy (@karpathy)
**Fecha de publicación:** 4 de abril de 2026
**Popularidad:** 5,000+ stars, 5,000+ forks — impacto masivo en la comunidad
**Fecha de ingesta:** 2026-06-07

---

## Resumen

Documento de Karpathy que describe un patrón para construir bases de conocimiento personales **persistentes y compuestas** usando LLMs. La idea central: en lugar de RAG (recuperar y responder desde cero cada vez), el LLM construye y mantiene una **wiki persistente** de archivos markdown interconectados. El conocimiento se compila una vez y se mantiene actualizado, no se re-deriva en cada query.

## Puntos clave

- **RAG vs Wiki persistente**: RAG re-descubre desde fuentes crudas. La wiki compila el conocimiento una vez y lo mantiene.
- **Tres capas**: fuentes crudas (inmutables) → wiki (mantenida por LLM) → schema (CLAUDE.md / AGENTS.md).
- **Tres operaciones**: ingesta, query, lint.
- **"Obsidian es el IDE; el LLM es el programador; la wiki es el codebase."** — cita directa de Karpathy.
- **Buenas respuestas a queries se archivan como páginas** en `wiki/exploraciones/`.
- **Por qué funciona**: el bookkeeping tedioso (cross-references, consistencia, contradicciones) es donde mueren los wikis humanos. Los LLMs lo hacen sin cansarse.
- **Inspiración**: Memex de Vannevar Bush (1945).
- **Intencionalidad abstracta**: el documento es un patrón, no una implementación. Cada usuario lo instancia con su LLM.

## Ecosistema derivado (comentarios del gist)

El gist generó un ecosistema rápido de proyectos que extienden el patrón:

- **Echel** — extiende el patrón a desarrollo de productos de software (requisitos, arquitectura, roadmap como wiki compounding)
- **Lint extension (brtrx)** — solución al "ingestion order bias" en wikis grandes (50+ fuentes)
- **Mnemosyne (noirblue)** — el patrón como infraestructura: Rust core, job queue, graph traversal, provenance por claim
- **Life Daily OS (iddingszhz)** — aplicación del patrón a diario personal y autoconocimiento, L0→L4
- **Synthadoc** — five-state page lifecycle, wiki export en 4 formatos, plugin Obsidian

Ver [[ecosistema-llm-wiki]] para análisis de estos proyectos.

## Páginas wiki creadas/actualizadas

- [[llm-wiki-pattern]] — concepto central
- [[andrej-karpathy]] — entidad: autor
- [[ecosistema-llm-wiki]] — proyectos derivados del gist
