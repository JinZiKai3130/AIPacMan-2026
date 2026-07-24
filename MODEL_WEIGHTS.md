# 模型权重说明

## machinelearning/models.py

### PerceptronModel
- 权重矩阵: (1, dimensions), 参数量 = dimensions
- 无隐藏层，无激活函数

### RegressionModel
- Layer1 (Linear): 128×1 + 128bias = 256
- Layer2 (Linear): 1×128 + 1bias = 129
- 总参数量: 385
- 激活函数: ReLU | 优化器: Adam(lr=0.005)

### DigitClassificationModel
- Layer1 (Linear): 256×784 + 256bias = 200,960
- Layer2 (Linear): 128×256 + 128bias = 32,896
- Layer3 (Linear): 10×128 + 10bias = 1,290
- 总参数量: 235,146
- 激活函数: ReLU | 优化器: Adam(lr=0.001)

## reinforcement/model.py

### DeepQNetwork
- 动作空间: 5 (North, South, East, West, Stop)
- 状态维度: 2 + 2×numGhosts + width×height
- Layer1 (Linear): (128, state_dim) + 128bias
- Layer2 (Linear): (128, 128) + 128bias = 16,512
- Layer3 (Linear): (5, 128) + 5bias
- 激活函数: ReLU | 优化器: SGD(lr=0.08) | batch_size=64
- Target Network: 结构相同，参数量 ×2