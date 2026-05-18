---
layout: post
title: "Biostatistics Without Fear"
date: 2026-05-17
categories: [Research]
author: Dr Kembhavi
---

**Biostatistics Without Fear: A Plain-Language Guide for Ayurveda Scholars**

**Part 2: From Test Selection to Ayurveda-Specific Challenges**

**Dr. Aakash Kembhavi**, MD (Ayu), PGDMLS, MS (Counselling &amp; Psychotherapy)

*"The goal is not to do statistics. The goal is to answer a question — honestly, completely, and with full acknowledgement of what you do not know."*

*This article was produced with AI collaboration assistance under the ****Ayurveda Unfiltered**** editorial framework. AI tools were used for structural drafting and language refinement. Final intellectual framing, critical perspective, and thematic direction are those of the named author.*

**Picking Up Where We Left Off**

In Part 1 of this series, we built the foundation.

We established that biostatistics is not mathematics — it is reasoning under uncertainty. We worked through the 20 terms every Ayurveda scholar must know cold: population and sample, variables and confounders, null and alternative hypotheses, alpha and power, p-value and confidence interval. We examined the four types of data — nominal, ordinal, interval, and ratio — and why getting this wrong at the design stage corrupts everything that follows. We walked through descriptive statistics and the correct way to present your data before any hypothesis testing begins. We spent serious time on the p-value — its precise meaning, its profound limitations, and the specific ways in which Ayurveda research misuses it routinely. And we made the case for confidence intervals as a more honest and more informative companion to any reported result.

If you have not read Part 1, do that first. The concepts in this article build directly on that foundation. Without it, sections of what follows will be technically legible but conceptually incomplete.

*[Link to Part 1: Biostatistics Without Fear — Sections 1 to 7]*

**What Part 2 Covers — and Why It Matters More Than You Might Expect**

Part 1 answered the question: *what are these concepts and what do they mean?*

Part 2 answers the harder, more practical questions:

*Which statistical test do I actually use for my data — and why?*

*How many patients do I genuinely need — and what happens if I don't have them?*

*What does correlation actually tell me — and what does it not?*

*How do I read a SPSS output table and report it correctly?*

*And — most critically for those of us working in this tradition — what are the specific statistical challenges that Ayurveda research faces that mainstream methodology textbooks never address?*

These are the questions that sit between a scholar who knows what a p-value means in theory and a scholar who can design, execute, and report a study that withstands scrutiny. That gap — between conceptual literacy and practical application — is where most Ayurveda researchers currently live. It is an uncomfortable place. This article is designed to move you out of it.

Part 2 does not assume you are comfortable with the material from Part 1. It assumes you have read it and understood it at the level of a careful non-specialist. Where Part 1 concepts are needed to make sense of something in Part 2, they are briefly restated — not because this article is self-contained, but because good teaching does not assume that everything learned last week is still perfectly accessible this week.

One further note on tone. Part 1 was deliberately critical — it named the recurring errors in Ayurveda research without softening the language. Part 2 continues in that spirit, but it is weighted more toward the practical and the constructive. The critique is still here. But the tools to do better are here alongside it — specific, usable, and freely available.

This is what being a critical insider means in practice: not just identifying what is wrong, but knowing how to make it right.

Let us continue.

**Section 8: Choosing the Right Statistical Test**

This is the question every Ayurveda scholar asks — and the one that generates the most confusion. The answer follows a logic. Learn the logic and the choice becomes straightforward.

**Step 1: What type of data is your outcome variable?**

- Ratio/interval (continuous) → parametric or non-parametric tests
- Ordinal → non-parametric tests
- Nominal (categorical) → chi-square or Fisher's exact

**Step 2: Is your data approximately normally distributed?** For continuous data, check whether the distribution is approximately normal using visual inspection (histogram), or formal tests (Shapiro-Wilk for small samples). If yes → parametric tests. If no → non-parametric tests.

**Step 3: How many groups are you comparing?**

- Two groups → t-test family or Mann-Whitney U
- Three or more groups → ANOVA family or Kruskal-Wallis

**Step 4: Are the groups independent or paired?**

- Independent (different participants in each group) → independent samples tests
- Paired (same participants measured twice, e.g., before and after) → paired tests

