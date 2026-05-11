---
layout: post
title: "Part 1 Biostatistics Without Fear"
date: 2026-05-10
categories: [Research]
author: Dr Kembhavi
---

# Biostatistics Without Fear: A Plain-Language Guide for Ayurveda Scholars Part 1: Foundations, Concepts, and the p-value Problem**Dr. Aakash Kembhavi**, MD (Ayu), PGDMLS, MS (Counselling &amp; Psychotherapy)

"Statistics is the grammar of science." — Karl Pearson

This article was produced with AI collaboration assistance under the ***Ayurveda Unfiltered*** editorial framework. AI tools were used for structural drafting and language refinement. Final intellectual framing, critical perspective, and thematic direction are those of the named author.

## Introduction: The Number That Terrifies and the Tradition That Should Not Fear ItWalk into any Ayurveda PG department in the country and ask a final-year scholar what their biggest anxiety is about their dissertation. The answer, almost universally, is not the literature review. It is not the clinical protocol. It is not even the viva.

It is the statistics.

And this fear is understandable. Biostatistics is typically taught in a single semester, often by a faculty member who is themselves not a statistician, using a textbook that was not written with Ayurveda research in mind, to students who have not yet collected a single data point. The result is a field where scholars can name a t-test but cannot tell you when not to use one, where p &lt; 0.05 is treated as an achievement rather than a threshold, and where a SPSS output table is copied into a dissertation without the scholar fully understanding what any of it means.

This article is written to change that — one concept at a time.

Biostatistics is not mathematics. It is reasoning under uncertainty. And Ayurveda, as a clinical tradition, has always reasoned under uncertainty. When you weigh Nidana against Samprapti, when you estimate the probability that a patient's presentation represents a Vata versus Pitta predominance, when you decide whether a symptom cluster signals an Upadrava or a new pathology — you are doing probabilistic reasoning. Biostatistics simply formalises that process, makes it transparent, and makes it checkable.

You have been doing this all along. You just didn't have the vocabulary.

**This is a two-part article.** Part 1 — which you are reading now — builds the conceptual foundation: the essential vocabulary, the types of data, descriptive statistics, the logic of hypothesis testing, the p-value, and confidence intervals. These are the concepts without which nothing that follows in Part 2 will make sense.

Part 2 picks up where this article ends. It covers the practical application: how to choose the right statistical test for your data, how to calculate the sample size your study actually needs, how to read and report a SPSS output table correctly, and — most importantly — the specific statistical challenges that are unique to Ayurveda research and that no mainstream methodology textbook adequately addresses.

Read Part 1 carefully and completely before moving to Part 2. The structure is deliberate. The foundation must be in place before the application can be understood.

**Section 1: Why Biostatistics Is Not the Enemy**

The anxiety around statistics in Ayurveda is partly cultural. We are trained in a tradition that privileges qualitative clinical observation — the texture of the pulse, the colour of the tongue, the quality of the patient's voice. Numbers feel foreign, reductive, even antithetical to holistic practice.

But this is a false opposition.

Biostatistics does not replace clinical observation. It answers a different question. Clinical observation answers: *what did I see in this patient?* Biostatistics answers: *how confident can I be that what I saw reflects a real pattern and not a coincidence?*

These are not competing questions. They are complementary ones. A tradition that can answer both is stronger than one that can answer only the first.

The second source of anxiety is more practical: most Ayurveda scholars were never properly taught biostatistics. They were taught procedures — run this test, report that number — without being taught the logic underneath. Procedures without logic produce errors. And in Ayurveda research, those errors are now endemic.

The goal of this article is not to make you a statistician. It is to make you someone who understands what statistics is doing, can choose the right approach for your data, can read a results section critically, and — most importantly — knows when a number that looks convincing is actually telling you very little.

That is a achievable goal. Let us begin.

**Section 2: The Language — 20 Terms You Must Know**

These are not definitions to memorise. They are concepts to understand. Read each one until you can explain it to a colleague without looking at this article.

**1. Population** The entire group you are interested in studying. In an Ayurveda study on Type 2 diabetes, the population might be all adults with Type 2 diabetes attending Ayurvedic outpatient departments in Karnataka. You can never study the entire population. You study a sample from it.

