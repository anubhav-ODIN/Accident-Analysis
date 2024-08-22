# Accident-Analysis
To create a README file for your project, you can follow this structure, summarizing the key points from your report while making it concise and easy to follow. Here's a draft README:

---

# How a Bayesian Hierarchical Model Makes Our Roads Safer

## Project Overview

This project is a replication and analysis of the model proposed in the paper *"A Novel Bayesian Hierarchical Model for Road Safety Hotspot Prediction"* by Fawcett, Thorpe, Matthews, and Kremer (2017). The aim of the paper is to take proactive road safety measures by predicting the number of accidents at specific sites and ranking them according to their safety hotspot potential. The key innovation of this model is its ability to address the confounding effects of regression-to-the-mean (RTM) and trend.

**Project Aim:**  
The goal of this project is to analyze and replicate the Bayesian Hierarchical Model using historical accident data from the German city of Halle. The model has been successfully replicated as demonstrated in the detailed results section of this report.

## Data

The dataset used in this project consists of accident counts from 734 sites in Halle, covering the years 2004–2012. The year 2012 is kept separate for model validation. For each site, the dataset includes covariates such as traffic volume, speed limits, and urban or non-urban location.

**Data Structure:**  
- Historical Data: 2004-2011  
- Validation Data: 2012  
- Covariates: Traffic volume, speed limit, urban area status, etc.

## Challenges Addressed

1. **Regression to the Mean (RTM):**  
   A recent spike in accidents at a site may result from a significant safety issue or a random fluctuation. If the increase is random, accidents are likely to decrease in the following year regardless of any safety measures, due to RTM. The model effectively differentiates between these scenarios.

2. **Trend Effects:**  
   Decreases in accidents may result from safety measures or broader site-specific or global trends, such as a general reduction in driving speeds. The model accounts for both local and global trends to provide accurate predictions.

## Model Overview

The Bayesian Hierarchical Model uses data from multiple time periods, treating the current time as t=0, with t<0 for the past and t>0 for the future. Accident counts are modeled using Poisson distributions with varying weightings for different years to give more significance to recent data.

- **Before Period (t < 0):** Modeled using a Negative Binomial distribution to handle variability.
- **After Period (t ≥ 0):** Modeled using a Poisson distribution, assuming accidents are independently and identically distributed over time.

The model incorporates random effects to handle RTM and trend effects, with parameters adjusted through MCMC (Markov Chain Monte Carlo) simulations.

## Implementation

The model was implemented using the PyMC3 library in Python, following the approach outlined in the paper. Global accident prediction models were generated, and the final predictions were validated against the actual data from 2012.

**Steps:**
- Data Rearrangement for APM (Accident Prediction Model)
- Fitting the Negative Binomial Model
- Incorporating RTM and trend effects
- Running MCMC for parameter estimation
- Validation and comparison with the original model

## Results

The model successfully replicated the results from the original paper, confirming the effectiveness of the Bayesian Hierarchical approach in predicting road safety hotspots. Detailed comparison tables and charts are available in the report.



