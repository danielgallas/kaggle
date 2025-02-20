---
layout: post
title: "March Mania 2025 competition - my entry"
date: 2025-02-14
---


## Evaluation

The Brier score is a metric used to assess the accuracy of probabilistic predictions. It's particularly helpful when predicting binary events (events that have two possible outcomes, like "yes/no," "true/false," or "win/lose"). The Brier score compares the predicted probability of an event to the actual outcome, offering a way to quantify how well the model's probability estimates match the real-world outcomes.

(Sum of ​(pi​−oi​)^2)/N

Where:

pi ​ is the predicted probability of the i-th event.
oi ​ is the actual outcome of the i-th event (1 if the event occurs, 0 if it doesn’t)
N is the number of predictions

Perfect prediction: A Brier score of 0 means the predicted probabilities were perfect, i.e., the predicted probabilities matched the actual outcomes exactly.
Worse prediction: The higher the Brier score, the worse the predictions. A score of 1 represents the worst possible prediction, meaning the predicted probability was always completely wrong (e.g., predicting 1 when the event didn’t occur).

## Submission fie

Each game has a unique ID created by concatenating the season in which the game was played and the two team's respective TeamIds. For example, "2025_1101_1102" indicates a hypothetical matchup between team 1101 and 1102 in the year 2025. You must predict the probability that the team with the lower TeamId beats the team with the higher TeamId. Note that the men's teams and women's TeamIds do not overlap.

Your 2025 submissions will score 0.0 if you have submitted predictions in the right format. The leaderboard of this competition will be only meaningful once the 2025 tournaments begin and Kaggle rescores your predictions!

The goal of this competition is to predict that probability that the smaller TeamID will win a given matchup.

## Strategies

I can literally drown in all these numbers. The [data tab in the competition](https://www.kaggle.com/competitions/march-machine-learning-mania-2025/data) is insane.

The submission file, however, is very straightforward. All they want are predictions of games - nothing more than that.

I will work my way up. I will start out with a minimal model and minimal inputs that generalize well. I will produce a train model with very few features and then work my way up, adding more features.

Intuitively I believe recent results are what really matter for predicting outcomes. I will prioritise this.

This [starter notebook by Paul Mooney](https://www.kaggle.com/code/paultimothymooney/simple-starter-notebook-for-march-mania-2025/notebook) is very sensible.


## Exploratory Data Analysis:

Here