**2. Sample** The subset of the population you actually study. Your sample must be representative of your population — otherwise your findings apply only to the people in your sample, not to the population you want to draw conclusions about.

**3. Variable** Anything that can take different values across individuals. Age, sex, blood glucose, Prakriti, symptom score — all are variables.

**4. Independent Variable** The variable you manipulate or observe as a potential cause. In a clinical trial, this is your intervention — the drug, procedure, or dietary modification being tested.

**5. Dependent Variable** The variable you measure as the outcome — the effect you are looking for. Fasting blood glucose, pain score, haemoglobin level.

**6. Confounding Variable** A variable that influences both the independent and dependent variables, creating a false appearance of a relationship between them. If patients receiving Panchakarma also changed their diet significantly, diet is a confounder. The improvement you observe may be due to diet, not Panchakarma — and if you did not control for it, you cannot distinguish between the two.

**7. Parameter** A numerical value that describes a characteristic of the entire population. Because we rarely study entire populations, parameters are usually unknown — they are what we are trying to estimate.

**8. Statistic** A numerical value calculated from your sample, used to estimate the population parameter. Your sample mean is a statistic. The true population mean is the parameter.

**9. Distribution** The pattern of how values of a variable are spread across a dataset. The most important distribution in biostatistics is the normal distribution — the bell curve — where most values cluster around the mean and fewer appear at the extremes. Many biological variables are approximately normally distributed. Many are not.

**10. Mean** The arithmetic average. Sum all values, divide by the number of observations. Sensitive to extreme values (outliers). If nine patients have a fasting glucose of 120 mg/dL and one has a glucose of 420 mg/dL, the mean will be misleadingly high.

**11. Median** The middle value when data are ranked from lowest to highest. Resistant to outliers. For skewed biological data, the median is almost always a more honest measure of central tendency than the mean.

**12. Standard Deviation (SD)** A measure of how spread out values are around the mean. A small SD means values cluster tightly. A large SD means they are widely dispersed. When you report a mean, always report the SD alongside it: mean ± SD.

**13. Standard Error (SE)** Not the same as SD — a distinction that trips up many scholars. The SE measures how precisely your sample mean estimates the true population mean. It decreases as your sample size increases. A large sample gives a more precise estimate of the population mean, reflected in a smaller SE.

**14. Null Hypothesis (H₀)** The default assumption that there is no effect, no difference, no relationship. Your study sets out to test whether the evidence is strong enough to reject this assumption. You never "prove" the null hypothesis false — you either reject it or fail to reject it.

**15. Alternative Hypothesis (H₁)** The hypothesis that there is an effect, difference, or relationship. This is what you are hoping to demonstrate. But hoping is not the same as proving.

**16. Alpha (α)** The probability of incorrectly rejecting the null hypothesis when it is actually true — a false positive. By convention, alpha is set at 0.05. This means you accept a 5% chance of concluding an effect exists when it does not.

**17. Statistical Power (1 − β)** The probability of correctly detecting a real effect when one exists. Conventionally set at 0.80 — meaning an 80% chance of finding the effect if it is real. Most small Ayurveda trials have power well below this threshold, meaning they would miss a real effect more often than they detect it.

**18. p-value** The probability of observing a result at least as extreme as the one obtained, assuming the null hypothesis is true. This is discussed in detail in Section 6. For now: it is a probability, not a measure of the size or importance of an effect.

**19. Confidence Interval (CI)** A range of values within which the true population parameter is likely to fall, with a specified degree of confidence. A 95% CI means that if you repeated the study 100 times, 95 of those intervals would contain the true value. Discussed in detail in Section 7.

**20. Effect Size** A measure of the magnitude of the difference or relationship you observed. Effect size tells you how large the effect is. The p-value tells you how confident you are that it is real. Both are necessary. Neither alone is sufficient.

**In Plain Language:** These 20 terms are the alphabet of biostatistics. You cannot read the language without them.

**Section 3: Types of Data and Why They Determine Everything**

The type of data you collect determines which statistical tests you can legitimately use. Using the wrong test for your data type is one of the most common errors in Ayurveda dissertations — and one of the most consequential.

