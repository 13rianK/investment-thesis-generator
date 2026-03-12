# Technical Analysis — Tactical Trading Signals

## Framing: Position Management, Not Trend Commentary

This section is written for an investor managing a 3-6 month position. The goal is
specific, actionable signals for entry, exit, position sizing, and hedging — not a
narrative about whether the stock is in an uptrend.

---

## 1. Signal Table (Required Output)

Every technical analysis section must include this table:

| Signal | Level / Condition | Action | Rationale |
|---|---|---|---|
| Entry zone | $XXX-$XXX | Initiate position | [Why this level — MA, support, volume] |
| Add zone | $XXX-$XXX | Increase position size | [Support held, oversold bounce] |
| Stop-loss | $XXX | Exit full position | [Key support break, trend reversal] |
| Take-profit (partial) | $XXX | Trim 50% | [Approaching resistance, overbought] |
| Take-profit (full) | $XXX | Exit remaining | [Price target hit, extreme extension] |
| Hedge trigger | [Event/level] | Add downside protection | [Deteriorating momentum] |

**Rules for setting levels:**
- Entry zone: Align with a technical support level AND fundamental value (e.g.,
  near the bear-case valuation or a key MA)
- Stop-loss: Below a meaningful support level (not an arbitrary percentage).
  Must be specific to the stock's volatility — a 5% stop on a stock with 3% daily
  moves will get triggered by noise.
- Take-profit: Near a resistance level or at the fundamental price target
- Hedge trigger: Based on a technical deterioration that precedes larger drops
  (e.g., death cross, RSI divergence, volume spike on decline)

---

## 2. Trend and Momentum Assessment

### Current Position (Brief)
- Price relative to 50-day and 200-day MA (above/below, gap in %)
- 50-day vs. 200-day relationship (golden cross, death cross, convergence)
- Trend direction: up, down, or range-bound (based on 6-month price action)

### Momentum Indicators
**RSI(14):**
- State the number and interpret: "RSI at 42 — neutral, consistent with a corrective
  phase. No oversold bounce signal yet (would need <30), no overbought concern."
- Note divergences: If price makes new high but RSI makes lower high = bearish divergence
  (flag as a hedge trigger).

**MACD:**
- State the position: above/below signal line, above/below zero
- Interpret the histogram: expanding = strengthening momentum, contracting = fading
- Signal crossovers: "MACD crossed below signal line on [date], confirming bearish
  momentum. A bullish re-cross would be an entry signal."

### Volume
- Recent volume vs. 3-month average (above/below, by how much)
- Volume on recent significant moves: Was the last big down-day on heavy volume
  (institutional selling) or light volume (retail profit-taking)?
- Earnings-day volume and direction (positive or negative skew)

---

## 3. Support and Resistance Levels

Identify 3-5 levels with specific derivation:

| Level | Price | Type | Derivation |
|---|---|---|---|
| R2 (major) | $XXX | Resistance | [52-week high / prior failed breakout] |
| R1 (near-term) | $XXX | Resistance | [50-day MA / recent swing high] |
| Current | $XXX | — | — |
| S1 (near-term) | $XXX | Support | [200-day MA / recent swing low] |
| S2 (major) | $XXX | Support | [Prior breakout level / bear-case valuation] |

**Aligning with fundamentals:** Where possible, tie technical levels to valuation levels.
If the bear-case DCF implies $140 and there's strong technical support at $135-140,
that's a powerful confluence that strengthens the risk management framework.

---

## 4. Synthesis: Technicals vs. Fundamentals

Conclude with how the technical picture modifies the fundamental recommendation:

**Technicals confirm:** "Entry at current levels. Technical support aligns with
fundamental value floor. Risk/reward setup is favorable."

**Technicals say wait:** "Fundamental thesis is constructive, but momentum is bearish
and key support hasn't been tested yet. Wait for [specific signal] before entering."

**Technicals conflict:** "Fundamental valuation suggests upside, but stock is technically
broken below 200-day MA with expanding downward momentum. Either (a) wait for
technical stabilization, (b) enter with reduced position size and wider stop, or
(c) use options to define risk."

---

## 5. Hedging Recommendations

Based on the technical setup, recommend specific hedging approaches:

**Low-risk setup (technicals confirm):**
- No hedging needed; use stop-loss at S2 for risk management

**Medium-risk setup (mixed signals):**
- Consider a collar: sell covered calls at R2, buy puts at S2
- Or: enter with 50% position size, add on technical confirmation

**High-risk setup (technicals conflict):**
- Buy protective puts (3-month, 10-15% OTM) to cap downside
- Or: wait entirely for technical confirmation before entering
- Define the cost of the hedge and its impact on expected return

**Always state the cost:** "3-month 10% OTM puts cost approximately X% of the position,
reducing the expected return from XX% to XX% but capping maximum loss at X%."
