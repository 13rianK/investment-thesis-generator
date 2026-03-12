# Fundamental Analysis — Valuation Methodology

## Core Principle: Every Assumption Needs a Derivation

Never state an assumption without explaining WHY you chose that number. The reader
should be able to challenge any input and understand your reasoning.

---

## 1. DCF Model

### Revenue Projection (Justify the Growth Rate)
- State the growth rate AND its derivation:
  - "We model 25% revenue CAGR (FY27-31), decelerating from 65% in FY26. This reflects:
    (a) base effect — growing from $216B is harder than from $131B, (b) data center
    buildout shifting from greenfield to expansion phase by FY29, (c) unit economics
    showing ASP stability but volume growth moderating to 20% by FY30."
- Cross-check against TAM: If Year 5 revenue > SAM, your model is broken.
- Cross-check against unit economics: Revenue = units × ASP. Does your unit growth
  assumption make sense given customer expansion rates?

### Margin Projection (Justify the Trajectory)
- State the margin AND its driver:
  - "Gross margin recovers from 71% to 75% by FY28 because: (a) Blackwell yields
    improve from ~70% to ~90% over 4 quarters, reducing per-unit COGS, (b) software
    and networking mix increases from 8% to 12% of revenue (these carry 85%+ gross
    margin), (c) no pricing pressure assumed given competitive moat analysis in Section 3."
- If margins are declining, explain the structural reason.

### Terminal Value (Justify the Multiple or Growth Rate)

**Terminal growth rate justification:**
- Must be ≤ long-term nominal GDP growth (~4-5%)
- State why you chose your specific rate: "3% terminal growth reflects AI compute
  demand growing above GDP (structural) but decelerating from current hyper-growth
  (reversion to maturity)"
- Sensitivity to this assumption is large — show it in the matrix.

**Terminal EV/EBITDA justification (if using exit multiple):**
- Derive from: (a) current peer median, (b) target's own historical average,
  (c) justified premium/discount based on competitive position
- Example: "20x terminal EV/EBITDA reflects a 10% discount to the current peer
  median of 22x. We apply this discount because: (a) terminal-year margins assume
  steady state, reducing re-rating potential, (b) competitive dynamics may tighten
  as custom ASICs capture inference share. If we used the full peer median (22x),
  implied value would be $XXX (+XX%)."

### WACC Justification
- Risk-free rate: current 10-year Treasury (search for latest, cite source)
- Beta: state the source and methodology (2-year weekly vs. S&P 500)
- Equity risk premium: cite Damodaran or other source with the specific number
- If the company has material debt, show the debt cost derivation

### Enterprise Value → Equity Value Bridge
Show the full bridge with current numbers:
```
DCF Enterprise Value:  $X,XXX B
- Net Debt:            ($XX B)  [or + Net Cash: $XX B]
- Minority Interest:   ($X B)
= Equity Value:        $X,XXX B
÷ Diluted Shares:      XX.X B
= Implied Price:       $XXX
```

---

## 1B. Capital Efficiency Analysis (ROIC / ROE / ROA)

Capital efficiency metrics answer a question that DCF alone cannot: **is this company
creating economic value, or just growing revenue while destroying capital?** A company
with ROIC above WACC is creating value on every dollar invested; a company below WACC
is destroying value regardless of top-line growth.

### Which Metric to Use (Selection Framework)

| Metric | Formula | Best For | Limitations |
|---|---|---|---|
| **ROIC** | NOPAT ÷ Invested Capital | Cross-company comparison regardless of capital structure; long-term investing | Ignores leverage effects; requires invested capital estimation |
| **ROE** | Net Income ÷ Shareholders' Equity | Companies within the same industry that rely heavily on equity financing | Inflated by leverage; penalizes companies with excess cash |
| **ROA** | Net Income ÷ Total Assets | Capital-intensive industries (manufacturing, utilities, banks) | Ignores capital structure; distorted by off-balance-sheet items |

**Decision rule:**
- Default to **ROIC** for most equity theses — it strips out financing decisions and
  shows the pure operating return on capital deployed.
- Add **ROE** when comparing companies in the same industry with similar leverage
  (e.g., banks, insurers, REITs) or when the company is equity-funded with minimal debt.
