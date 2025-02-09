---
layout: post
title: "My Draft Post"
date: 2025-02-09
categories: [blog]
published: true
---

The competition [I will look at is Child Mind Institute — Problematic Internet Use](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use).

The first place solution is by [Lennart Haupts](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use/leaderboard)

The evaluation method is: [quadratic weighted kappa](https://www.kaggle.com/code/aroraaman/quadratic-kappa-metric-explained-in-5-simple-steps), which measures the agreement between two ratings. This metric typically varies from 0 (random agreement between raters) to 1 (complete agreement between raters).

### Quadratic Weighted Kappa (QWK)

The **Quadratic Weighted Kappa (QWK)** is a metric used to measure the agreement between two raters, accounting for the ordinal nature of the ratings.

The formula for QWK is:

$$
\kappa = 1 - \frac{\sum_{i,j} W_{i,j} O_{i,j}}{\sum_{i,j} W_{i,j} E_{i,j}}
$$

Where:

- \( O_{i,j} \) is the observed agreement matrix.
- \( E_{i,j} \) is the expected agreement matrix (agreement by chance).
- \( W_{i,j} \) is the quadratic weight, given by:

$$
W_{i,j} = \frac{(i - j)^2}{(N - 1)^2}
$$

Where:
- \( i \) and \( j \) are the rating indices.
- \( N \) is the number of possible ratings.

#### Interpretation:

- \( \kappa = 1 \): Perfect agreement.
- \( \kappa = 0 \): Agreement is no better than chance.
- \( \kappa < 0 \): Worse than random agreement.

This metric is particularly useful for tasks involving ordinal data such as grading or scoring scales.

