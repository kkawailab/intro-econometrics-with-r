# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains practice exercises for "Introduction to Econometrics with R" (https://www.econometrics-with-r.org/). It consists of 16 Jupyter notebooks (R kernel) with 10 problems each, covering econometrics topics from basic R to advanced time series analysis.

## Repository Structure

```
exercises/
├── chapter01_introduction.ipynb      # R basics
├── chapter02_probability_theory.ipynb
├── chapter03_statistics_review.ipynb
├── chapter04_simple_regression.ipynb # OLS fundamentals
├── chapter05-07_*.ipynb              # Hypothesis testing
├── chapter08_nonlinear_regression.ipynb
├── chapter09_assessing_studies.ipynb
├── chapter10_panel_data.ipynb        # Fixed/random effects
├── chapter11_binary_dependent.ipynb  # Probit/Logit
├── chapter12_instrumental_variables.ipynb # 2SLS
├── chapter13_experiments.ipynb       # DID, RDD
├── chapter14-16_*.ipynb              # Time series topics
```

## Notebook Format

Each notebook follows this structure:
1. Chapter title and overview (markdown)
2. Required packages installation/loading (code cell)
3. For each problem (10 per chapter):
   - Problem statement (markdown)
   - Empty answer cell for students
   - "模範解答" (Model Answer) header
   - Solution code cell

## Key R Packages Used

- `AER` - Datasets (CASchools, Fatalities, HMDA, CigarettesW) and ivreg()
- `lmtest`, `sandwich` - Hypothesis testing, robust standard errors
- `plm` - Panel data analysis
- `dynlm` - Dynamic linear models
- `forecast`, `vars` - Time series, VAR models
- `urca`, `tseries` - Unit root tests, cointegration
- `strucchange` - Structural break tests
- `fGarch` - GARCH models

## Running Notebooks

Notebooks require R kernel (IRkernel) in Jupyter. First cell in each notebook handles package installation:
```r
if (!require("package")) install.packages("package")
library(package)
```

## Language

All problem statements, explanations, and comments are in Japanese. Variable names and R code follow standard English conventions.