- Add **ROA** for capital-intensive businesses where the asset base IS the business
  (utilities, manufacturing, airlines, banks) or when comparing across leverage levels.
- Always calculate **all three** and present them in the Capital Efficiency table, but
  weight your interpretation toward the most appropriate metric for that company.

### Component Derivations

**ROIC:**
```
NOPAT = Operating Income × (1 - Tax Rate)
Invested Capital = Total Equity + Total Debt - Cash & Equivalents - Non-operating Assets
  (alternatively: Net Fixed Assets + Net Working Capital + Other Operating Assets)
ROIC = NOPAT ÷ Average Invested Capital
```

**ROE:**
```
Net Income = Bottom-line earnings (after tax, interest, and non-controlling interests)
Shareholders' Equity = Total Assets - Total Liabilities (average of period start/end)
ROE = Net Income ÷ Average Shareholders' Equity
```

**ROA:**
```
Net Income = Bottom-line earnings
Total Assets = Average of period start/end total assets
ROA = Net Income ÷ Average Total Assets
```

### Required Output: Capital Efficiency Table

This table MUST appear in Section 7 (Fundamental Valuation) of the thesis document:

| Metric | FY(N-2) | FY(N-1) | FY(N) | FY(N+1)E | Peer Median | vs. WACC |
|---|---|---|---|---|---|---|
| ROIC | XX.X% | XX.X% | XX.X% | XX.X% | XX.X% | ▲ Above / ▼ Below / ≈ Near |
| ROE | XX.X% | XX.X% | XX.X% | XX.X% | XX.X% | ▲ / ▼ / ≈ |
| ROA | XX.X% | XX.X% | XX.X% | XX.X% | XX.X% | ▲ / ▼ / ≈ |
| WACC | — | — | XX.X% | — | — | — |

The "vs. WACC" column is the critical signal:
- **▲ Above WACC** = value creation (ROIC > WACC = positive economic spread)
- **▼ Below WACC** = value destruction (growth actually hurts shareholders)
- **≈ Near WACC** = neutral (company earns roughly its cost of capital)

### Interpretation Framework

After the table, provide a 2-3 paragraph interpretation:

1. **Trend analysis:** Is capital efficiency improving, stable, or deteriorating? A company
   with rising revenue but declining ROIC is becoming less capital-efficient — growth is
   getting more expensive. This is a red flag even if the stock is rallying.

2. **ROIC-WACC spread:** The spread between ROIC and WACC is the economic value creation
   per dollar of invested capital. A 25% ROIC with a 10% WACC means each $1 of capital
   creates $0.15 of economic value annually. This spread justifies a premium to book value
   and a higher valuation multiple. Quantify: "NVIDIA's ROIC of 65% against a 10.2% WACC
   produces a 55pp spread — among the widest in large-cap technology."

3. **Peer comparison:** Where does the target sit relative to peers on each metric? A
   company with higher ROIC than peers but a lower P/E multiple is potentially mispriced.
   A company with lower ROIC than peers but a higher multiple is potentially overvalued.
   This directly feeds the mispricing thesis.

### ROIC in the Comps Table

Add ROIC as a column in the Competitive Landscape comps table (Section 4). This immediately
shows which competitors are truly capital-efficient versus those buying growth at poor returns:

| Company | Why Comparable | Growth | Gross Margin | ROIC | Fwd P/E | EV/EBITDA |
|---|---|---|---|---|---|---|

### Edge Cases and Adjustments

- **Negative equity (buyback-heavy):** If shareholders' equity is negative due to
  aggressive buybacks (e.g., McDonald's, Starbucks), ROE becomes meaningless (negative
  denominator). Flag this and rely on ROIC instead.
- **Large cash balances:** For companies with excess cash (e.g., tech), adjust invested
  capital to exclude non-operating cash above a reasonable operating buffer (~3-6 months
  of revenue). Otherwise ROIC is diluted by idle cash.
- **Recently IPO'd / high-growth:** ROIC may appear low if the company is reinvesting
  aggressively — invested capital is high relative to current NOPAT because returns lag
  investment. In this case, track the trend and project forward ROIC once investments mature.
- **Financial companies (banks, insurers):** ROIC is less meaningful because debt IS the
  business. Use ROE and ROA as the primary metrics, benchmarking against regulatory
  minimums (e.g., Basel III CET1 thresholds).

