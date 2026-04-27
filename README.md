---
title: "DATA 555 Final Project"
output: github_document
---

## Overview

This dashboard displays select results from my masters thesis titled "Evaluating the Reactogenicity-Immunogenicity Relationship Among Pandemic Influenza Vaccines."

## Data 

Data on 12 mix-and-match clinical trials for pandemic influenza vaccines was obtained from the National Institute on Allergy and Infectious Diseases. All studies were conducted at Vaccine Treatment and Evaluation Unit network locations and took place between 2009 and 2020. Participants were healthy, non-pregnant, immuno-competent adults, with specific age ranges varying by study.

## Analysis 

Spearman's rank correlation coefficient was used to evaluate bivariable relationships between reactogenicity and immunogenicity. A one-stage individual participant data (IPD) meta-regression model was used to evaluate the relationship between reactogenicity and immunogenicity, adjusting for covariates. Analyses were conducted in R (v4.5.1) using lme4 for mixed-effects models.

Note: Bivariable analysis was performed using all 12 studies. One study (09-0058) was excluded from the IPD meta-regression model because it was the only study evaluating the H1N1 strain, and it would've been impossible to differentiate between study and strain effects.

### Model Components: 

-   Fixed effects

    -   Age group (18-30, 31-40, 41-50, 51-64, 65+ years)

    -   Sex (M/F)

    -   Strain (H5N1, H5N8, H7N9)

    -   Dosage/Adjuvant

        -   Dosage: Low (3.75mcg per dose), Medium (7.5mcg per dose), High (15mcg+ per dose)

        -   Adjuvant: Unadjuvanted, AS03 for all, MF59 for all, AS03 for dose 1 then unadjuvanted for dose 2, unadjuvanted for dose 1 then AS03 for dose 2, MF59 for dose 1 then unadjuvanted for dose 2, unadjuvanted for dose 1 then MF59 for dose 2, AS03 for dose 1 then MF59 for dose 2, MF59 for dose 1 then AS03 for dose 2

        -   16 combinations of these were present in the data

    -   Strain\*Dosage/Adjuvant interaction term

-   Random effects

    -   Random intercept for study (to allow for variation in baseline immunogenicity by study)

    -   Random slope for reactogenicity (to allow for variation in reactogenicity-immunogenicity relationship by study)

## Real-World Impact 

Understanding the reactogenicity-immunogenicity relationship could improve public health communication by giving meaning to the adverse events that people experience after receiving a vaccination. Additionally, developing reliable predictive frameworks that integrate clinical and immunologic markers could improve early evaluation of vaccine candidates and inform more efficient trial designs.
