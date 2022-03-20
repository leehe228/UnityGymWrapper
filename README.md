# UnityGymWrapper
OpenAI Gym style Wrapper for Multi-agent environment which made by Unity ML-Agents

This wrapper is used in [Logistics Environment (for MARL)](https://github.com/dmslab-konkuk/LogisticsEnv)

**You can use this wrapper to wrap user algorithm to make OpenAI gym style like this,**
```python
from UnityGymWrapper5 import GymEnv

env = GymEnv(...)

obs = env.reset()
next_obs, rewards, done, info = env.step(actions)
```

This wrapper file **detect information of your ML-Agent environment automately** (number of agents, state of each agents, number of actions etc...)