---

## 2. Comparable Companies Analysis

### Peer Selection (Business Model, Not Sector)

**Selection criteria (in order of importance):**
1. Same customer type (who are they selling to?)
2. Similar revenue model (recurring vs. one-time, hardware vs. software)
3. Comparable margin profile (±15% gross margin)
4. Similar growth stage (hyper-growth vs. mature)
5. Overlapping end market

**Anti-patterns to avoid:**
- Don't comp a GPU monopolist against a diversified chip company
- Don't comp a 65% grower against a 5% grower without adjusting for growth
- Don't include more than 6 peers — dilution reduces signal

### Comps Table

| Company | Ticker | Why Comparable | Mkt Cap | Growth | Margin | Fwd P/E | EV/EBITDA | P/FCF |
|---|---|---|---|---|---|---|---|---|

The "Why Comparable" column is mandatory. It forces you to justify each peer's inclusion.

### Statistical Summary
Include: Median, Mean, Min, Max. Use median as the primary reference (less skewed by
outliers).

### Relative Valuation Assessment
- Where does the target trade vs. peer median?
- Is the premium/discount justified? (Higher growth, better margins, stronger moat?)
- How does the current multiple compare to the target's 3-year average?
- **Key question:** Is the current discount an opportunity or is it justified?

---

## 3. Confidence-Weighted Valuation Blend

Do NOT simply average your valuation methods. Assign confidence weights based on which
methods are most reliable for this specific company.

### Weight Assignment Framework

| Method | When to overweight | When to underweight |
|---|---|---|
| DCF | Stable FCF, predictable growth, mature company | High-growth (terminal value dominates), unprofitable |
| Comps (P/E) | Profitable, similar-growth peers available | Pre-profit, highly cyclical earnings |
| Comps (EV/EBITDA) | Capital structure differences matter, cross-border | Negative EBITDA, wildly different D&A profiles |
| Comps (EV/Rev) | Pre-profit or early-stage, high growth | Mature companies (ignores profitability) |

### Blended Valuation Table

| Method | Implied Value | Confidence | Weight | Contribution |
|---|---|---|---|---|
| DCF (Base Case) | $XXX | High/Med/Low | XX% | $XX |
| Comps (EV/EBITDA) | $XXX | High/Med/Low | XX% | $XX |
| Comps (Fwd P/E) | $XXX | High/Med/Low | XX% | $XX |
| **Blended Target** | | | **100%** | **$XXX** |

State the rationale: "We assign 45% weight to DCF because NVIDIA's FCF is highly
predictable and growing. We assign 35% to EV/EBITDA comps because the peer set
(while imperfect) provides a market-based anchor. We assign 20% to P/E comps with
lower confidence due to the growth differential between NVIDIA and peers."

---

## 4. Scenario Analysis

### Probability-Weighted Scenarios

| | Bull | Base | Bear |
|---|---|---|---|
| **Probability** | XX% | XX% | XX% |
| Revenue (Yr 1) | $XXX B | $XXX B | $XXX B |
| Gross Margin | XX% | XX% | XX% |
| EPS | $XX.XX | $XX.XX | $XX.XX |
| Target Multiple | XXx | XXx | XXx |
| **Price Target** | **$XXX** | **$XXX** | **$XXX** |
| **Return** | **+XX%** | **+XX%** | **-XX%** |
| **Catalyst** | [What goes right] | [Base expectation] | [What goes wrong] |

**Probability-weighted expected value:**
= (Bull × P_bull) + (Base × P_base) + (Bear × P_bear) = $XXX

**Reward-to-risk ratio:**
= (Bull upside × P_bull + Base upside × P_base) / (Bear downside × P_bear)

This ratio should be ≥ 2:1 for a BUY recommendation.

---

## 5. TAM Reconciliation Check

Before finalizing, verify:
- [ ] Year 5 projected revenue ≤ SAM (or explain why you expect SAM expansion)
- [ ] Revenue = Units × ASP, and both inputs are reasonable
- [ ] Implied market share at Year 5 is achievable (not >100% of SAM)
- [ ] Growth deceleration is built in (no company grows 40% forever)
- [ ] If terminal growth > 3%, justify why (most companies revert to GDP growth)
