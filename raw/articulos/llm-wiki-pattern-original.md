# LLM Wiki (documento original)

**Fuente:** https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
**Autor:** Andrej Karpathy (@karpathy)
**Fecha de publicación:** 4 de abril de 2026
**Fecha de ingesta:** 2026-06-07
**Stars:** 5,000+ | **Forks:** 5,000+

---

A pattern for building personal knowledge bases using LLMs.

This is an idea file, it is designed to be copy pasted to your own LLM Agent (e.g. OpenAI Codex, Claude Code, OpenCode / Pi, or etc.). Its goal is to communicate the high level idea, but your agent will build out the specifics in collaboration with you.

## The core idea

Most people's experience with LLMs and documents looks like RAG: you upload a collection of files, the LLM retrieves relevant chunks at query time, and generates an answer. This works, but the LLM is rediscovering knowledge from scratch on every question. There's no accumulation. Ask a subtle question that requires synthesizing five documents, and the LLM has to find and piece together the relevant fragments every time. Nothing is built up. NotebookLM, ChatGPT file uploads, and most RAG systems work this way.

The idea here is different. Instead of just retrieving from raw documents at query time, the LLM **incrementally builds and maintains a persistent wiki** — a structured, interlinked collection of markdown files that sits between you and the raw sources. When you add a new source, the LLM doesn't just index it for later retrieval. It reads it, extracts the key information, and integrates it into the existing wiki — updating entity pages, revising topic summaries, noting where new data contradicts old claims, strengthening or challenging the evolving synthesis. The knowledge is compiled once and then *kept current*, not re-derived on every query.

This is the key difference: **the wiki is a persistent, compounding artifact.** The cross-references are already there. The contradictions have already been flagged. The synthesis already reflects everything you've read. The wiki keeps getting richer with every source you add and every question you ask.

You never (or rarely) write the wiki yourself — the LLM writes and maintains all of it. You're in charge of sourcing, exploration, and asking the right questions. The LLM does all the grunt work — the summarizing, cross-referencing, filing, and bookkeeping that makes a knowledge base actually useful over time. In practice, I have the LLM agent open on one side and Obsidian open on the other. The LLM makes edits based on our conversation, and I browse the results in real time — following links, checking the graph view, reading the updated pages. Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase.

This can apply to a lot of different contexts:

- **Personal**: tracking your own goals, health, psychology, self-improvement
- **Research**: going deep on a topic over weeks or months
- **Reading a book**: building a companion wiki chapter by chapter (cf. Tolkien Gateway)
- **Business/team**: internal wiki fed by Slack threads, meeting transcripts, project docs
- **Competitive analysis, due diligence, trip planning, course notes, hobby deep-dives**

## Architecture

Three layers:

**Raw sources** — immutable source documents (articles, papers, images, data files). The LLM reads but never modifies.

**The wiki** — LLM-generated markdown files. Summaries, entity pages, concept pages, comparisons, overview, synthesis. The LLM owns this entirely.

**The schema** — CLAUDE.md (for Claude) or AGENTS.md (for Codex). Tells the LLM how the wiki is structured, conventions, and workflows. Co-evolved by human + LLM over time.

## Operations

**Ingest.** Drop new source → LLM reads, discusses key takeaways, writes summary page, updates index, updates entity/concept pages, appends to log. A single source might touch 10-15 wiki pages. Prefer one source at a time with involvement.

**Query.** Ask questions → LLM reads index.md first, then relevant pages, synthesizes with citations. Good answers → file back into wiki/exploraciones/ as new pages.

**Lint.** Periodic health check → contradictions, stale claims, orphan pages, missing cross-references, data gaps.

## Indexing and logging

**index.md** — content-oriented catalog. LLM reads it first on every query. Works at ~100 sources / hundreds of pages without RAG infrastructure.

**log.md** — append-only chronological record. Prefix `## [YYYY-MM-DD] type | description` makes it grep-able.

## Optional: CLI tools

**qmd** (https://github.com/tobi/qmd) — local search engine for markdown: hybrid BM25/vector search + LLM re-ranking, all on-device. CLI + MCP server.

## Tips and tricks

- **Obsidian Web Clipper** — browser extension to convert web articles to markdown
- **Download images locally** — Obsidian Settings → Attachment folder → `raw/assets/`; bind hotkey to "Download attachments for current file"
- **Obsidian graph view** — see what's connected, what's hub, what's orphan
- **Marp** — markdown-based slide decks; Obsidian plugin available
- **Dataview** — Obsidian plugin for queries over frontmatter (tags, dates, source counts)
- **Git** — version history, branching, collaboration for free

## Why this works

The tedious part of maintaining a knowledge base is the bookkeeping. Humans abandon wikis because maintenance burden grows faster than value. LLMs don't get bored, don't forget to update a cross-reference, can touch 15 files in one pass.

> "The human's job is to curate sources, direct the analysis, ask good questions, and think about what it all means. The LLM's job is everything else."

Related in spirit to Vannevar Bush's Memex (1945). Bush couldn't solve who does the maintenance. The LLM handles that.

## Note

Intentionally abstract. The exact directory structure, schema conventions, page formats, tooling — all depend on your domain, preferences, and LLM of choice. Everything is optional and modular. Share this with your LLM agent and work together to instantiate a version that fits your needs.

---

## Comentarios notables de la comunidad (gist)

**alirezabbasi** (May 28, 2026): Lanzó **Echel v0.2.0** — plataforma que extiende el patrón LLM Wiki al desarrollo de productos de software. Un domain expert define problema/solución/constraints, y Echel lo convierte en requisitos, arquitectura, roadmap, y work packets compounding. https://github.com/alirezabbasi/echel

**brtrx** (May 28, 2026): Extensión de lint para wikis con 50+ fuentes. Combate el "ingestion order bias" (sesgo hacia fuentes ingresadas primero). Corre lint en batches de 5 con scratchpad persistente entre sesiones, orden aleatorio de fuentes para detectar contradicciones cross-cutting. https://gist.github.com/brtrx/ba595fd01e344d797cb66d34d982ecad

**noirblue** (May 28, 2026): Propuso **Mnemosyne** — extiende el patrón como infraestructura (Rust core + Python satellites), con schema, job queue, graph traversal, auditoría por claim, provenance, deployment topologies. https://github.com/noirblue/IsaacCLupus_mnemosyn_spec

**iddingszhz** (May 29, 2026): Aplicó el patrón a diario personal / autoconocimiento. CLAUDE.md como protocolo de comportamiento (no prompts). Arquitectura L0→L4 de profundización incremental. https://github.com/iddingszhz/Life_Daliy_OS

**paulmchen** (May 29, 2026): Lanzó **Synthadoc v0.6.0** — five-state page lifecycle (draft→active→stale→contradicted→archived), wiki export en 4 formatos (llms.txt, graphml, json con trazabilidad a líneas de fuente), plugin de Obsidian. https://github.com/axoviq-ai/synthadoc