**The Decision Framework**

| Situation | Parametric Test | Non-Parametric Alternative |
| --- | --- | --- |
| Two independent groups, continuous data | Independent samples t-test | Mann-Whitney U test |
| Two paired groups / before-after, continuous data | Paired t-test | Wilcoxon signed-rank test |
| Three or more independent groups, continuous data | One-way ANOVA | Kruskal-Wallis test |
| Three or more paired groups / repeated measures | Repeated measures ANOVA | Friedman test |
| Two categorical variables | Chi-square test | Fisher's exact (small samples) |
| Relationship between two continuous variables | Pearson correlation | Spearman correlation |

**The most common test in Ayurveda research: the paired t-test**

Most Ayurveda dissertations compare a single group before and after an intervention, without a control group. The paired t-test or its non-parametric equivalent (Wilcoxon signed-rank) is used.

This is statistically appropriate — if the data meet the assumptions. But the conclusion that can be drawn is severely limited: the patients changed. Not that the intervention caused the change.

**Post-hoc tests after ANOVA**

When ANOVA identifies a significant difference among three or more groups, it tells you that at least one group differs from the others — but not which one. Post-hoc tests (Tukey, Bonferroni, Scheffé) perform pairwise comparisons while controlling for the increased risk of false positives that comes from multiple testing. Always specify which post-hoc test was used.

**In Ayurveda Research, This Means:** The single most common error is applying a paired t-test to ordinal symptom score data. The test is parametric; the data are not continuous. The correct test is the Wilcoxon signed-rank test. This error appears in the majority of Ayurveda dissertations and published papers.

**Section 9: Sample Size and Statistical Power**

**Why sample size is calculated, not guessed**

Every study requires a sample size calculation before data collection begins. This calculation is not bureaucratic paperwork — it is a fundamental part of the study design. A study with an inadequate sample size is an unethical study: it exposes participants to intervention and observation without any realistic prospect of generating reliable conclusions.

**The four inputs to a sample size calculation**

- **Expected effect size** — how large a difference do you anticipate between groups? Smaller effects require larger samples to detect.
- **Alpha (α)** — your acceptable false positive rate. Conventionally 0.05.
- **Power (1 − β)** — your desired probability of detecting a real effect. Conventionally 0.80.
- **Standard deviation** — for continuous outcomes, the variability in your population, usually estimated from pilot data or previous studies.