**Nominal Data** Categories with no meaningful order. Blood group (A, B, O, AB). Sex. Prakriti type (Vata, Pitta, Kapha, and their combinations). Religion. You can count how many fall in each category. You cannot calculate a meaningful average. "Average Prakriti" is a meaningless concept.

*Ayurveda example:* Prakriti classification. Deha Prakriti is a nominal variable. You can say 40% of your sample was Vata-Pitta. You cannot say the mean Prakriti was 2.3.

**Ordinal Data** Categories with a meaningful order, but unequal and unmeasurable intervals between them. Pain severity (mild, moderate, severe). Grading of oedema (1+, 2+, 3+, 4+). Symptom scales scored as 0, 1, 2, 3.

The critical point: the gap between "mild" and "moderate" is not necessarily the same as the gap between "moderate" and "severe." You can rank ordinal data. You cannot add, subtract, or average it with the same confidence as ratio data.

*Ayurveda example:* Most symptom scoring systems used in Ayurveda dissertations produce ordinal data. Treating them as if they were ratio data — calculating means and SDs, running t-tests — is a methodological error that appears in the majority of published Ayurveda studies.

**Interval Data** Ordered categories with equal intervals between them, but no true zero point. Temperature in Celsius is the classic example. The difference between 20°C and 30°C is the same as between 30°C and 40°C. But 0°C does not mean "no temperature" — it is an arbitrary point on the scale. You can calculate means and SDs for interval data, but you cannot form ratios (40°C is not "twice as hot" as 20°C).

*Ayurveda example:* Relatively rare in Ayurveda research. Calendar dates and IQ scores are interval-level.

**Ratio Data** Ordered, equal intervals, and a true zero point — zero means the complete absence of the quantity. Height, weight, blood glucose, haemoglobin, serum cholesterol, urine output. You can calculate means, SDs, ratios, and percentages meaningfully. 120 mg/dL fasting glucose is twice 60 mg/dL.

*Ayurveda example:* All biochemical parameters — HbA1c, lipid profile, liver enzymes, haemoglobin — are ratio data. These are the outcomes most amenable to parametric statistical analysis.

**In Ayurveda Research, This Means:** Before you decide which statistical test to use, write down the type of data each of your variables produces. If your primary outcome is an ordinal symptom score, you need non-parametric tests — regardless of what your senior told you to run.

**Section 4: Describing Your Data — Descriptive Statistics**

Before you test any hypothesis, you must describe what you actually observed. This is the purpose of descriptive statistics — not to prove anything, but to show the reader what your data look like.

**Measures of Central Tendency**

The mean, median, and mode all answer the question: what is a typical value in this dataset?

Use the **mean** when your data are approximately normally distributed (ratio or interval data, roughly symmetric). Always report it with the SD: "Mean fasting blood glucose at baseline was 148.3 ± 22.6 mg/dL."

Use the **median** when your data are skewed, when you have ordinal data, or when outliers are present. Report it with the interquartile range (IQR) — the range between the 25th and 75th percentiles. "Median symptom score at baseline was 6 (IQR 4–8)."

The **mode** — the most frequently occurring value — is rarely reported in clinical research except for categorical data.

**Measures of Spread**

The **standard deviation** tells you how spread out your data are around the mean. In a normally distributed dataset, approximately 68% of values fall within 1 SD of the mean, and 95% within 2 SDs. This is useful: if mean haemoglobin is 11.2 g/dL with an SD of 1.4, you know most of your sample falls between 8.4 and 14.0 g/dL.

The **interquartile range** (IQR) tells you where the middle 50% of your data fall. It is the appropriate measure of spread for ordinal or skewed data.

**How to Present Descriptive Data**

Always present baseline characteristics of your study groups in a table. This table should show, for each group: age (mean ± SD or median with IQR), sex (n and %), duration of illness, relevant comorbidities, and key outcome variables at baseline. This allows the reader to judge whether your groups were comparable before the intervention began.

**Common Error in Ayurveda Dissertations:** Reporting means and SDs for ordinal symptom scores — then running a paired t-test on them. Both steps are methodologically incorrect for ordinal data. The correct approach is to report median and IQR, then use the Wilcoxon signed-rank test.

**Section 5: The Logic of Hypothesis Testing**

This section is the conceptual heart of the article. If you understand this, everything else follows.

**The Basic Logic**

