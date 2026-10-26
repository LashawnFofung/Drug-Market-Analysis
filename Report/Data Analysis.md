# Drug Market Analysis Report
### Decision tree analysis for Major Pharmaceutical Company (MPC)

**Prepared by:** Lashawn Fofung · **Course:** Data-Driven Decision Making (MBA, WGU) · **Tools:** Microsoft Excel

[← Back to project overview](../README.md)

---

## Contents
1. [Objective](#1-objective)
2. [Problem Statement](#2-problem-statement)
3. [Data](#3-data)
4. [Methodology](#4-methodology)
5. [Analysis](#5-analysis)
6. [Key Findings](#6-key-findings)
7. [Sensitivity Check](#7-sensitivity-check)
8. [Limitations](#8-limitations)
9. [Recommendation](#9-recommendation)
10. [Conclusion](#10-conclusion)

---

## 1. Objective

Determine which drug-line strategy will maximize expected financial value for MPC as it faces new competition and uncertain market demand. The report evaluates three options, recommends a primary and a backup course of action, and explains the limits of the analysis.

---

## 2. Problem Statement

A new competitor has entered MPC's market, and future demand is uncertain. MPC must choose one of three strategies:

| Option | Description |
|---|---|
| **New Drug Line** | Develop and launch a new drug |
| **Existing Drug Line** | Modify and relaunch a drug MPC already sells |
| **No Change** | Keep the current approach |

**Business question:** Which strategy gives MPC the highest expected monthly profit, given the chance that market demand turns out favorable or unfavorable?

---

## 3. Data

The dataset (`Drug Market Analysis.xlsm`) was provided by Western Governors University for this course. It may be simulated for learning purposes.

For each option, it gives the profit per unit, the expected monthly demand in a favorable and an unfavorable market, and the probability of each market outcome.

| Option | Profit per unit | Favorable demand (units/mo) | Favorable probability | Unfavorable demand (units/mo) | Unfavorable probability |
|---|---|---|---|---|---|
| New Drug Line | $0.68 | 4,966 | 76% | 1,205 | 24% |
| Existing Drug Line | $0.98 | 5,377 | 60% | 1,807 | 40% |
| No Change | $0.84 | 1,101 | 88% | 541 | 12% |

For each option, the two probabilities add up to 100%.

![Drug line input values](../Results/Drug%20Line%20Values.png)

---

## 4. Methodology

**Why a decision tree?** This problem has everything a decision tree needs:
- **Clear choices:** three strategies MPC controls
- **Uncertain outcomes:** favorable or unfavorable demand, which MPC doesn't control
- **Known probabilities** for each outcome
- **Payoffs** that can be calculated for every path

**Steps:**
1. **Payoff** for each path = profit per unit × monthly demand
2. **Weighted value** for each path = probability × payoff
3. **Expected value (EV)** for each option = favorable weighted value + unfavorable weighted value
4. **Decision rule:** choose the option with the highest expected value

All calculations were done in Excel.

---

## 5. Analysis

### 5.1 Payoffs

| Option | Favorable payoff | Unfavorable payoff |
|---|---|---|
| New Drug Line | $0.68 × 4,966 = **$3,376.88** | $0.68 × 1,205 = **$819.40** |
| Existing Drug Line | $0.98 × 5,377 = **$5,269.46** | $0.98 × 1,807 = **$1,770.86** |
| No Change | $0.84 × 1,101 = **$924.84** | $0.84 × 541 = **$454.44** |

### 5.2 Expected values

| Option | Favorable weighted value | Unfavorable weighted value | Expected value |
|---|---|---|---|
| New Drug Line | 0.76 × $3,376.88 = $2,566.43 | 0.24 × $819.40 = $196.66 | **$2,763.08** |
| **Existing Drug Line** | 0.60 × $5,269.46 = $3,161.68 | 0.40 × $1,770.86 = $708.34 | **$3,870.02** ✅ |
| No Change | 0.88 × $924.84 = $813.86 | 0.12 × $454.44 = $54.53 | **$868.39** |

![Expected value calculations](../Results/Expected%20Value%20Calculations.png)

### 5.3 Decision tree

The tree shows each option (decision nodes), its two possible market outcomes (chance nodes), and the payoff and expected value for each path.

![Drug market decision tree](../Results/Drug%20Market%20Analysis%20Decision%20Tree.png)

*Note: the diagram labels the weighted values and final results as "Earned Value." The correct term is **expected value**; earned value is a separate project-management measure.*

---

## 6. Key Findings

1. **Modifying the existing drug line has the highest expected value:** $3,870.02 per month.
2. **It beats the alternatives by a wide margin:** about **40% more** than a new drug line ($2,763.08) and about **4.5× more** than no change ($868.39).
3. **It wins in both market outcomes.** In a favorable market it pays $5,269.46 vs. $3,376.88 for a new drug. In an unfavorable market it pays $1,770.86 vs. $819.40.
4. **Its worst case beats no change's best case.** The existing drug's unfavorable payoff ($1,770.86) is higher than no change's favorable payoff ($924.84).
5. **A new drug has the most reliable upside, but less of it.** A 76% chance of favorable demand, but a lower profit per unit ($0.68) limits its value.
6. **No change is the safest but least valuable.** An 88% chance of favorable demand can't make up for low demand.

---

## 7. Sensitivity Check

The existing drug line has the *lowest* chance of favorable demand (60%), so it's worth testing how much that estimate matters.

- **Break-even point:** the existing drug line stays ahead of a new drug as long as its chance of favorable demand is at least **~28%**:
  $1,770.86 + p × ($5,269.46 − $1,770.86) = $2,763.08 → **p ≈ 0.28**
  The estimate is 60%, so it could be cut by more than half without changing the decision.
- **Best case for a new drug:** even if a new drug were *certain* to meet favorable demand, its payoff ($3,376.88) would still be below the existing drug's expected value ($3,870.02).

**Conclusion:** the recommendation does not depend on precise probability estimates.

---

## 8. Limitations

- **Costs aren't included.** Payoffs reflect monthly profit from sales only. Development, regulatory approval, and launch costs aren't modeled. They would likely be highest for a new drug, which would strengthen the recommendation.
- **Only two outcomes.** Real demand falls on a range, not just "favorable" or "unfavorable."
- **One time period.** The model shows monthly value and ignores timing, ramp-up, product life cycle, and the long-term value of a new product.
- **Inputs are given, not tested.** Probabilities and demand come from the course dataset and weren't validated against market research.
- **Competitor response isn't modeled.** The new competitor's pricing or marketing could change demand for every option.

---

## 9. Recommendation

| | Strategy | Expected value | Rationale |
|---|---|---|---|
| 🥇 **Primary** | **Modify the existing drug line** | $3,870.02 / month | Highest expected value, best result in both market outcomes, and holds up under the sensitivity check |
| 🥈 **Backup** | Develop a new drug line | $2,763.08 / month | Second-highest value and a 76% chance of favorable demand; consider it if the existing drug can't be modified (e.g., regulatory or patent limits) |
| ❌ **Avoid** | No change | $868.39 / month | Lowest value; leaves MPC exposed to the new competitor |

**Before committing,** MPC should add development and launch costs, extend the model to a multi-year horizon, and test the key inputs (demand and profit per unit) with market research.

---

## 10. Conclusion

The decision tree analysis gives MPC a clear, defensible direction: **modify the existing drug line.** It has the highest expected value, performs best whether the market turns out well or badly, and stays the right choice even if its probability of success is far lower than estimated.

---

**Files:** [Excel workbook](../Data/Drug%20Market%20Analysis.xlsm) · [Input values](../Results/Drug%20Line%20Values.png) · [Expected value calculations](../Results/Expected%20Value%20Calculations.png) · [Decision tree](../Results/Drug%20Market%20Analysis%20Decision%20Tree.png)
