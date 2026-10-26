<div align="center">

# 💊 Drug Market Analysis
### Which drug-line strategy should a pharma company pursue when demand is uncertain?

**Decision Analysis · Expected Value · Excel** · MBA, Data-Driven Decision Making

[![Data Portfolio](https://img.shields.io/badge/Data_Portfolio-View-2EA44F?style=flat&logo=github&logoColor=white)](https://github.com/LashawnFofung/Data-Analysis-Portfolio)
[![MBA Portfolio](https://img.shields.io/badge/MBA_Portfolio-View-6E40C9?style=flat&logo=github&logoColor=white)](https://github.com/LashawnFofung/MBA-IT-Management-Portfolio)

</div>

---

## Contents
[TL;DR](#tldr) · [The Decision](#the-decision) · [Method](#method-decision-tree) · [Results](#results) · [Why the Answer Holds Up](#why-the-answer-holds-up) · [Recommendation](#recommendation) · [Limitations](#limitations) · [Files](#files)

---

## TL;DR

| | |
|---|---|
| **Business question** | Facing new competition, should Major Pharmaceutical Company (MPC) develop a new drug, modify an existing one, or change nothing? |
| **Method** | Decision tree with expected value (EV), built in Excel |
| **Answer** | **Modify the existing drug line.** Expected value of **$3,870 per month**, about 40% higher than a new drug ($2,763) and 4.5× higher than no change ($868) |
| **Why it's robust** | It pays more than a new drug in both good and bad markets, and stays the best choice unless its odds of favorable demand fall below ~28% (estimate: 60%) |

---

## The Decision

MPC faces new competition and uncertain demand. It has three options:

| Option | Description |
|---|---|
| **New Drug Line** | Develop and launch a new drug |
| **Existing Drug Line** | Modify and relaunch a drug MPC already sells |
| **No Change** | Keep the current approach |

Each option could meet **favorable** or **unfavorable** market demand, with different probabilities.

---

## Method: Decision Tree

A decision tree fits this problem because it has clear choices, two possible market outcomes for each, a probability for each outcome, and a payoff that can be calculated.

**For each option:**
1. **Payoff** = profit per unit × monthly demand
2. **Expected value** = (favorable probability × favorable payoff) + (unfavorable probability × unfavorable payoff)
3. **Choose** the option with the highest expected value

<img src="Results/Drug%20Market%20Analysis%20Decision%20Tree.png" width="850" alt="Decision tree showing the three options, their favorable and unfavorable outcomes, payoffs, and expected values">

---

## Results

### Inputs and payoffs

| Option | Profit per unit | Favorable demand (units/mo) | Favorable probability | Unfavorable demand (units/mo) | Unfavorable probability |
|---|---|---|---|---|---|
| New Drug Line | $0.68 | 4,966 | 76% | 1,205 | 24% |
| **Existing Drug Line** | **$0.98** | **5,377** | **60%** | **1,807** | **40%** |
| No Change | $0.84 | 1,101 | 88% | 541 | 12% |

### Expected value

| Option | Favorable payoff | Unfavorable payoff | Expected value (per month) |
|---|---|---|---|
| New Drug Line | $3,376.88 | $819.40 | $2,763.08 |
| **Existing Drug Line** | **$5,269.46** | **$1,770.86** | **$3,870.02** ✅ |
| No Change | $924.84 | $454.44 | $868.39 |

**Worked example (Existing Drug Line):**
(0.60 × $5,269.46) + (0.40 × $1,770.86) = $3,161.68 + $708.34 = **$3,870.02**

---

## Why the Answer Holds Up

The Existing Drug Line has the **lowest** chance of favorable demand (60%), yet it still wins. A quick sensitivity check shows the answer isn't fragile:

- **It wins state by state.** In a favorable market it pays $5,269 vs. $3,377 for a new drug. In an unfavorable market it pays $1,771 vs. $819.
- **A new drug can't catch up.** Even if a new drug were *certain* to meet favorable demand, it would earn $3,377 — still less than the existing drug's expected $3,870.
- **The break-even point is far away.** The existing drug stays ahead as long as its chance of favorable demand is at least **~28%**. The estimate is 60%, so it could be cut by more than half without changing the decision.

## Recommendation

| | Strategy | Expected value | Why |
|---|---|---|---|
| 🥇 **Primary** | **Modify the existing drug line** | $3,870 / month | Highest expected value and the best result in both markets |
| 🥈 **Backup** | Develop a new drug line | $2,763 / month | Strong upside in a favorable market, and a 76% chance of getting it |
| ❌ **Avoid** | No change | $868 / month | Lowest value; leaves MPC exposed to the new competition |

---

## Limitations

- **Costs aren't included.** Payoffs are monthly profit from sales. Development, approval, and launch costs aren't modeled, and they would likely make a new drug look even less attractive.
- **Two outcomes only.** Real demand falls on a range, not just "favorable" or "unfavorable."
- **One time period.** The model shows monthly value and doesn't account for timing, ramp-up, or the long-term value of a new product.
- **Given inputs.** Probabilities and demand come from the course dataset and weren't independently tested.

**Next step for a real decision:** add development costs and a multi-year time horizon, then run a sensitivity analysis on the key inputs.

---

## Files

| File | What it is |
|---|---|
| [Drug Market Analysis.xlsm](Data/Drug%20Market%20Analysis.xlsm) | Excel workbook: inputs, expected value calculations, and decision tree |
| [Data Analysis report](Report/Data%20Analysis.md) | Written report |
| [`Results/`](Results) | Images of the [input table](Results/Drug%20Line%20Values.png), [expected value calculations](Results/Expected%20Value%20Calculations.png), and [decision tree](Results/Drug%20Market%20Analysis%20Decision%20Tree.png) |

**Data source:** Provided by Western Governors University (WGU) for the Data-Driven Decision Making course. The data may be simulated for learning purposes and isn't for commercial use.

<div align="center">

**Lashawn Fofung** · Technical Product Manager · [LinkedIn](https://www.linkedin.com/in/lashawnfofung/) · [Data Portfolio](https://github.com/LashawnFofung/Data-Analysis-Portfolio) · [MBA Portfolio](https://github.com/LashawnFofung/MBA-IT-Management-Portfolio)

</div>
