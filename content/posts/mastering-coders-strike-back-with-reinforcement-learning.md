---
title: "Mastering Coders Strike Back With Reinforcement Learning"
date: 2019-03-30T15:15:16+01:00
draft: false
toc: false
images:
tags: 
  - untagged
---

# Coders Strike Back
Coders Strike Back is a popular AI programming challenge on [codingame.com](https://www.codingame.com/). Players write an AI that is able to steer a pair of pods through a few waypoints in order to win a race against another player. Here's what it looks like:

{{< youtube nKgkD3ar2PM >}}

The contest is organized using a league scheme: players start at a lower league with simplified rules: only one pod, no collisions, etc. More rules are added as the player progresses through the contest. In order to climb to a harder league, a player has to beat the "boss", a well-calibrated AI that allows gauging players' progress.

Most players manually define a few heuristics that allow their pods to play a decent game: slow down before waypoints, steer towards the next waypoint, etc. The most advanced players tend to use search algorithms such as minimax to optimize their steering.

While this strategy works very well, couldn't we do better and let the computer learn a good strategy all by itself? Such is the goal of [Reinforcement Learning](https://en.wikipedia.org/wiki/Reinforcement_learning) (RL), a branch of machine learning that aims at learning agent behaviors.

# Reinforcement Learning

sutton, backgammon
go, chess, starcraft

deepmind humanoid video

## Ray's rllib
Setting up a good environment for reinforcement learning is no easy task. Succesful learning frequently requires millions of simulated games. In order to iterate quickly, it's important to have access to a setup that allows many games in parallel, while the agent is updated regularly using the RL algorithm of choice.

After some experimentation, and [a useful thread on reddit](https://old.reddit.com/r/MachineLearning/comments/axmbc6/d_what_librariesframeworks_do_you_use_for_casual/), I settled on [Ray's RLLib](https://ray.readthedocs.io/en/latest/rllib-training.html). Rllib is a very nice library that handles distributed simulations and centralized updates to the agent. It's very easy to get started, implements a lot of the modern RL algorithms, and scales all the way up to multiple GPUs and even computers.

# Starting simple
From painful past experiences, I knew that in RL, it's best to start simple, ensure that everything works, and add complexity gradually. Coders Strike Back is great in this respect: the initial wood league have only one pod and no collisions. In order to make things even simpler, I handled the steering automatically (always towards the next waypoint, a safe but suboptimal strategy) and only let the agent handle thrust. I also limited observations to the distance to the next waypoint.

# Adding boost

# Adding observations and actions

# What didn't work

# Conclusion

