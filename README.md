# JUNO
## A Trilemma Framework for GSE Reform Analytics

**David Bieri · Virginia Tech School of Public and International Affairs**  
**v1.0 · April 2026**

---

## Overview

JUNO is a browser-native policy analytics tool examining why comprehensive reform of Fannie Mae and Freddie Mac has proven structurally impossible despite seventeen years of federal conservatorship. The tool operationalizes a trilemma framework — no reform mechanism can simultaneously achieve **market discipline**, **systemic stability**, and **implementation simplicity** — and demonstrates through three agent-based simulations that this trilemma is not a static policy choice problem but a **temporal trap** where prioritizing one objective initiates processes that eventually eliminate access to all three.

No build step. No server. No dependencies beyond D3 and cdnjs-hosted libraries.

---

## Analytical Architecture

JUNO is organized as a **signal chain**: nine analytical tabs, each adding one layer to a shared understanding of GSE reform constraints. The chain runs from taxonomic description through empirical scoring, mechanism visualization, and simulation evidence, culminating in scenario projection and proposal evaluation.

```
Reform Options → Complexity → Mechanism Design → Pathways
      → Trilemma → Lock-In Clock → Coordination → Complementarities → Scenarios
```

### Tab 01 — REFORM OPTIONS
Fourteen reform options organized across five categories (Administrative, Sector-Specific, Legislative Moderate, Comprehensive Restructuring, Emergency/Extreme), scored on mechanism design criteria, regulatory complexity, and stakeholder consensus. Five stakeholder weight sliders (Progressive, Libertarian, Federal Reserve, Political Feasibility, Housing Advocacy) dynamically rerank options in real time.

### Tab 02 — COMPLEXITY
The regulatory complexity rubric and its inverse relationship with stakeholder consensus. A scatter plot of all 14 options with complexity score on the x-axis and consensus score on the y-axis surfaces the core empirical finding: administratively feasible options (scoring 20–30 on complexity) achieve higher consensus than legislatively superior but politically stalled alternatives (scoring 70–80). Per-option five-dimensional radar charts (regulatory authority, inter-agency coordination, Dodd-Frank impact, timeline, transition risk) available on hover.

### Tab 03 — MECHANISM DESIGN
The A–D grade matrix across four criteria: incentive compatibility, information revelation, participation constraints, and efficiency. Heat map layout making the central tension immediately visible — FMIC grades A across all dimensions but is unimplementable; the Hybrid Utility-Competition Model grades C+ but is the most robust implementable option.

### Tab 04 — PATHWAYS
Dynamic reform quality trajectories for all 14 options over a 20-year horizon, computed using logistic growth functions, regulatory capture models, and degradation effects. Three-source confidence bands: parameter uncertainty, model specification uncertainty, and scenario uncertainty. Category filter isolates Administrative, Legislative Moderate, or Comprehensive Restructuring options.

### Tab 05 — TRILEMMA
The trilemma triangle with all 14 options plotted at their computed positions across the three vertices. A temporal slider (2008–2025+) shows the four-phase evolution of the achievable zone: reform window open (2008–2013), lock-in acceleration (2014–2020), structural impossibility (2020–2025), all vertices lost (2025+). Amber compare overlay holds a second option for parallel analysis.

### Tab 06 — LOCK-IN CLOCK
Simulation 3: path dependence accumulation through four mechanisms — learning effects (power law), coordination/network externalities (exponential), adaptive expectations (linear with calibrated shock jumps), sunk costs (logarithmic). Two-panel layout: stacked area accumulation above, reform cost vs. political feasibility limit below. Three fixed historical policy shocks (2012 Third Amendment, 2019 Treasury Reform Plan, 2025 PSPA amendments) calibrated to empirical evidence. Critical threshold at year 12 (~2020) and current 7.3× feasibility ratio displayed as headline stat cards.

### Tab 07 — COORDINATION
Simulation 2: N-player coordination game with heterogeneous agency preferences. Interactive agency selector updates Nash equilibrium success probability in real time via P(success) ≈ p^N. Three agencies with negative benefit coefficients (HUD, SEC, CFPB) distinctly marked with rationale for rational opposition. Per-agency effort levels shown as bar chart alongside the exponential decay curve.

