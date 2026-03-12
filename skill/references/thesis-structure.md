# Thesis Structure — Section Writing Guide (10-12 Page Format)

Every section must connect to the mispricing thesis. If a paragraph could appear in
the company's investor deck, delete it and write what YOU see that consensus is missing.

---

## 1. Executive Summary & Mispricing Thesis (1 page, max 400 words)

This page determines whether a PM reads the rest. Structure it as:

**Paragraph 1 (3 sentences):** What the company does → Recommendation + price target →
Core mispricing thesis (what the market believes, why it's wrong, the catalyst).

**Paragraph 2 (2-3 sentences):** Expected return, investment horizon, the 2-3 data
points that give you conviction.

**Paragraph 3 (2-3 sentences):** Top 2-3 risks and why the risk/reward is still
asymmetric (or why it isn't, if recommending Hold/Sell).

**Key metrics table** (right below the text):

| Metric | Value |
|---|---|
| Current Price | $XXX |
| Price Target | $XXX |
| Upside/Downside | +XX% |
| Recommendation | BUY / HOLD / SELL |
| Investment Horizon | X months |
| Valuation (Fwd P/E) | XXx |

**Rules:**
- First sentence after company description = the recommendation. No hedging.
- The mispricing must be specific: "The market is pricing in 15% data center growth
  deceleration, but our unit economics analysis shows 25% is achievable because [X]"
- If you can't identify a mispricing, recommend HOLD and explain why.

---

## 2. Market Opportunity & Unit Economics (1-2 pages)

This section does two things: (1) sizes the opportunity, (2) proves the revenue
model works at the unit level.

**Market sizing (half page):**
- TAM → SAM → SOM with sources and math shown
- Growth rate with driver decomposition
- Use a table for the funnel — prose for interpretation only

**Unit economics (half to one page):**
- Revenue per customer/unit, ASPs, attach rates, retention/churn
- Gross margin per unit and contribution margin
- How unit economics evolve at scale (improving? deteriorating?)
- **Critical reconciliation:** Your revenue projection (from Section 7) must be
  achievable given these unit economics. If TAM is $100B and you're modeling $120B
  in revenue, that's a conflict. If unit economics imply a $200B ceiling and you're
  modeling $300B, that's a conflict. Flag and resolve explicitly.

**This section answers:** Is the market big enough and is the revenue model durable
enough to support the growth embedded in the valuation?

---

## 3. Business Overview & Competitive Moats (1-2 pages)

Lead with how money is made, not company history.

**Revenue model (table + brief commentary):**

| Segment | Revenue | % Total | Growth | Margin | Trend |
|---|---|---|---|---|---|
| Segment A | $XB | XX% | XX% | XX% | Accelerating/Stable/Decelerating |

**Competitive moats (quantified):**
- Each moat claim needs a number or measurable evidence
- "High switching costs" → "12-18 month migration + $2-5M transition cost, evidenced
  by 95%+ gross retention"
- "Network effects" → "4M+ developers on CUDA; each new developer improves library
  coverage, attracting more users (measured by [metric])"
- "Scale advantage" → "R&D spend of $12B/yr enables annual architecture cadence;
  nearest competitor spends $4B"

**Product roadmap** (brief — 2-3 sentences on what's coming and how it extends moats).

**This section answers:** Why can't competitors replicate this business?

---

## 4. Competitive Landscape (1 page)

Use a structured comparison table as the core of this section.

**Comps selection rule:** Choose 4-6 companies that share the target's actual business
model — same customer type, similar revenue model, comparable margin profile, similar
growth stage. Do NOT default to sector/industry classifications.

Example: For an AI GPU monopolist selling to hyperscalers, comparable companies might
be other hyperscaler infrastructure suppliers (not diversified chip companies selling
to handset OEMs).

**Comparison table (ROIC column required):**

| Company | Revenue | Growth | Margin | ROIC | Market Share | Competitive Position |
|---|---|---|---|---|---|---|

**Key insight to surface:** Is the competitive window opening or closing? Are rivals
innovating or stagnating? This directly informs the mispricing thesis.

Keep prose to 3-4 paragraphs interpreting the table. No biographical competitor
descriptions.

---

## 5. Management & Governance (0.5 page)

**Execution track record** over biography. Format as a small table:

| Executive | Tenure | Key Achievement | Concern |
|---|---|---|---|

Plus 2-3 paragraphs covering:
- Have they delivered on prior guidance? (Track record of beats/misses)
- Compensation alignment (stock-based comp, performance metrics)
- Insider transactions (buying or selling?)
- Board quality and any activist pressure

Flag trust deficits explicitly. Skip this section's length if there's nothing notable.

---

## 6. Macroeconomic & Regulatory Context (0.5-1 page)

**Only include factors with quantifiable impact on this company's earnings or multiple.**
If interest rates don't materially affect the thesis, don't write about interest rates.

For each factor included:
- State the factor
- Quantify the impact: "A 25% tariff on China exports reduces revenue by ~$X or X%"
- State the current trajectory: getting better, worse, or stable
- Connect to the mispricing: is the market over/under-pricing this risk?

If fewer than 3 material macro factors exist, this section should be half a page.

---

## 7. Fundamental Valuation (2-3 pages)

See `references/fundamental-analysis.md` for full methodology. This section must include:

1. **Capital efficiency table** (ROIC, ROE, ROA — see Section 1B of fundamental-analysis.md)
2. **DCF summary table** with every assumption justified
3. **DCF sensitivity matrix** (WACC vs. terminal growth)
4. **Comparable companies table** using business-model peers
5. **Confidence-weighted valuation blend** with stated rationale for weights
6. **Bull/Base/Bear scenario table** with probability weights and catalysts
7. **Price target derivation** showing the math

The capital efficiency table appears FIRST in this section because it answers the
threshold question: is this company creating value above its cost of capital? If ROIC
is below WACC, the company is destroying value and no amount of revenue growth fixes
that — the DCF model needs to account for this directly.

**TAM reconciliation check:** If your Year 5 revenue projection exceeds SAM, or if
unit economics can't support the projection, revise your model or flag the conflict.

---

## 8. Technical Analysis & Trading Signals (0.5-1 page)

See `references/technical-analysis.md`. Frame for a **tactical 3-6 month position
manager**, not a long-term holder.

**Required table:**

| Signal | Level | Action |
|---|---|---|
| Entry zone | $XXX-$XXX | Initiate position |
| Add zone | $XXX-$XXX | Increase position (support held) |
| Stop-loss | $XXX | Exit full position |
| Take-profit | $XXX | Trim 50% |
| Hedging trigger | [Technical event] | Add puts / collar |

Plus 2-3 paragraphs on current momentum, volume, and how technicals align with
or diverge from the fundamental thesis.

---

## 9. Investment Risks & Mitigants (1 page)

**Risk table (required):**

| Risk | Category | Severity | Probability | Mitigant |
|---|---|---|---|---|

**Rules:**
- 5-7 risks, MECE categorization
- Every mitigant is specific and actionable — "management is monitoring" is not a mitigant
- Include one "thesis-breaking" risk with the early warning signal
- Quantify impact where possible: "If hyperscaler capex falls 30%, our revenue estimate
  drops X%, implying a stock price of $Y"

---

## 10. Exit Strategy & Hedging (0.5 page)

- Investment horizon
- Upside exit: price target, valuation stretched, better opportunity
- Downside exit: thesis broken, stop-loss hit, fundamental deterioration
- Hedging: specific approaches (e.g., "Buy 3-month 15% OTM puts at $X to cap
  downside at -10%")
- Monitoring checklist: 3-5 specific metrics/events to watch

---

## 11. Sources (second-to-last page)

Numbered endnote list. Format:

[1] Source description, URL or publication, date accessed
[2] ...

All quantitative claims in the document must reference a source. Aim for 15-25 sources
for a thorough thesis.

---

## Appendix A: WACC Derivation (final page)

This appendix provides full transparency on the discount rate used in the DCF. It
must include every sub-component with its source, so a reader can replicate or challenge
any input.

**Required table:**

| Component | Value | Source |
|---|---|---|
| Risk-Free Rate (10Y UST) | X.XX% | U.S. Treasury Daily Yield Curve, [date] |
| Equity Risk Premium | X.X% | Damodaran, [month year] update / other source |
| Beta (levered) | X.XX | [Source], [methodology: 2yr weekly vs. S&P 500] |
| Cost of Equity (Re) | X.XX% | Rf + β × ERP = [math shown] |
| Pre-Tax Cost of Debt (Rd) | X.XX% | Weighted average of outstanding debt / credit spread + Rf |
| Tax Rate (Marginal) | XX.X% | 10-K effective tax rate / statutory rate |
| After-Tax Cost of Debt | X.XX% | Rd × (1 - Tax Rate) |
| Equity Weight (E/V) | XX.X% | Market cap ÷ (Market cap + Total debt) |
| Debt Weight (D/V) | XX.X% | Total debt ÷ (Market cap + Total debt) |
| **WACC** | **X.XX%** | **(E/V × Re) + (D/V × Rd × (1-T))** |

**Rules:**
- Show the arithmetic: "4.25% + (1.18 × 5.0%) = 10.15%"
- If the company has no debt (or negligible debt), state: "Negligible debt; WACC ≈ Cost
  of Equity" and simplify accordingly
- If you use an alternative beta source or adjustment (e.g., Blume adjustment, sector
  unlevered beta), explain why
- Reference the specific date for each market input — rates change daily

---

## Formatting Standards

- **Font:** Arial throughout, 10-11pt body text
- **Tables:** Use for ALL financial data. No financial numbers in prose paragraphs.
- **Color scheme:** Dark navy headers (#1B365D), medium blue sub-headers (#2E5090),
  dark gray body text (#333333)
- **Cover page:** Company name, ticker, price, recommendation, price target, date
- **Headers/footers:** Company name + "Investment Thesis" in header; page numbers in footer
- **Endnotes:** Superscript-style [1] references inline, full list in Sources section