Every statistical test begins with the same assumption: the null hypothesis (H₀) is true. There is no effect. There is no difference. The intervention does nothing.

You then collect data and ask: if the null hypothesis were true, how likely is it that I would observe data as extreme as what I actually observed?

If that probability is very low (below your pre-set alpha, typically 0.05), you conclude that the null hypothesis is probably not true — and you reject it in favour of the alternative hypothesis.

If that probability is not sufficiently low, you fail to reject the null hypothesis. This does not mean the null hypothesis is true. It means your evidence was insufficient to overturn it.

**The Courtroom Analogy**

Think of the null hypothesis as innocence. In a criminal trial, the accused is presumed innocent until proven guilty beyond reasonable doubt. The prosecution must produce evidence strong enough to overturn the presumption of innocence.

In hypothesis testing, the null hypothesis is presumed true until your data produce evidence strong enough to overturn it. "Beyond reasonable doubt" in statistics is your alpha level — the threshold of evidence you require.

Crucially: a verdict of "not guilty" does not mean the accused is innocent. It means the evidence was insufficient to convict. Similarly, failing to reject the null hypothesis does not mean the treatment has no effect. It means your study did not produce sufficient evidence to conclude that it does.

**One-Tailed vs Two-Tailed Tests**

A **two-tailed test** asks: is there a difference in either direction? Could the treatment increase or decrease the outcome? This is the appropriate default for most clinical research, because you should be open to the possibility that a treatment could harm as well as help.

A **one-tailed test** asks: is there a difference in one specific direction only? This requires a strong prior justification that an effect in the opposite direction is impossible or irrelevant. One-tailed tests reach significance more easily — which is why researchers sometimes use them without adequate justification. Be sceptical when you see a one-tailed test in an Ayurveda study.

**In Plain Language:** You start by assuming your treatment does nothing. Your data must be unusual enough — under that assumption — to justify concluding otherwise. "Unusual enough" is defined before the study begins, not after the results are in.

**Section 6: The p-value — The Most Misused Number in Ayurveda Research**

The p-value deserves its own section because it is the single most misunderstood concept in Ayurveda research — and its misuse has done more damage to the quality of our published evidence than any other methodological error.

**What the p-value actually is**

The p-value is the probability of observing a result at least as extreme as the one you obtained, *assuming the null hypothesis is true.*

That is a precise and carefully worded definition. Read it again.

It is NOT the probability that your results occurred by chance. It is NOT the probability that the null hypothesis is true. It is NOT a measure of how large or clinically important the effect is. It is NOT evidence that your study was well-designed. It is NOT a guarantee that the result will replicate.

**What p &lt; 0.05 actually means**

If your p-value is 0.03, it means: assuming there is truly no effect, there is a 3% probability of observing data as extreme as what you observed. Because this is below the conventional threshold of 5%, you reject the null hypothesis.

That is all it means.

A p-value of 0.03 in an underpowered, unblinded, single-centre, uncontrolled trial with an unvalidated outcome measure and post-hoc outcome selection tells you almost nothing about whether the treatment genuinely works. The p-value cannot rescue a poorly designed study.

**The p-value and sample size**

Here is something every Ayurveda scholar must understand: p-values are directly influenced by sample size. A very large study will produce statistically significant p-values for tiny, clinically meaningless differences. A very small study will fail to reach significance even for clinically meaningful effects.

If you have 10,000 patients, a 0.5 mmHg reduction in blood pressure will be statistically significant. No clinician would treat a patient to achieve a 0.5 mmHg reduction.

If you have 30 patients, a 15 mmHg reduction — clinically very meaningful — may not reach significance simply because the study lacks power.

This is why effect size and confidence intervals are more informative than p-values alone.

**p-hacking**

p-hacking — also called data dredging — occurs when a researcher tests multiple outcomes, multiple subgroups, or multiple time points and reports only the ones that reached p &lt; 0.05. If you test 20 outcomes, you would expect one to reach significance by chance alone (at alpha = 0.05). Reporting that one outcome as a "finding" without disclosing the other 19 tests is a form of scientific misconduct.

In Ayurveda dissertations, post-hoc outcome selection — choosing the primary outcome based on which variable showed significance — is extremely common. It is not always deliberate. But it is always a distortion of the evidence.