### Tab 08 — COMPLEMENTARITIES
Simulation 1: institutional complementarities network displayed from pre-computed outputs. Six-node network diagram with edge weights proportional to complementarity strength κ_ij. Isolated reform trajectory showing 28% equilibrium and 23% system fitness drop. Time-varying complementarity strengthening results (68% → 8% reform success across years 5–20). Pre-computed display only — full ODE model details in technical appendix.

### Tab 09 — SCENARIOS
Six historical counterfactual projections: Corker-Warner passes (2014), Johnson-Crapo passes (2015), Trump Recap & Release succeeds (2020), Biden acts (2022), New legislative window (2027), and a user-defined intervention. Each scenario reruns path dependence accumulation from the intervention date, showing avoided lock-in and trilemma vertex accessibility. AI-powered Proposal Analyzer (Anthropic API) evaluates new reform proposals against the full rubric.

---

## Data and Simulation Foundations

### Scoring Data
All mechanism design grades, regulatory complexity scores, and stakeholder consensus scores are computed outputs from the underlying analytical framework, not generated interactively. The five stakeholder weighting scenarios are applied to fixed underlying scores. Source: Bieri (2026), manuscript in preparation for *Socio-Economic Review*.

### Simulation 1 — Institutional Complementarities
Theoretical foundation: Hall & Soskice (2001) varieties of capitalism.  
Model: Fitness landscape ODE system over six complementary institutions.  
Implementation: Pre-computed Python outputs (Radau stiff ODE solver).  
Key finding: Isolated reform achieves 28% of target; system fitness drops 23%.

### Simulation 2 — Fragmented Authority Coordination Game
Theoretical foundation: Ostrom (1990) collective action; Tullock (1965) bureaucratic costs.  
Model: N-player coordination game with Nash equilibrium effort calculation.  
Implementation: Closed-form JS computation (`p^N` exponential scaling).  
Key finding: 2-agency coordination 85% success; 12-agency coordination 12% success.

### Simulation 3 — Path Dependence Accumulation
Theoretical foundation: Pierson (2000, 2004) increasing returns to political institutions.  
Model: Four accumulation mechanisms with closed-form functional specifications.  
Implementation: Closed-form JS computation; shock parameters fixed to empirical calibration.  
Key finding: Critical threshold at year 12 (~2020); current reform cost 7.3× feasibility limit.

---

## File Structure

```
juno/
├── index.html          # Landing page
├── juno.html           # Main analytical tool (9 tabs)
├── README.md           # This file
├── CHANGELOG.md        # Version history
└── data/
    └── sim1_outputs/   # Pre-computed Simulation 1 results (CSV)
```

---

## Theoretical References

Bieri, D. (2015). Financial stability and regulatory reform. *[Journal]*.  
Bieri, D. (2026). The GSE reform trilemma: A temporal trap. Manuscript in preparation, *Socio-Economic Review*.  
Crouch, C. (2011). *The Strange Non-Death of Neoliberalism*. Polity.  
Hall, P. A., & Soskice, D. (2001). *Varieties of Capitalism*. Oxford University Press.  
Ostrom, E. (1990). *Governing the Commons*. Cambridge University Press.  
Pierson, P. (2004). *Politics in Time*. Princeton University Press.  
Tinbergen, J. (1952). *On the Theory of Economic Policy*. North-Holland.

---

## Citation

```bibtex
@software{bieri2026juno,
  author      = {Bieri, David},
  title       = {{JUNO}: A Trilemma Framework for {GSE} Reform Analytics},
  year        = {2026},
  version     = {1.0},
  institution = {Virginia Tech School of Public and International Affairs},
  publisher   = {GitHub},
  url         = {https://github.com/davidbieri/juno},
  note        = {Trilemma framework, three agent-based simulations,
                 institutional complementarities, coordination game,
                 path dependence accumulation, temporal trap dynamics}
}
```

---

## License

MIT License · David Bieri · Virginia Tech SPIA  
For educational and research purposes only. Not financial or legal advice.

---

*david-bieri.com · circular-flows.org · august-loesch.org*
