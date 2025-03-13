# Project Description

## Summary

Cookie Cats is a popular mobile puzzle game where players match tiles to clear levels.

As players progress, they sometimes hit gates that require them to wait or make a purchase to continue. These gates are meant to encourage breaks and increase enjoyment.

The first gate was originally at level 30, but in this test, we moved it to level 40. We’ll now look at how this change affects all metrics. Let’s check it out!

## Data Description:

The data comes from 90,189 players who installed the game during the A/B test. The variables are:

- userid: A unique ID for each player.

- version: Whether the player was in the control group (gate_30) or test group (gate_40)

- sum_gamerounds: The number of rounds played in the first week.

- retention_1: Whether the player returned 1 day after installation.

- retention_7: Whether the player returned 7 days after installation.

- Players were randomly assigned to either gate_30 or gate_40 when they installed the game.

## A/B Testing Evaluate
Metric Game_rounds : Mann-Whitney

Metric %Retention_1 : Chi-Square

Metric %Retention_7 : Chi-Square

## Conclusion
**Business Problem Recap:**

In Cookie Cats, players face gates that make them wait before progressing or making an in-app purchase. We analyzed an A/B test where the first gate was moved from level 30 to level 40, focusing on player retention and game rounds.

**Key Findings:**

- The Mann-Whitney U test showed no difference in game rounds between gate_30 and gate_40.
- The Chi-Square test found no difference in 1-day retention, but 7-day retention for gate_40 was lower (14.92%) compared to gate_30 (15.76%).

**Conclusion:**

The gate change didn’t impact game rounds or 1-day retention, but 7-day retention decreased. Therefore, we recommend keeping the old version (gate_30). Other factors, like game experience and rewards, should also be considered.



