# A_B-Testing-Marketing-Analytics

# Marketing A/B Test Analysis - Do Ads Actually Drive Conversions?

A structured analysis of a real-world marketing experiment across ~588,000 users, examining whether ad exposure meaningfully increases conversion rates compared to a neutral PSA control.

---

## Background

Most A/B test write-ups stop at comparing two percentages. This one doesn't.

The dataset comes from an online experiment where users were randomly assigned to one of two groups — one saw **advertisements**, the other saw a **public service announcement (PSA)**. The core question is deceptively simple:

> Do ads actually move the needle, or is the difference noise?

To answer that properly, the analysis goes beyond averages into exposure segmentation, time-based patterns, and statistical validation.

---

## Dataset

- ~588,000 users
- Two groups: **Ad** (treatment) and **PSA** (control)
- Features: group assignment, conversion status, number of ads seen, day and hour of peak exposure

One thing worth flagging upfront — **96% of users were in the ad group**, with only 4% in the PSA group. This imbalance is accounted for in the statistical testing, but it's the kind of detail that matters when interpreting results.

---

## Analysis Structure

The approach mirrors how a real-world A/B test would be evaluated in a professional setting.

**1. Distribution check**
Before anything else — understand what the data actually looks like and flag anything unusual.

**2. Conversion rate comparison**
Core question answered first: do users who see ads convert at a higher rate?

**3. Ad exposure segmentation**
Not all users saw the same number of ads. Segmenting by exposure volume (1–10, 11–50, 51–100, 100+) reveals how dose-response behavior looks — and where the interpretation gets complicated.

**4. Time-based patterns**
Which day of the week and hour of the day yield the highest conversion rates? Findings here translate directly into campaign scheduling decisions.

**5. Statistical validation**
A Chi-Square test of independence confirms whether the observed difference is statistically significant or a byproduct of sample size and chance.

---

## Key Findings

### Ads increase conversions — and the effect is real

| Group | Conversion Rate |
|-------|----------------|
| Ad    | 2.55%          |
| PSA   | 1.79%          |

That's a **43% relative lift**. The Chi-Square statistic came in around 54 with a p-value well below 0.001, meaning this result is not a statistical fluke.

---

### Higher exposure correlates with higher conversion

| Ads Seen | Conversion Rate |
|----------|----------------|
| 1–10     | 0.33%          |
| 11–50    | 1.89%          |
| 51–100   | 11.63%         |
| 100+     | 17.14%         |

The pattern is clear, but the interpretation requires caution. This is a correlation — it's equally plausible that high-intent users naturally encounter more ads, rather than ads themselves causing conversion. The data can't resolve that question on its own.

---

### Timing has a measurable impact

- **Best day:** Monday (~3.32% conversion rate)
- **Worst day:** Saturday (~2.13%)
- **Best hours:** 14:00–16:00 and 20:00–21:00

Mid-afternoon and early evening consistently outperform other windows. For campaign scheduling, this is actionable.

---

## Limitations

**Group imbalance** — A 96/4 split is workable but not ideal. Statistical tests are adjusted, but it limits certain types of subgroup analysis.

**Correlation vs. causation** — The exposure-to-conversion relationship can't be cleanly attributed to ad effectiveness without knowing more about how high-exposure users differ behaviorally from low-exposure ones.

**Randomization unknown** — The dataset doesn't document how users were assigned to groups. If assignment wasn't truly random, selection bias could affect the results.

**No user-level context** — Without demographic, behavioral, or historical purchase data, deeper segmentation isn't possible.

---


## Final Takeaway

If I had to summarize this for a stakeholder:

- The ad campaign led to a **43% increase in conversion rate**
- The result is **statistically significant** — not random
- Higher ad exposure is strongly associated with higher conversion
- **Best performance windows:** Monday, mid-afternoon, and early evening

These are actionable insights — not just analysis.

---
## Why This Analysis Matters

A lot of marketing analyses answer the wrong question. They report a number and call it a conclusion.

This one works through the problem the way a business decision actually requires — checking whether the effect is real, understanding the mechanism behind it (or at least its limits), and extracting the kind of time-based and exposure-level insight that informs what to do next.

The 43% lift is the headline. The statistical validation, the exposure segmentation, and the timing breakdown are what make it useful.

## Tech Stack

- **Python** — core analysis
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **SciPy** — Chi-Square significance testing
- **Matplotlib** — visualization

---

