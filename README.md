# Sinkhorn Policy Optimization

## 代码说明
1. `core.py` 文件主要包含：
    - 一些工具性的函数，例如：模型参数的获取与拷贝等；
    - 网络模型：`Q-Net`, `Pi-Net` 以及 `AC-Net`;
    - `Replay Buffer`: 可以随机采样(Off-policy)，也可以获取最新加入的样本(On-policy);
2. `shpo.py` 文件包含算法的主要流程：
    - 一些初始化的内容，例如：模型创建，环境创建，种子设定，`Replay Buffer`的创建；
    - `Critic` 部分相关的子函数： `Critic` 损失函数 与 参数更新函数；
    - `Actor` 部分相关的子函数： `Actor` 损失函数 与 参数更新函数；
    - 算法的主循环部分: 开始强化学习，会调用上面定义的函数。

## 目前的版本的特点
- 使用 `Double Q Net` 技术 以及 `Replay Buffer` 来训练 `Q-Net`;
- 使用当前policy采集的样本来训练 `Pi-Net`;


## 需要补充的点

文件 `shpo.py` 中的 `update_actor()` 函数中计算自然梯度的部分。