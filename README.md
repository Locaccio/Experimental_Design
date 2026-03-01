# Experimental Design and Data Analysis - RStudio Projects

This repository contains a series of statistical analysis projects implemented in **R / RStudio**, covering core concepts in experimental design and data analysis — from basic frequency comparisons to complex mixed factorial ANOVA models with random effects.

> **Course:** Experimental Design, Data Analysis and Presentation
> **Author:** Berkin Beleroglu

---

## Table of Contents

| # | Project | File | Format | Dataset |
|---|---------|------|--------|---------|
| **1** | [Comparing Frequencies](#project-1-comparing-frequencies) | [ExpDes_Pract_1.pdf](./ExpDes_Pract_1.pdf) | 📄 PDF | `Newts.txt`, `Newts2.txt` |
| **2** | [Comparing Means](#project-2-comparing-means) | [ExpDes_Pract_2.html](./ExpDes_Pract_2.html) | 🌐 HTML | `Cockoo.txt` |
| **3** | [Simple ANOVA](#project-3-simple-anova) | [ExpDes_Pract_3.docx](./ExpDes_Pract_3.docx) | 📝 DOCX | `flies.txt` |
| **4** | [Regression Line](#project-4-regression-line) | [ExpDes_Pract_4.docx](./ExpDes_Pract_4.docx) | 📝 DOCX | `rodents.txt` |
| **5** | [Factorial ANOVA](#project-5-factorial-anova) | [ExpDes_Pract_5.docx](./ExpDes_Pract_5.docx) | 📝 DOCX | `metals.txt` |
| **6** | [Hierarchical & Mixed Factorial ANOVA](#project-6-hierarchical-and-mixed-factorial-anova) | [ExpDes_Pract_6.docx](./ExpDes_Pract_6.docx) | 📝 DOCX | `Voles_BMR.txt` |

---

## Project 1: Comparing Frequencies

**File:** [ExpDes_Pract_1.pdf](./ExpDes_Pract_1.pdf) · **Dataset:** `Newts.txt`, `Newts2.txt`

Tests whether categorical frequency distributions match expected proportions and whether two groups differ in their sex ratio.

**Biological context:** Sex ratio analysis of newt populations — comparing observed female proportions against an expected 1:1 ratio, and testing whether the sex ratio differs between a large and a small pond.

**Methods covered:**
- Goodness-of-fit test using `prop.test()` and `chisq.test()` (one-sample)
- Test of independence (two-sample) using contingency tables
- Manual construction of frequency tables via `table()`
- Multiple equivalent approaches: manual vectors, matrix input, and raw data vectors
- Checking chi-square assumptions (expected cell counts ≥ 5)

**Key result:** No significant deviation from 1:1 sex ratio overall (p = 0.134), but a significant difference between ponds (χ² = 4.64, p = 0.031) — females were proportionally more common in the small pond.

---

## Project 2: Comparing Means

**File:** [ExpDes_Pract_2.html](./ExpDes_Pract_2.html) · **Dataset:** `Cockoo.txt`

Compares mean measurements between two independent groups using t-tests with full assumption checking.

**Biological context:** Comparison of egg length between two cuckoo species (*M. a.* and *T. t.*) to determine whether egg size differs significantly between species.

**Methods covered:**
- Independent two-sample t-test (`t.test()`)
- Normality assessment: histograms, QQ-plots, Shapiro-Wilk test
- Homogeneity of variances: `var.test()`
- Descriptive statistics by group using `dplyr`
- Custom plotting function for mean ± SE and 95% CI
- Visualization with `ggplot2` and `ggpubr`

**Packages:** `tidyverse`, `ggplot2`, `ggpubr`

---

## Project 3: Simple ANOVA

**File:** [ExpDes_Pract_3.docx](./ExpDes_Pract_3.docx) · **Dataset:** `flies.txt`

One-way ANOVA investigating whether a response variable differs across five treatment groups, including data transformation and post-hoc testing.

**Biological context:** Effect of silver nanoparticle (AgNP) shape (cubic, triangular, semi-spherical, rod, wire-like) on lifespan of male *Drosophila* — testing whether nanoparticle shape causes significantly different toxicity.

**Methods covered:**
- One-way ANOVA using `aov()`
- Residual diagnostics: histogram of residuals, QQ-plot, `shapiro.test()`
- Homogeneity of variance: `leveneTest()` from the `car` package
- Log transformation to meet ANOVA assumptions, with re-checked diagnostics
- Post-hoc comparisons (Tukey HSD) following a significant result
- Descriptive statistics table and boxplot with jittered data points

**Key result:** Large variance across groups (cubic mean = 6.93 days vs. wire-like mean = 40.6 days); log transformation was required before valid inference.

**Packages:** `tidyverse`, `ggplot2`, `car`

---

## Project 4: Regression Line

**File:** [ExpDes_Pract_4.docx](./ExpDes_Pract_4.docx) · **Dataset:** `rodents.txt`

Simple and allometric linear regression examining metabolic scaling in rodents, including testing the slope against pre-defined theoretical values.

**Biological context:** Testing the allometric relationship between resting metabolic rate (RMR) and body mass (M) across 114 rodent species — evaluating whether the slope follows the *Metabolic Theory of Ecology* (b = 3/4) or the classical *law of area* (b = 2/3).

**Methods covered:**
- Simple linear regression on raw and log₁₀-transformed data (`lm()`)
- Allometric analysis using power functions linearised via log transformation
- Testing slope against pre-defined values (H₀: b = 0.75 and H₀: b = 0.67)
- Full regression diagnostics: residual plots, QQ-plots, influence measures
- Scatterplots on raw and log scale with fitted regression line (`geom_smooth()`)
- Descriptive statistics for both predictor and response variables

**Packages:** `tidyverse`, `ggplot2`, `scatterplot3d`

---

## Project 5: Factorial ANOVA

**File:** [ExpDes_Pract_5.docx](./ExpDes_Pract_5.docx) · **Dataset:** `metals.txt`

Two-way factorial ANOVA with interaction, examining the joint and interactive effects of two factors on a continuous response variable.

**Biological context:** Toxic effects of copper (Cu) and zinc (Zn) on mouse growth rate — mice were randomly assigned to four dietary groups (control, Cu only, Zn only, Cu+Zn) to test for main effects and their interaction.

**Methods covered:**
- Two-way ANOVA with interaction term (`aov()` with `Cu * Zn`)
- Computing a derived response variable: growth rate G = (M₃₅ − M₂₀) / 15 days
- Type III sums of squares using `car::Anova()`
- Interaction plots using `effects` and `emmeans`
- Post-hoc pairwise comparisons with estimated marginal means (`emmeans()`)
- Levene's test for homogeneity of variance across factorial groups
- Descriptive statistics by group combination

**Packages:** `tidyverse`, `ggplot2`, `car`, `effects`, `emmeans`

---

## Project 6: Hierarchical and Mixed Factorial ANOVA

**File:** [ExpDes_Pract_6.docx](./ExpDes_Pract_6.docx) · **Dataset:** `Voles_BMR.txt`

Advanced ANOVA designs with random effects, including one-level and two-level nested models, mixed factorial models, and split-plot designs.

**Biological context:** Basal metabolic rate (BMR) in bank voles (*Myodes glareolus*) from a long-term artificial selection experiment — four selection directions (Aerobic, Herbivorous, Predatory, Control), each with 4 replicate lines and multiple families per line, with both sexes measured. The central question is whether selection for aerobic capacity elevated BMR.

**Methods covered:**
- One-level nested ANOVA: replicate lines nested within selection type using `aov()` with `Error()`
- Two-level nested ANOVA: families nested within lines, lines within types using `lmer()`
- Mixed factorial model: fixed effects (selection type, sex) + random effect (replicate line)
- Split-plot (cross-nested) design: selection × sex interaction with random line effects
- Comparison of `aov()` vs. `lmer()` outputs and when each gives misleading results
- Likelihood ratio tests for random effects significance
- Estimated marginal means and interaction plots for final conclusions

**Packages:** `tidyverse`, `lme4`, `lmerTest`, `effects`, `emmeans`, `car`

---

## Packages Used Across Projects

```r
library(tidyverse)     # Data manipulation and visualization
library(ggplot2)       # Plotting
library(ggpubr)        # Publication-ready plots
library(car)           # Levene's test, Type III SS
library(lme4)          # Linear mixed-effects models
library(lmerTest)      # p-values for lmer() models
library(effects)       # Effect displays
library(emmeans)       # Estimated marginal means & post-hoc tests
library(scatterplot3d) # 3D scatter plots
```

---

## Repository Structure

```
├── ExpDes_Pract_1.pdf          # Project 1 – Comparing Frequencies (Newts)
├── ExpDes_Pract_2.html         # Project 2 – Comparing Means (Cuckoo eggs)
├── ExpDes_Pract_3.docx         # Project 3 – Simple ANOVA (Drosophila lifespan)
├── ExpDes_Pract_4.docx         # Project 4 – Regression Line (Rodent metabolic rate)
├── ExpDes_Pract_5.docx         # Project 5 – Factorial ANOVA (Cu/Zn toxicity in mice)
├── ExpDes_Pract_6.docx         # Project 6 – Hierarchical & Mixed ANOVA (Vole BMR)
└── README.md
```

---

## References

- Field, A. (2013). *Discovering Statistics Using IBM SPSS Statistics*. SAGE Publications.
- Navarro, D. (2019). *Learning Statistics with R*. https://learningstatisticswithr.com
- R Core Team (2023). *R: A Language and Environment for Statistical Computing*. https://www.r-project.org
- Bates, D. et al. (2015). Fitting Linear Mixed-Effects Models Using lme4. *Journal of Statistical Software*, 67(1).
