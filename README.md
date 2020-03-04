# FQF, IQN and QR-DQN in PyTorch

This is a PyTorch implementation of Fully parameterized Quantile Function(FQF)[[1]](#references), Implicit Quantile Networks(IQN)[[2]](#references) and Quantile Regression DQN(QR-DQN)[[3]](#references). I tried to make it easy for readers to understand algorithms. Please let me know if you have any questions.

## Installation
You can install dependencies using `pip install -r requirements.txt`.

## Examples
You can train FQF agent using hyperparameters [here](https://github.com/ku2482/fqf-iqn-qrdqn.pytorch/blob/master/config/fqf.yaml).

```
python train_fqf.py --cuda --env_id PongNoFrameskip-v4 --seed 0 --config config/fqf.yaml
```

You can also train IQN or QR-DQN agent in the same way. Note that we log results with the number of frames, which equals to the number of agent's steps multiplied by 4 (e.g. 100M frames means 25M agent's steps).

## Results
Results of examples (without n-step rewards, double q-learning, dueling network nor noisy net) are shown below, which is comparable (if no better) with the paper. Scores below are evaluated arfer every 1M frames (250k agent's steps). Result are averaged by 2 seeds and visualized with min/max.

Note that I only trained a limited number of frames due to limited resources (e.g. 100M frames instead of 200M).


### BerzerkNoFrameskip-v4
I tested FQF and IQN on `BerzerkNoFrameskip-v4` to see the difference between FQF's performance and IQN's, which is quite obvious in FQF's paper.

<img src="https://user-images.githubusercontent.com/37267851/75833357-2315e280-5dfc-11ea-88f1-ac8eba138953.png" title="BerzerkNoFrameskip-v4" width=700>

## TODO

- [ ] Support risk-averse policies in IQN.
- [ ] Test FQF-Rainbow agent.

## References
[[1]](https://arxiv.org/abs/1911.02140) Yang, Derek, et al. "Fully Parameterized Quantile Function for Distributional Reinforcement Learning." Advances in Neural Information Processing Systems. 2019.

[[2]](https://arxiv.org/abs/1806.06923) Dabney, Will, et al. "Implicit quantile networks for distributional reinforcement learning." arXiv preprint. 2018.

[[3]](https://arxiv.org/abs/1710.10044) Dabney, Will, et al. "Distributional reinforcement learning with quantile regression." Thirty-Second AAAI Conference on Artificial Intelligence. 2018.

