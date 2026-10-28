# Replicating a NewsGuard Source-Label Experiment, with a Trolling Extension

Group project for *Statistics II: Statistical Modeling and Causal Inference with R* (Hertie School, spring 2024). Completed with two co-authors: [Co-author 1] and [Co-author 2].

## What this project is

We replicated and checked the analysis of Aslett, Guess, Bonneau, Nagler and Tucker (2022), a randomised field experiment testing whether in-feed source-reliability labels (the NewsGuard browser extension) change news consumption, trust in media and political attitudes.

Original paper: Aslett, K., Guess, A. M., Bonneau, R., Nagler, J., & Tucker, J. A. (2022). News credibility labels have limited average effects on news diet quality and fail to reduce misperceptions. *Science Advances*. https://doi.org/10.1126/sciadv.abl3844

Original replication code and data: https://github.com/SMAPPNYU/Labels_Have_Limited_Effects

## My contribution

- Wrote the paper-summary sections on causal identification challenges and on the authors' research design.
- Re-ran, checked and adapted the authors' replication code in R for the figure replication: [data cleaning, merging survey waves with browsing data, instrumental-variable estimates, power calculations].
- Proposed the trolling extension in the group's brainstorm and developed it: (wrote the hypothesis, built the causal diagram, ran the regression].

My co-authors wrote the remaining sections of the report. The data and the base code come from the original authors and the course.

## Methods used

- R and R Markdown
- Merging survey waves with digital browsing data
- Intent-to-treat and complier effects using instrumental variables
- Power and minimum-detectable-effect calculations
- Covariate selection with lasso
- Effect plots by decile of prior news-source reliability
- Logistic regression for the extension

## Extension: does trolling predict exposure to unreliable news?

Hypothesis: people who report frequent trolling would deliberately visit unreliable news sources, so unreliable content would sit higher in their feeds and search results. If so, exposure to unreliable news would not necessarily mean belief in it.

Method: logistic regression on second-wave survey data, with self-reported trolling frequency as the predictor and age (birth year), gender and education as controls.

Result: for the highest trolling frequency ("most of the time"), the coefficient was 0.59 on the log-odds scale, and it was not statistically significant. The data therefore do not clearly support the hypothesis. This does not show the hypothesis is false: the sample may be too small or the measures too coarse.

## Limitations

- Exposure to the labels could not be observed directly.
- The experiment did not allow for changes over time, such as elections or wars.
- The extension is exploratory, based on self-reported trolling and a single survey wave.

## Data and code

This repository does not include the data. The data and base code come from the original authors' replication materials (link above) and the course. To reproduce the analysis, download the original materials, place them in a folder called `data`, and knit `Final Replication Upload.Rmd`. The required packages include tidyverse, AER, glmnet, estimatr, huxtable, texreg, ivpack, ggplot2, ggdag and modelsummary.

## Credits

Original study: Aslett et al. (2022). Course: Statistics II, Hertie School. Co-authors.
