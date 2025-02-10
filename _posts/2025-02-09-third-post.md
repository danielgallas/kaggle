---
layout: post
title: "My Draft Post"
date: 2025-02-09
---


The competition [I will look at is Child Mind Institute — Problematic Internet Use](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use).

The first place solution is by [Lennart Haupts](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use/leaderboard)

# The problem

It is a basic classification problem. Based on a number of features, one must predict the level of problematic internet usage exhibited by children and adolescents, based on their physical activity. The goal of this competition is to predict from this data a participant's Severity Impairment Index (sii), a standard measure of problematic internet use. Sii has four categories: 0 for None, 1 for Mild, 2 for Moderate, and 3 for Severe.

The submission file will be a table with two columns: user ID and his or her sii.

The evaluation method is: [quadratic weighted kappa](https://www.kaggle.com/code/aroraaman/quadratic-kappa-metric-explained-in-5-simple-steps), which measures the agreement between two ratings. This metric typically varies from 0 (random agreement between raters) to 1 (complete agreement between raters).

