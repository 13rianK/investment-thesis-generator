# Investment Thesis Generator

A structured equity analysis skill for Claude that produces publication-ready investment thesis Word documents (.docx). Designed for buy-side analysts, portfolio managers, and serious individual investors who need rigorous, data-driven equity research — not generic company descriptions.

## What It Does

Given any publicly traded company, this skill produces an 11–14 page investment thesis document with:

- A **mispricing thesis** as the central organizing principle — "what does the market believe that is incorrect, and what is the catalyst for re-pricing?"
- **Confidence-weighted valuation** blending DCF, EV/EBITDA comps, and P/E comps (weighted by reliability, not equal-averaged)
- **Capital efficiency analysis** (ROIC, ROE, ROA) with component derivations, peer benchmarking, and vs. WACC indicators
- **Tactical technical analysis** framed for 3–6 month position managers with entry/exit/hedging signal tables
- **Full WACC derivation appendix** with sourced sub-components
- Numbered endnote sourcing throughout (15–25 sources per thesis)

The skill will recommend HOLD when no mispricing exists — it does not manufacture buy cases.

## Document Structure

| # | Section | Pages | Purpose |
|---|---------|-------|---------|
| 1 | Executive Summary & Mispricing Thesis | 1 | Recommendation, price target, what the market is getting wrong |
| 2 | Market Opportunity & Unit Economics | 1–2 | TAM/SAM/SOM sizing + unit-level revenue model validation |
| 3 | Business Overview & Competitive Moats | 1–2 | Revenue model, quantified moats, product roadmap |
| 4 | Competitive Landscape | 1 | Business-model-comparable peer table with ROIC column |
| 5 | Management & Governance | 0.5 | Execution track record, comp alignment, insider activity |
| 6 | Macroeconomic & Regulatory Context | 0.5–1 | Only factors with quantifiable earnings impact |
| 7 | Fundamental Valuation | 2–3 | Capital efficiency table, DCF, comps, scenario analysis |
| 8 | Technical Analysis & Trading Signals | 0.5–1 | Entry zone, stop-loss, take-profit, hedging triggers |
| 9 | Investment Risks & Mitigants | 1 | 5–7 MECE risks with specific, actionable mitigants |
| 10 | Exit Strategy & Hedging | 0.5 | Upside/downside triggers, specific hedge structures |
| 11 | Sources | 1 | Numbered endnotes referenced throughout |
| A | Appendix: WACC Derivation | 1 | Full component breakdown with sources and arithmetic |

## Project Structure

```
investment-thesis-generator/
├── README.md
├── skill/                          # Claude skill files
│   ├── SKILL.md                    # Main workflow and instructions
│   └── references/
│       ├── fundamental-analysis.md # DCF, comps, ROIC/ROE/ROA, scenario methodology
│       ├── technical-analysis.md   # Tactical trading signals framework
│       └── thesis-structure.md     # Section-by-section writing guide
├── builders/                       # Node.js document generators (docx-js)
│   ├── build_nvda_thesis.js        # NVIDIA — BUY thesis (GPU monopolist)
│   ├── build_msft_thesis.js        # Microsoft — BUY thesis (diversified megacap)
│   ├── build_cost_thesis.js        # Costco — HOLD thesis (great business, fair price)
│   └── build_sofi_thesis.js        # SoFi — BUY thesis (high-growth fintech)
└── examples/                       # Generated .docx output files
    ├── NVIDIA_Investment_Thesis_2026-03-09.docx
    ├── Microsoft_Investment_Thesis_2026-03-11.docx
    ├── Costco_Investment_Thesis_2026-03-11.docx
    └── SoFi_Investment_Thesis_2026-03-11.docx
```

## Key Design Decisions

**Mispricing-first architecture.** Every section connects back to the central thesis. If a paragraph could appear in the company's investor presentation, it doesn't belong in this document — the skill is trained to surface what *you* see that consensus is missing.

**Business-model comps, not sector comps.** Peer selection uses customer type, revenue model, margin profile, and growth stage — not GICS classification. A GPU monopolist selling to hyperscalers is not comparable to a diversified chip company selling to handset OEMs.

**Capital efficiency as a threshold gate.** The ROIC/ROE/ROA table appears *before* the DCF in Section 7 because it answers the threshold question: is this company creating value above its cost of capital? If ROIC < WACC, growth destroys value — the DCF needs to account for this directly.

**Metric selection framework:**
- **ROIC** (default): Strips out financing decisions; best for cross-company comparison
- **ROE**: Best for same-industry equity-funded comparisons (banks, insurers, REITs)
- **ROA**: Best for capital-intensive industries where the asset base IS the business

**Confidence-weighted valuation.** Methods are weighted by reliability for each specific company, not equal-averaged. The skill states the rationale for each weight assignment.

**Tactical technical analysis.** Framed for a 3–6 month position manager, not a long-term holder. Provides specific entry zones, stop-losses, take-profit levels, and hedging triggers — not vague trend commentary.

## Test Suite Results

| Company | Ticker | Recommendation | Words | Sections | Capital Efficiency | WACC Appendix |
|---------|--------|---------------|-------|----------|-------------------|---------------|
| NVIDIA | NVDA | BUY — $190 PT | 4,386 | 12/12 | ROIC 65.3% (55pp spread) | 10.2% |
| Microsoft | MSFT | BUY — $480 PT | 5,953 | 12/12 | ROIC 32.8% (23pp spread) | 9.5% |
| Costco | COST | HOLD — $960 PT | 4,942 | 12/12 | ROIC 22.1% (12pp spread) | 8.8% |
| SoFi | SOFI | BUY — $18 PT | 5,877 | 12/12 | ROE 8.2% (primary — bank) | 11.5% |

The test suite covers four distinct company profiles: pureplay semiconductor (NVDA), diversified megacap (MSFT), defensive consumer staple (COST), and high-growth fintech (SOFI). Costco demonstrates the skill correctly recommends HOLD when no mispricing is identified.

## Usage

### As a Claude Skill

Place the `skill/` directory in your Claude skills folder. The skill triggers on requests like:
- "Write an investment thesis on AAPL"
- "What do you think about MSFT as an investment?"
- "Deep dive on Tesla"
- "Bull/bear case for AMZN"

### Running Builder Scripts Directly

The builder scripts use [docx-js](https://www.npmjs.com/package/docx) to generate Word documents:

```bash
npm install -g docx
node builders/build_nvda_thesis.js
```

Each builder script contains company-specific research data and produces a formatted .docx file.

## Methodology References

The `skill/references/` directory contains three methodology guides:

- **fundamental-analysis.md** — DCF model construction (revenue projection, margin trajectory, terminal value, WACC), capital efficiency analysis (ROIC/ROE/ROA with component derivations and edge cases), comparable companies analysis, confidence-weighted valuation blending, and probability-weighted scenario analysis
- **technical-analysis.md** — Tactical signal framework for 3–6 month positions including trend identification, momentum indicators (RSI, MACD), volume analysis, support/resistance mapping, and hedge trigger definitions
- **thesis-structure.md** — Section-by-section writing guide with formatting standards, table templates, and quality rules for each of the 12 document sections

## Limitations

- Financial data is sourced via web search at generation time — accuracy depends on available sources
- Technical analysis levels reflect conditions at the time of generation and decay quickly
- The skill generates analysis and recommendations but is not financial advice
- Price targets are self-derived from first principles (DCF + comps), not scraped from analyst consensus

## License

MIT
