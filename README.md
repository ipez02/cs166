# Space Invaders DQN Exploration

This project adapts the starter DQN Pong notebook to a new Atari domain: **Space Invaders**.  
Using Gymnasium’s ALE environments, I trained a DQN agent briefly to see how behavior changes from early random play to later, more structured strategies.  

---

## 🎥 Gameplay Videos

### Early Training (near-random behavior)
<video src="videos/spaceinvaders_early-episode-0.mp4" controls width="480"></video>

### Later Training (emerging strategy)
<video src="videos/apaceinvaders_later-episode-0.mp4" controls width="480"></video>

---

## ✍️ Reflection

I chose **Space Invaders** because it offers a more dynamic challenge than Pong — the agent must learn not only to shoot descending aliens but also to dodge incoming fire. This makes the environment more complex, balancing offense with survival, and rewards are less frequent than in Pong. I was interested to see how a DQN could start to discover these patterns even within a short training run.

In the **early training video**, the agent’s behavior was nearly random. It moved back and forth with little purpose, sometimes firing but rarely hitting targets. The gameplay looked chaotic, with little evidence of strategy, which is expected at the start since the replay buffer and Q-values were still being initialized. Rewards were sparse and mostly due to accidental hits.

By the **later training video**, I noticed emerging patterns: the agent fired more consistently toward the alien formations and positioned itself better to line up shots. While it was still far from optimal, this showed that the DQN was beginning to associate actions (like moving into alignment before firing) with rewards. The difference between the two videos demonstrates clear learning progress.

The main challenges were **sparse rewards and partial observability**. Space Invaders punishes mistakes quickly (getting hit), and rewards can be delayed until a shot actually lands. If I continued training, I would tune hyperparameters such as the epsilon-greedy schedule (to balance exploration vs. exploitation), increase the replay buffer size, and possibly stack more frames to capture movement better. I’d also consider reward clipping and adjusting the learning rate to stabilize training further.

---

## 📂 Repo Structure