These four inputs are fed into a formula (or a free software tool such as G*Power, available at https://www.psychologie.hhu.de/arbeitsgruppen/allgemeine-psychologie-und-arbeitspsychologie/gpower) which outputs the minimum required sample size.

**What happens when studies are underpowered**

An underpowered study has a high Type II error rate — a high probability of missing a real effect. If your study has 50% power, you have a coin-flip chance of detecting the effect even if it genuinely exists.

In Ayurveda research, most trials are severely underpowered. A study with 30 patients per group typically has power of 20–40% for detecting moderate effects. This means: even if the treatment works, the study would fail to detect it more than half the time.

The publication bias compounds this problem. Studies that happen to reach p &lt; 0.05 — even if underpowered and unreliable — get published. Studies that find no significant difference — often because they lacked power, not because the treatment is ineffective — do not.

**The 30-patient problem — stated statistically**

To detect a moderate effect (Cohen's d = 0.5) with 80% power at alpha = 0.05 in an independent-groups comparison, you need approximately 64 participants per group — 128 total. The standard Ayurveda dissertation with 30 per group (60 total) has power of approximately 55% for the same effect. It will miss a real moderate effect nearly half the time.

There is no statistical justification for 30 patients per group as a universal standard. It is an institutional habit that has never been examined and should no longer be accepted.

**In Plain Language:** Before you collect a single data point, calculate how many patients you actually need. If your institution's infrastructure cannot support that number, your study question needs to change — or your study design does.

**Section 10: Correlation, Regression, and What They Actually Mean**

**Correlation**

Correlation measures the strength and direction of the linear relationship between two continuous variables. It is expressed as a correlation coefficient (r) ranging from −1 to +1.

- r = +1: perfect positive correlation (as one variable increases, the other increases perfectly)
- r = 0: no linear relationship
- r = −1: perfect negative correlation

In practice: r &gt; 0.7 is considered strong, 0.4–0.7 moderate, and &lt; 0.4 weak — though these thresholds are context-dependent.

**Pearson vs Spearman**

Pearson correlation is parametric — appropriate for normally distributed continuous data. Spearman correlation is non-parametric — appropriate for ordinal data or non-normally distributed continuous data. Because most Ayurveda outcome measures are ordinal, Spearman is usually the appropriate choice.

**Correlation is not causation**

This cannot be stated often enough. If body weight and fasting blood glucose are correlated in your sample, it means they tend to move together. It does not mean weight causes glucose elevation, or that glucose elevation causes weight gain. A third variable — physical inactivity, dietary pattern, insulin resistance — may drive both.

In Ayurveda research, correlational findings between classical parameters (Prakriti type, Agni status) and biomedical outcomes are frequently reported as if they imply a causal mechanism. They do not.

**Simple Linear Regression**

Regression goes beyond correlation to model the relationship between variables: it predicts the value of one variable (the dependent variable) from one or more others (independent variables). Simple linear regression uses one predictor. Multiple regression uses several.

In Ayurveda research, regression is underused where it would be appropriate (e.g., identifying which baseline characteristics predict treatment response) and avoided because scholars are not taught how to interpret the output.

**In Ayurveda Research, This Means:** Report Spearman correlations for ordinal data, always state the r value and p-value together, and never interpret a correlation as evidence of a mechanism. The mechanism requires a different study design.

**Section 11: Reading Statistical Output — What the Tables Actually Mean**

Most Ayurveda scholars receive their SPSS or similar software output and face a wall of numbers they were not trained to interpret. This section walks you through it.

**Standard reporting format**

The international standard for reporting statistical results is specific:

- Continuous, normally distributed data: **Mean ± SD** at baseline and endpoint; the test statistic (t value), degrees of freedom (df), and p-value. Example: "Fasting blood glucose decreased from 148.3 ± 22.6 mg/dL to 118.7 ± 19.4 mg/dL (t = 6.24, df = 29, p &lt; 0.001)."
- Ordinal or non-normally distributed data: **Median (IQR)**; the test statistic (z or W) and p-value. Example: "Symptom score decreased from 7 (IQR 5–9) to 3 (IQR 2–5) (z = −4.78, p &lt; 0.001)."
- Categorical data: **n (%)** for each category; chi-square value (χ²), df, and p-value.
- Always include effect size and 95% CI alongside p-values.

**What SPSS output tables contain**

The paired t-test output in SPSS will show you: the mean difference, SD of the difference, SE of the difference, 95% CI of the difference, t statistic, df, and two-tailed p-value. Report all of these — not just the p-value.

The Mann-Whitney U output will show you: the U statistic, z value, and asymptotic significance (p-value). For small samples, use exact significance rather than asymptotic.

**Degrees of freedom**

Degrees of freedom (df) is a concept that confuses many scholars. Think of it as the number of values in a calculation that are free to vary once certain constraints are set. For a t-test comparing two groups of n₁ and n₂: df = (n₁ + n₂ − 2). Report it — it tells the reader the effective sample size used in the calculation.

**In Plain Language:** Copy the full statistical output into your results section — not just p-values. A result reported as only "p = 0.03" is incomplete. The test statistic, degrees of freedom, effect size, and confidence interval are all part of the result.

**Section 12: Ayurveda-Specific Statistical Challenges**

This final section addresses the methodological problems that are unique to — or particularly acute in — Ayurveda research.

**Measuring Classical Constructs Numerically**

How do you assign a number to Agni daurbalya? How do you quantify Srotorodha? The answer is: with great difficulty and explicit acknowledgement of the limitations.

The first requirement is a validated measurement instrument. If you are scoring Agni status on a 0–3 scale, you must demonstrate that two observers using your scale will arrive at the same score for the same patient (inter-rater reliability), and that the same observer will arrive at the same score on two separate occasions (test-retest reliability). The statistic used for this is **Cohen's Kappa (κ)**:

- κ &lt; 0.20: poor agreement
- κ 0.21–0.40: fair agreement
- κ 0.41–0.60: moderate agreement
- κ 0.61–0.80: substantial agreement
- κ &gt; 0.80: almost perfect agreement

Most Ayurveda studies use observer-rated outcome measures without reporting any reliability statistics. This is not a minor omission. It is a fundamental failure of measurement validity.

**The Problem with Composite Symptom Scores**

Many Ayurveda studies create a composite symptom score by adding up individual symptom grades — for example, scoring each of five symptoms on a 0–3 scale to produce a total score of 0–15. This appears to convert ordinal data into a continuous score.

The problem: the total score is still ordinal in nature. The intervals between total scores are not necessarily equal. A change from 10 to 5 may not represent the same clinical change as a change from 5 to 0. Unless the composite score has been formally validated as an interval-level measure, non-parametric statistics are still required.

**Inter-rater Reliability for Prakriti Assessment**

Multiple studies have attempted to use Prakriti as an independent variable. The validity of this approach depends entirely on whether Prakriti can be assessed consistently across observers. Current evidence suggests it cannot — at least not with existing assessment tools. Kappa values for Prakriti assessment between different observers are generally low.

This does not mean Prakriti is not a meaningful construct. It means we do not yet have a measurement instrument that captures it reliably enough for research purposes. Proceeding as if we do produces unreliable data.

**Multiplicity: The Multiple Testing Problem**

If a study tests 15 different outcome variables and reports all p-values as if each were independent, the overall probability of at least one false positive is dramatically higher than 0.05. For 15 independent tests at alpha = 0.05, the probability of at least one false positive is approximately 54%.

The solution is either to pre-specify a single primary outcome before data collection, or to apply a correction for multiple comparisons (Bonferroni correction: divide alpha by the number of tests; or False Discovery Rate methods for larger numbers of comparisons).

Ayurveda studies routinely test multiple outcomes and report all significant p-values as findings without any multiplicity correction. This inflates the apparent evidence base and contributes to findings that do not replicate.

**Repeated Measures Designs for Panchakarma Studies**

Panchakarma procedures are administered over multiple sessions, with outcomes potentially measured at multiple time points (before, during, immediately after, one month after, three months after). This is a repeated measures design — and it has specific statistical requirements.

Repeated measures ANOVA (or its non-parametric equivalent, the Friedman test) is required when you have more than two measurement points on the same participants. Running multiple paired t-tests between consecutive time points — without correction — is statistically incorrect and inflates the Type I error rate. Yet this is what most Ayurveda Panchakarma studies do.

**The Honest Conclusion:** These are not minor procedural errors. They are systematic failures that collectively produce a published literature that overstates the evidence for Ayurvedic interventions. Correcting them requires not just individual scholars learning better methods, but a field-wide change in what is accepted as adequate methodology.

**Conclusion: From Fear to Fluency**

Biostatistics is not a wall between Ayurveda and scientific credibility. It is a bridge — the set of tools that allows a tradition with millennia of clinical observation to translate that observation into language that the wider world can evaluate, question, and build upon.

The fear of statistics is understandable. But it is no longer excusable — not when the tools are freely available, the concepts are learnable, and the consequences of statistical illiteracy are this clearly visible in our published literature.

The path forward is not to hire a statistician to run your numbers after the study is done. It is to understand the statistical logic well enough to design your study correctly from the beginning — so that the numbers, when they come, mean something.

Start with the basics in this article. Run your data through G*Power before you recruit a single patient. Use the decision framework in Section 8 before you open SPSS. Report your results in the full format specified in Section 11 — not just the p-values.

And remember: a tradition that cannot withstand statistical scrutiny is not a tradition that needs protection from statistics. It is a tradition that needs better studies.

That is what rigour looks like from the inside. That is what being a critical insider means.

Begin with the numbers. Follow them honestly. Report them completely.

The tradition will be stronger for it.

*Ayurveda Unfiltered is a forum for critical engagement with Ayurvedic education, practice, and research. Articles are posted on this blog every week. A companion WhatsApp discussion community engages with each article through structured weekend conversations. If you would like to join the discussion, reach out through the blog.*

*© 2026 Astanga Wellness Pvt. Ltd. All rights reserved.*

---

*Share your thoughts in the comments below.*
