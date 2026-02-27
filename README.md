# Experimental Design and Data Analysis - RStudio Projects

This repository contains a series of statistical analysis projects implemented in **R / RStudio**, covering core concepts in experimental design and data analysis — from basic frequency comparisons to complex mixed factorial ANOVA models.

---

## Table of Contents

| Lab # | Project | Topics Covered |
|-------|---------|----------------|
| **Project 1** | [Comparing Frequencies](#project-1-comparing-frequencies) | Chi-square tests, goodness-of-fit, contingency tables |
| **Project 2** | [Comparing Means](#project-2-comparing-means) | t-tests, independent & paired samples |
| **Project 3** | [Simple ANOVA](#project-3-simple-anova) | One-way ANOVA, post-hoc tests |
| **Project 4** | [Regression Line](#project-4-regression-line) | Simple linear regression, model diagnostics |
| **Project 5** | [Factorial ANOVA](#project-5-factorial-anova) | Two-way ANOVA, interaction effects |
| **Project 6** | [Hierarchical and Mixed Factorial ANOVA](#project-6-hierarchical-and-mixed-factorial-anova) | Nested designs, within/between subject factors |

---

## Project 1: Comparing Frequencies

Explores the analysis of categorical data using frequency-based statistical tests.

- Chi-square goodness-of-fit test
- Chi-square test of independence
- Contingency table analysis
- Effect size (Cramér's V)

---

## Project 2: Comparing Means

Focuses on comparing group means using t-tests for various experimental scenarios.

- One-sample t-test
- Independent samples t-test
- Paired samples t-test
- Assumptions checking (normality, homogeneity of variance)

---

## Project 3: Simple ANOVA

Introduction to Analysis of Variance for comparing means across multiple groups.

- One-way ANOVA
- Post-hoc comparisons (Tukey HSD, Bonferroni)
- ANOVA assumptions and diagnostics
- Effect size (η²)

---

## Project 4: Regression Line

Covers simple linear regression for modeling relationships between variables.

- Fitting a regression line (`lm()`)
- Interpreting slope and intercept
- R² and model fit
- Residual diagnostics and assumption checks

---

## Project 5: Factorial ANOVA

Examines designs with two or more independent variables and their interactions.

- Two-way ANOVA
- Main effects and interaction effects
- Interaction plots
- Post-hoc tests for factorial designs

---

## Project 6: Hierarchical and Mixed Factorial ANOVA

Advanced ANOVA designs involving nested factors and both between- and within-subject variables.

- Hierarchical (nested) ANOVA
- Mixed factorial ANOVA (between + within-subject factors)
- Sphericity assumption and Mauchly's test
- Greenhouse-Geisser and Huynh-Feldt corrections

---

## Tools & Packages

The following R packages are used across projects:

```r
library(tidyverse)   # Data manipulation and visualization
library(ggplot2)     # Plotting
library(car)         # Levene's test, Type III SS
library(rstatix)     # Pipe-friendly statistical tests
library(ez)          # Mixed ANOVA (ezANOVA)
library(emmeans)     # Estimated marginal means & post-hoc tests
library(effectsize)  # Effect size calculations
```

---

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/your-repo-name.git
   ```
2. Open the `.Rproj` file in RStudio.
3. Navigate to the desired project folder and open the corresponding `.R` or `.Rmd` file.
4. Install any required packages using `install.packages("package_name")`.

---

## Repository Structure

```
├── Project1_ComparingFrequencies/
│   ├── project1.R
│   └── data/
├── Project2_ComparingMeans/
│   ├── project2.R
│   └── data/
├── Project3_SimpleANOVA/
│   ├── project3.R
│   └── data/
├── Project4_RegressionLine/
│   ├── project4.R
│   └── data/
├── Project5_FactorialANOVA/
│   ├── project5.R
│   └── data/
├── Project6_HierarchicalMixedANOVA/
│   ├── project6.R
│   └── data/
└── README.md
```

---

## References

- Field, A. (2013). *Discovering Statistics Using IBM SPSS Statistics*. SAGE Publications.
- Navarro, D. (2019). *Learning Statistics with R*. https://learningstatisticswithr.com
- R Core Team (2023). *R: A Language and Environment for Statistical Computing*. https://www.r-project.org
