---
layout: post
title: "March Mania 2025 competition - my entry"
date: 2025-02-14
---


# The evaluation method

The Brier score is a metric used to assess the accuracy of probabilistic predictions. It's particularly helpful when predicting binary events (events that have two possible outcomes, like "yes/no," "true/false," or "win/lose"). The Brier score compares the predicted probability of an event to the actual outcome, offering a way to quantify how well the model's probability estimates match the real-world outcomes.

Formula:
For a set of 
𝑁
N predictions, the Brier score is calculated as:

Brier Score
=
1
𝑁
∑
𝑖
=
1
𝑁
(
𝑝
𝑖
−
𝑜
𝑖
)
2
Brier Score= 
N
1
​
  
i=1
∑
N
​
 (p 
i
​
 −o 
i
​
 ) 
2
 
Where:

𝑝
𝑖
p 
i
​
  is the predicted probability of the 
𝑖
i-th event.
𝑜
𝑖
o 
i
​
  is the actual outcome of the 
𝑖
i-th event (1 if the event occurs, 0 if it doesn't).
𝑁
N is the number of predictions.
