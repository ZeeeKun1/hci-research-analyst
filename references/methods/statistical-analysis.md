# Statistical Analysis for HCI Research

## Overview

Guide for analyzing quantitative data in HCI user studies. Covers common statistical methods with emphasis on appropriate application, effect size reporting, and common pitfalls. Follows APA 7th edition and HCI publication norms.

## Analysis Workflow

### 1. Data Preparation
- Clean data: handle missing values, outliers, impossible values.
- Check assumptions BEFORE choosing tests (normality, homogeneity of variance, sphericity).
- Compute descriptive statistics for all variables (mean, SD, median, IQR, range).
- Visualize distributions (histograms, box plots) before inferential tests.

### 2. Choosing the Right Test

**Comparing two groups:**
| Condition | Test | Effect Size |
|-----------|------|-------------|
| Normal, independent | Independent t-test | Cohen's d |
| Non-normal, independent | Mann-Whitney U | Rank-biserial r |
| Normal, paired | Paired t-test | Cohen's d |
| Non-normal, paired | Wilcoxon signed-rank | Rank-biserial r |
| Categorical | Chi-square / Fisher's exact | Cramér's V |

**Comparing 3+ groups:**
| Condition | Test | Effect Size |
|-----------|------|-------------|
| Normal, independent | One-way ANOVA | η² (eta-squared) |
| Normal, repeated | Repeated-measures ANOVA | η² |
| Non-normal | Kruskal-Wallis | ε² (epsilon-squared) |
| Categorical | Chi-square test of independence | Cramér's V |

**Relationships between variables:**
| Goal | Test | Effect Size |
|------|------|-------------|
| Linear relationship | Pearson correlation | r |
| Monotonic, non-normal | Spearman correlation | ρ (rho) |
| Predicting outcome | Multiple regression | R², standardized β |
| Group prediction | Logistic regression | Odds ratio |
| Latent constructs | Factor analysis / SEM | Factor loadings, CFI/TLI/RMSEA |

**Repeated measures / longitudinal:**
| Design | Test | Notes |
|--------|------|-------|
| Within-subjects | RM-ANOVA | Check Mauchly's test; use Greenhouse-Geisser correction |
| Mixed design | Mixed ANOVA | Between × Within interaction |
| Longitudinal | Linear mixed-effects model | Handles missing data, varying time points |

### 3. Assumption Checking

Always report assumption checks:
- **Normality**: Shapiro-Wilk test (n < 50); visual inspection of Q-Q plot
- **Homogeneity of variance**: Levene's test; if violated, use Welch's correction
- **Sphericity**: Mauchly's test; if violated, apply Greenhouse-Geisser or Huynh-Feldt correction
- **Linearity**: Scatterplot inspection for correlation/regression
- **Multicollinearity**: VIF < 5 (ideally < 3) for regression

### 4. Reporting Standards

**Always report:**
- Descriptive statistics (M, SD or median, IQR)
- Test statistic (t, F, U, χ², etc.) with degrees of freedom
- Exact p-value (not just p < .05), or note if non-significant
- Effect size with 95% confidence interval
- Direction of effect
- Sample size per condition

**Example (APA format):**
> Participants in the gesture condition (M = 4.32, SD = 0.87) reported higher usability than those in the mouse condition (M = 3.58, SD = 1.02), t(46) = 2.89, p = .006, d = 0.79, 95% CI [0.22, 1.35].

### 5. Bayesian Considerations (Optional but Increasingly Expected)

When sample sizes are small (common in HCI):
- Consider Bayesian t-test / ANOVA as complement to frequentist tests.
- Report Bayes Factor (BF₁₀) alongside p-values.
- BF₁₀ > 3: moderate evidence for H₁; BF₁₀ > 10: strong evidence.
- BF₁₀ < 1/3: moderate evidence for H₀.

## Common Pitfalls in HCI

| Pitfall | Problem | Solution |
|---------|---------|----------|
| p-hacking | Running multiple tests without correction | Pre-register hypotheses; use Bonferroni/FDR correction |
| Ignoring effect sizes | Significant p with tiny effect | Always report and interpret effect sizes |
| Small samples | Low power; unstable estimates | Report confidence intervals; consider Bayesian analysis |
| Normality assumption | HCI data is often non-normal | Check assumptions; use non-parametric alternatives |
| Ordinal data treated as interval | Likert scales are ordinal | Use non-parametric tests or ordinal regression |
| Ignoring violations | Running ANOVA when assumptions violated | Check first; apply corrections or alternative tests |

## HCI-Specific Considerations

- **Likert scales**: Debate continues on whether to treat as interval. Conservative approach: non-parametric for small n; parametric with caveat for large n (>30 per group).
- **Learning effects**: Within-subjects designs need counterbalancing; check for order effects.
- **Within-subjects is king**: Most HCI studies use within-subjects designs (more power, less noise). Account for this in analysis.
- **System usability scales**: SUS, NASA-TLX, etc. have established scoring procedures — follow them exactly.

## Tools & Scripts

When implementing in code:
- Python: scipy.stats, statsmodels, pingouin
- R: stats, lme4, BayesFactor, rstatix
- Report all analysis code for reproducibility.

## Foundational Citations

- Cohen, J. (1988). *Statistical Power Analysis for the Behavioral Sciences* (2nd ed.). Routledge.
- Cumming, G. (2014). *Understanding the New Statistics: Effect Sizes, Confidence Intervals, and Meta-Analysis*. Routledge.
- Kaptein, M., & Robertson, T. (2012). Rethinking statistical analysis methods for CHI. *Proceedings of CHI '12*, 1105-1114.
- Larson, R., & Haller, M. (2019). Statistical significance in HCI research. *Interactions*, 26(3), 64-66.
