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
