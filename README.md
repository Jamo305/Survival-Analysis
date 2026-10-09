# Survival Analysis: Treatment Effect on Time-to-Event Outcomes

A survival analysis of a 200-patient dataset, comparing a new treatment with standard care using Kaplan-Meier curves and Cox proportional hazards models. Written in R Markdown as part of coursework in Applied Statistics with Computing at Moi University.

## Repository contents

| File | Description |
|---|---|
| `SURV_James_Odhiambo.Rmd` | R Markdown source: all code, analysis, and written interpretation |
| `SURV_analysis.pdf` | Knitted report (PDF) |
| `survival_data_group1.csv` | Dataset used in the analysis (200 patients) |

## Data

Each row is one patient.

| Variable | Description |
|---|---|
| `id` | Patient identifier |
| `time` | Follow-up time (months) |
| `status` | Event indicator (1 = event occurred, 0 = censored) |
| `age` | Age in years |
| `sex` | 0 = Female, 1 = Male |
| `treatment` | 0 = Standard care, 1 = New treatment |
| `comorbidity` | Number of comorbid conditions |

The dataset was provided for coursework. It contains no names or other direct identifiers.

## Analysis overview

**Section A: Data exploration**
- Summary statistics for all variables
- Survival time by treatment group
- Kaplan-Meier curves by treatment group and by sex, with risk tables and log-rank p-values

**Section B: Model fitting**
- Cox proportional hazards model with treatment, age, and sex (Model 1)
- Hazard ratio interpretation and a proportional hazards assumption check (`cox.zph`)
- Extended model adding comorbidity (Model 2), compared with Model 1 using AIC and log-likelihood

**Section C: Application and interpretation**
- Estimated 12-month survival probability for two example patient profiles
- Treatment-by-sex interaction test
- Summary of key findings and implications for patient care

**Section D: Conceptual questions**
- Hazard ratio versus risk ratio
- Censoring and its types, with medical examples

## Tools and packages

R, R Markdown, `survival`, `survminer`, `rms`, `dplyr`

## How to reproduce

1. Clone or download this repository.
2. Open `SURV_James_Odhiambo.Rmd` in RStudio.
3. Install the required packages:
   ```r
   install.packages(c("dplyr", "survival", "survminer", "rms"))
   ```
4. Make sure `survival_data_group1.csv` is in the same folder as the Rmd, and that the `read.csv()` call in the `data_import` chunk points to it (for example `read.csv("survival_data_group1.csv")`).
5. Knit to PDF, HTML, or Word. PDF output needs a LaTeX installation (`tinytex::install_tinytex()`).

## Author

James Odhiambo, Applied Statistics with Computing, Moi University
