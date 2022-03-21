# UnityGymWrapper (Unity ML-Agents to OpenAI Gym Style)
OpenAI Gym style Wrapper for Multi-agent environment which made by Unity ML-Agents.
Unity ML-Agents doesn't support Multi-agent environment officially, so you can use this file to wrap your environment.

This wrapper is used in Github Repository: [Logistics Environment (for MARL)](https://github.com/dmslab-konkuk/LogisticsEnv) and Paper: ["Multi agent reinforcement learning based UAV control for Urban Aerial Mobility logistics"](https://apisat2021.org/) in [APISAT2021](https://apisat2021.org/) Conference.

**You can use this wrapper to wrap user algorithm to make OpenAI gym style like this,**
```python
from UnityGymWrapper5 import GymEnv

env = GymEnv(...)

obs = env.reset()

for _ in steps:
    actions = algorithm(obs)
    
    next_obs, rewards, done, info = env.step(actions)
    
    obs = next_obs
```

This wrapper file **detect information of your ML-Agent environment automately** (number of agents, state of each agents, number of actions etc...)

### Parameters Customation
You can also your customed parameters linked with your environment. You can see an example on this repository: [Logistics Environment (for MARL)](https://github.com/dmslab-konkuk/LogisticsEnv).

You can set default parameter values to change Unity rendering options.
```python

        def __init__(self, 
                 name : str, 
                 width : Optional[int] = 480, 
                 height : Optional[int] = 270, 
                 timescale : Optional[float] = 20,
                 quality_level : Optional[int] = 5,
                 target_frame_rate : Optional[int] = None,
                 capture_frame_rate : Optional[int] = None):
        """
        <Unity Environment Engine Parameters>
        name : path to Unity Environment
        width : Defines the width of the display. (Must be set alongside height)
        height : Defines the height of the display. (Must be set alongside width)
        timescale : Defines the multiplier for the deltatime in the simulation. 
                    If set to a higher value, time will pass faster in the simulation 
                    but the physics may perform unpredictably.
        quality_level : Defines the quality level of the simulation.
        target_frame_rate : Instructs simulation to try to render at a specified frame rate.
        capture_frame_rate : Instructs the simulation to consider time between updates to 
                             always be constant, regardless of the actual frame rate.
        """
```

### Requirements

- Python 3.6 (minimum)
- [OpenAI baselines](https://github.com/openai/baselines), version 0.1.6
- [PyTorch](https://pytorch.org/) (compatible to your CUDA version)
- [Tensorboard](https://github.com/tensorflow/tensorboard) (compatible to PyTorch version)
- [OpenAI Gym](https://github.com/openai/gym), version 0.15.7
- [Unity mlagents](https://github.com/Unity-Technologies/ml-agents), version 0.27.0 (Release 18)
<br>

### Credit
developed by [Hoeun Lee](https://github.com/leehe228) (in [DMS Lab](https://github.com/dmslab-konkuk) in [Dept. of Computer Science and Engineering](http://cse.konkuk.ac.kr/), [Konkuk University](http://www.konkuk.ac.kr/do/Index.do), Seoul, Korea)

Copyright Hoeun Lee, 2021, All Right Reserved. 
