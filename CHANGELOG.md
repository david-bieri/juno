# JUNO — Changelog

## v1.0.1 · 23 November 2026

### Fixed
- Proposal Analyzer had failed since 15 Jun 2026: it called `claude-sonnet-4-20250514`, which Anthropic retired. Model is now `claude-sonnet-5-5`, set once in `CLAUDE_API`.
- Requests now send the required `anthropic-version` header.
- Works outside claude.ai: an API key field (with Forget) above the Analyze button; the key is kept in sessionStorage for the tab only.
- API errors now show their message (401, retired model, rate limit) instead of "No response received."

## v1.0 · April 2026

**Initial release.**

### Analytical Content
- 14 GSE reform options across five categories (Administrative, Sector-Specific, Legislative Moderate, Comprehensive Restructuring, Emergency/Extreme)
- Five stakeholder weighting scenarios with dynamic reranking
- 5-dimensional regulatory complexity rubric
- Mechanism design A–D grade matrix (four criteria)
- Dynamic pathways visualization with three-source confidence bands
- Trilemma triangle with four-phase temporal evolution (2008–2025+)
- Three agent-based simulations mapped to trilemma vertices

### Simulations
- Simulation 1 (Complementarities): Pre-computed ODE outputs; 28% isolated reform finding
- Simulation 2 (Coordination): Live JS computation; p^N exponential scaling
- Simulation 3 (Lock-in): Live JS computation; critical threshold year 12 finding

### Tool Features
- Nine analytical tabs in signal chain architecture
- Dark/light mode toggle
- Amber compare overlay on Trilemma tab
- Six historical counterfactual scenarios
- AI-powered Proposal Analyzer (Anthropic API with web search)
- APA / BibTeX / Chicago citation export
- No build step, no server, no external dependencies beyond D3

---

*Future versions will incorporate updated FHFA conservatorship data, expanded interview evidence, and comparative case material (Canada, Denmark, Germany) as manuscript development proceeds.*