**In Ayurveda Research, This Means:** A table full of p &lt; 0.05 values is not evidence of efficacy. It is a question — how were these outcomes selected, and were they specified before data collection began?

**Section 7: Confidence Intervals — More Honest Than p-values**

If the p-value tells you whether an effect is likely to be real, the confidence interval tells you how large it probably is and how precisely you have estimated it.

**What a confidence interval is**

A 95% confidence interval is a range of values constructed so that, if you repeated your study 100 times under identical conditions, 95 of the 100 intervals you constructed would contain the true population parameter.

It is not quite correct to say "there is a 95% probability that the true value lies in this interval" — the true value is fixed; it is the interval that varies across repeated studies. But for practical purposes, interpreting a 95% CI as the plausible range for the true effect is a reasonable working understanding.

**Reading a confidence interval**

Suppose you conduct a study and find that your intervention reduces fasting blood glucose by a mean of 18 mg/dL, with a 95% CI of 6 to 30 mg/dL.

This tells you:

- The best estimate of the true effect is 18 mg/dL
- The effect is almost certainly real (the interval does not include zero)
- But there is considerable uncertainty — the true effect could be as small as 6 or as large as 30

Now suppose the 95% CI was 16 to 20 mg/dL. The effect is still approximately 18 mg/dL, but your estimate is now highly precise. You can be confident the true effect is close to 18.

**The CI and the line of no effect**

For a difference between groups, the line of no effect is zero. If the 95% CI includes zero (e.g., −3 to 21 mg/dL), the result is not statistically significant at the 0.05 level — zero is a plausible value for the true effect.

For a ratio measure (like relative risk or odds ratio), the line of no effect is 1. A 95% CI for an odds ratio of 0.6 to 1.4 includes 1 — not significant.

**Why CIs are superior to p-values alone**

A p-value gives you a binary answer: significant or not significant. A CI gives you a range — the full picture of uncertainty. Two studies can both produce p = 0.04, but one might have a CI of 1 to 35 (wide, imprecise, unreliable) and another a CI of 15 to 21 (narrow, precise, reliable). The p-value alone conceals this difference entirely.

**In Plain Language:** Always report confidence intervals alongside p-values and effect sizes. A result without a CI is like a map without a scale — you know a direction, but not how far you are from the destination.

**The Foundation Is Set — Now the Work Begins**

You have just covered the conceptual core of biostatistics as it applies to Ayurveda research.

You now understand what a variable is — and why confounders matter so much in studies that cannot be blinded. You can distinguish between nominal, ordinal, interval, and ratio data — and you understand why getting this classification wrong at the design stage corrupts every statistical step that follows. You know the difference between a mean and a median, and when each is the honest choice. You understand the logic of hypothesis testing — the presumption of the null, the threshold of evidence, the meaning of rejection and non-rejection. You have sat with the p-value long enough to understand both what it tells you and the significant list of things it does not. And you now understand why the confidence interval is a more complete and more honest way to report a result than a p-value alone.

This is not a small thing. Most Ayurveda PG scholars complete their dissertations without a working understanding of any of it.

But understanding concepts is only the first half of research literacy. The second half is application — knowing which test to use, how many patients you actually need, how to read the output your software generates, and how to navigate the specific methodological challenges that Ayurveda research faces that no generic textbook addresses.

That is what Part 2 covers.

**Part 2 — Sections 8 to 12 — is available here:** *[Insert Part 2 link on publication]*

It covers:

- A complete decision framework for choosing the right statistical test
- Sample size calculation and the statistical case against the 30-patient norm
- Correlation, regression, and the causation trap
- Reading and reporting SPSS output correctly
- Ayurveda-specific statistical challenges: Kappa reliability, composite symptom scores, Prakriti measurement, multiplicity, and repeated measures designs for Panchakarma studies

Do not stop here. The foundation you have built in Part 1 is only useful if you build on it.

*Ayurveda Unfiltered is a forum for critical engagement with Ayurvedic education, practice, and research. Articles are posted on this blog every week. A companion WhatsApp discussion community engages with each article through structured weekend conversations. If you would like to join the discussion, reach out through the blog.*

*© 2026 Astanga Wellness Pvt. Ltd. All rights reserved.*

---

*Share your thoughts in the comments below.*
