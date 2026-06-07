---
tipo: concepto
tags: [llm, wiki, ecosistema, herramientas, open-source]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [fuente-llm-wiki-pattern]
---

# Ecosistema LLM Wiki

Proyectos que emergieron en la comunidad a partir del [[llm-wiki-pattern]] de [[andrej-karpathy]]. El gist original (abril 2026) generó 5,000+ forks y varios proyectos publicados en pocas semanas.

## Proyectos derivados

### Echel v0.2.0 — wiki para desarrollo de productos
**Autor:** alirezabbasi | **Repo:** https://github.com/alirezabbasi/echel

Extiende el patrón LLM Wiki al ciclo de vida de productos de software. Un domain expert define problema, solución, constraints, MVP y stack. Echel convierte eso en: requisitos, arquitectura, roadmap, work packets ejecutables, agent packets, review reports, readiness gates, y "compounding project intelligence". El producto no pierde memoria cuando el contexto del LLM se resetea.

**Relevancia para Eurekant:** potencialmente útil para gestión de proyectos de clientes.

---

### Bias-Aware Stateful Lint — extensión de lint para wikis grandes
**Autor:** brtrx | **Gist:** https://gist.github.com/brtrx/ba595fd01e344d797cb66d34d982ecad

Soluciona el "ingestion order bias": wikis con 50+ fuentes tienden a estar sesgadas hacia las fuentes ingresadas primero. La extensión:
- Corre lint en batches de 5 páginas (evita límites de contexto)
- Mantiene scratchpad persistente entre sesiones
- Usa orden aleatorio (no de ingesta) para detectar contradicciones cross-cutting

Se integra como adición al CLAUDE.md existente.

---

### Mnemosyne — el patrón como infraestructura
**Autor:** noirblue | **Spec:** https://github.com/noirblue/IsaacCLupus_mnemosyn_spec

Toma el patrón LLM Wiki y lo convierte en **infraestructura de ingeniería**:
- **Rust core** para el path crítico (schema, job queue, graph traversal, API)
- **Python satellites** para extracción de documentos y orquestación LLM
- Audit trail por claim (cada afirmación trazada a su fuente)
- Agent memory: `memory/inbox/` → `memory/committed/` con review, link, decay
- Dual-node deployment: Foundry (batch compile/audit) + Frontline (interactive serve)

Más ambicioso que los otros; apunta a ser una plataforma, no una herramienta personal.

---

### Life Daily OS — aplicación a diario personal
**Autor:** iddingszhz | **Repo:** https://github.com/iddingszhz/Life_Daliy_OS

Aplica el patrón a autoconocimiento y journaling. Innovaciones:
- **Separación protocolo/personalidad**: CLAUDE.md como protocolo de comportamiento (no prompts acumulados). El protocolo es portable entre clientes de IA; la personalidad se cambia con un archivo.
- **Arquitectura L0→L4**: L0 (registro) → L1 (revisión semanal) → L2 (patrones) → L3 (comparación cross-time) → L4 (evolución compounding). La mayoría de apps de diario se quedan en L0-L1.

---

### Synthadoc v0.6.0 — wiki con lifecycle y export
**Autor:** paulmchen / axoviq-ai | **Repo:** https://github.com/axoviq-ai/synthadoc

Agrega dos capas al patrón base:

**Five-State Page Lifecycle:** `draft → active → stale → contradicted → archived`
- Transiciones automáticas: lint limpio → active; hash mismatch → stale; fuente conflictiva → contradicted
- Audit log permanente de cada transición (quién, cuándo, por qué)

**Wiki Export (4 formatos):**
- `llms.txt` / `llms-full.txt` — spec llmstxt.org para downstream LLM workflows
- `graphml` — grafo de wikilinks con atributos (status, confidence, citation count) para Gephi/yEd
- `json` — incluye `claims[]` (párrafo → líneas exactas de fuente), `lifecycle_history[]`, `ingest_cost_usd`

También tiene plugin de Obsidian.

## Patrones emergentes del ecosistema

1. **El patrón es modular** — cada proyecto toma partes distintas y las profundiza.
2. **Lint y sesgo son problemas reales** a escala (50+ fuentes).
3. **El lifecycle de páginas** (stale, contradicted) es una extensión natural no contemplada en el gist original.
4. **La separación protocolo/personalidad** en CLAUDE.md es una idea valiosa para portabilidad.
5. **Aplicaciones no técnicas** (journaling, autoconocimiento) son tan válidas como las técnicas.

## Ver también

- [[llm-wiki-pattern]] — patrón base
- [[andrej-karpathy]] — autor del gist original
