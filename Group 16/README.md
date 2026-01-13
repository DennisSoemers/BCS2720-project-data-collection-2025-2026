# ML-Agents Training Data Dictionary

This dataset contains metadata and performance metrics from Unity ML-Agents training runs using PPO (Proximal Policy Optimization) and SAC (Soft Actor-Critic) reinforcement learning algorithms.

## Dataset Overview
- **Total Records**: 67 training runs
- **Algorithms**: PPO, SAC
- **Environments**: 3DBall, Basic, PushBlock, Crawler, Walker, GridWorld
- **Collection Period**: January 2026

---

## Column Descriptions

### 1. Environment & Algorithm Configuration

#### `enviroment`
The Unity ML-Agents environment used for training.
- **Type**: String
- **Examples**: 3DBall, Basic, Crawler, Walker, PushBlock, GridWorld
- **Context**: Different environments present varying complexity levels for RL agents

#### `algorithm`
The reinforcement learning algorithm used for training.
- **Type**: String
- **Values**: ppo (Proximal Policy Optimization), sac (Soft Actor-Critic)
- **Context**: PPO is on-policy, SAC is off-policy; different algorithms suit different tasks

---

### 2. Neural Network Architecture

#### `hidden_units`
Number of neurons in each hidden layer of the neural network.
- **Type**: Integer
- **Range**: 100-1000+
- **Context**: Larger networks can learn more complex policies but require more compute

#### `num_layers`
Number of hidden layers in the neural network.
- **Type**: Integer
- **Range**: 1-5
- **Context**: Deeper networks can model more complex behaviors but may overfit or train slower

---

### 3. Core Hyperparameters

#### `learning_rate`
Step size for gradient descent optimization.
- **Type**: Float
- **Range**: 0.0001 - 0.001 (typical)
- **Context**: Controls how quickly the model adapts; too high causes instability, too low slows learning

#### `batch_size`
Number of experiences sampled from the buffer for each gradient update.
- **Type**: Integer
- **Values**: 64, 128, 256, 512, 1024, 2048
- **Context**: Larger batches provide more stable gradients but use more memory

#### `buffer_size`
Maximum number of experiences stored in the replay buffer.
- **Type**: Integer
- **Values**: 2048, 4096, 8192, 10240
- **Context**: Larger buffers provide more diverse training data but use more memory

#### `time_horizon`
Number of steps collected before adding experiences to the buffer.
- **Type**: Integer
- **Values**: 64, 128, 256, 512, 1024
- **Context**: Affects how credit is assigned across time; longer horizons help with delayed rewards

#### `gamma`
Discount factor for future rewards.
- **Type**: Float
- **Range**: 0.8 - 0.995
- **Context**: Values closer to 1 make the agent more far-sighted; lower values prioritize immediate rewards

---

### 4. PPO-Specific Hyperparameters

#### `beta`
Entropy regularization coefficient.
- **Type**: Float
- **Range**: 0.001 - 0.01
- **Context**: Encourages exploration by adding randomness to the policy

#### `epsilon`
Clipping parameter for PPO objective.
- **Type**: Float
- **Range**: 0.1 - 0.3
- **Context**: Limits how much the policy can change per update to maintain training stability

#### `lambd`
Lambda parameter for Generalized Advantage Estimation (GAE).
- **Type**: Float
- **Range**: 0.9 - 0.99
- **Context**: Balances bias vs. variance in advantage estimates

#### `num_epoch`
Number of passes through the experience buffer per update.
- **Type**: Integer
- **Range**: 3 - 10
- **Context**: More epochs extract more learning from each batch but risk overfitting

---

### 5. SAC-Specific Hyperparameters

#### `tau`
Target network update rate for SAC.
- **Type**: Float
- **Range**: 0.001 - 0.01
- **Context**: Controls soft update of target networks; lower values mean slower, more stable updates

#### `init_entcoef`
Initial entropy coefficient for SAC.
- **Type**: Float
- **Context**: Controls exploration vs. exploitation trade-off in SAC

---

### 6. Curriculum Learning & Rewards

#### `strength`
Multiplier for extrinsic rewards.
- **Type**: Float
- **Default**: 1.0
- **Context**: Can amplify or dampen reward signals for easier/harder learning

#### `reward_signal_steps_per_update`
Steps between reward signal updates.
- **Type**: Float
- **Context**: Affects frequency of reward-based learning updates

---

### 7. Training Configuration

#### `steps`
Total number of environment steps actually executed during training.
- **Type**: Integer
- **Context**: Actual steps completed (may differ from max_steps if training ended early)

#### `max_steps`
Maximum number of environment steps configured for training.
- **Type**: Integer
- **Range**: 100k - 3M+
- **Context**: Upper limit on training duration; training may stop earlier if convergence is reached

#### `num_parallel_agents`
Number of agents training simultaneously in parallel environments.
- **Type**: Integer
- **Context**: More agents provide more data per step but require more compute resources

#### `summary_freq`
Frequency (in steps) at which training metrics are logged.
- **Type**: Integer
- **Default**: 10000
- **Context**: Controls granularity of TensorBoard logging

---

### 8. Hardware & System Information

#### `os`
Operating system where training was executed.
- **Type**: String
- **Values**: Windows, Linux, macOS
- **Context**: May affect performance and compatibility

#### `timestamp`
ISO 8601 timestamp when training started.
- **Type**: DateTime
- **Format**: YYYY-MM-DDTHH:MM:SS.ffffff
- **Context**: Useful for tracking chronological order and experimental batches

#### `ram_gb`
Total system RAM available (in gigabytes).
- **Type**: Float
- **Context**: More RAM allows larger buffers and batch sizes

#### `cpu_cores`
Number of CPU cores available for training.
- **Type**: Integer
- **Context**: More cores enable better parallelization of environment simulations

#### `gpu_available`
Whether a GPU was available for training.
- **Type**: Boolean
- **Values**: True, False
- **Context**: GPU dramatically accelerates neural network training

#### `gpu_name`
Model name of the GPU used for training.
- **Type**: String
- **Example**: "NVIDIA GeForce RTX 4070 Ti"
- **Context**: Different GPUs have vastly different performance characteristics

#### `gpu_memory_gb`
GPU memory available (in gigabytes).
- **Type**: Float
- **Context**: Determines maximum model and batch size that can fit in GPU memory

---

### 9. Training Performance Metrics

#### `training_duration_seconds`
Total wall-clock time for training (in seconds).
- **Type**: Float
- **Context**: Key metric for computational efficiency; varies widely by environment complexity

#### `peak_ram_mb`
Maximum RAM usage during training (in megabytes).
- **Type**: Float
- **Context**: Indicates memory requirements for reproducing training runs

---

### 10. Final Training Outcomes

These metrics represent the agent's final performance at the end of training.

#### `final_mean_entropy`
Average policy entropy across all agents at the final step.
- **Type**: Float
- **Context**: Measures randomness in the policy; higher means more exploration, lower means more exploitation

#### `final_sum_entropy`
Cumulative entropy summed across all agents.
- **Type**: Float
- **Context**: Aggregate measure of exploration across parallel agents

#### `final_mean_reward`
Average cumulative reward per episode at training completion.
- **Type**: Float
- **Context**: **Primary success metric** - higher is better; indicates how well the agent learned the task

#### `final_sum_reward`
Total cumulative reward across all agents.
- **Type**: Float
- **Context**: Aggregate performance measure across parallel training

#### `final_cumulative_mean_reward`
Running average of all rewards throughout entire training.
- **Type**: Float
- **Context**: Smoothed reward metric showing overall learning trajectory

#### `final_cumulative_sum_reward`
Cumulative sum of all rewards throughout training.
- **Type**: Float
- **Context**: Total accumulated reward across all training steps

---

### 11. Value Function Metrics

#### `final_mean_extrinsic_value_estimate`
Average value function estimate for extrinsic rewards.
- **Type**: Float
- **Context**: Represents agent's estimate of expected future rewards from current states

#### `final_sum_extrinsic_value_estimate`
Sum of value estimates across all agents.
- **Type**: Float
- **Context**: Aggregate value function predictions

---

### 12. Loss Functions

#### `final_mean_policy_loss`
Average policy loss at final training step.
- **Type**: Float
- **Context**: Measures how much the policy changed; should decrease over training

#### `final_sum_policy_loss`
Cumulative policy loss across agents.
- **Type**: Float
- **Context**: Aggregate measure of policy optimization

#### `final_mean_value_loss`
Average value function loss at final step.
- **Type**: Float
- **Context**: Measures accuracy of value predictions; should decrease as agent learns

#### `final_sum_value_loss`
Cumulative value loss across agents.
- **Type**: Float
- **Context**: Total value function prediction error

---

### 13. SAC-Specific Losses

#### `final_mean_q1_loss`
Average Q1 critic loss (SAC only).
- **Type**: Integer
- **Context**: First critic network's prediction error in SAC

#### `final_sum_q1_loss`
Sum of Q1 losses (SAC only).
- **Type**: Integer

#### `final_mean_q2_loss`
Average Q2 critic loss (SAC only).
- **Type**: Integer
- **Context**: Second critic network's prediction error in SAC (twin critics reduce overestimation)

#### `final_sum_q2_loss`
Sum of Q2 losses (SAC only).
- **Type**: Integer

---

### 14. Entropy Coefficient (SAC)

#### `final_mean_cont_entropy_coeff`
Average continuous entropy coefficient at final step (SAC only).
- **Type**: Integer
- **Context**: Adaptive exploration parameter in SAC

#### `final_sum_cont_entropy_coeff`
Sum of continuous entropy coefficients (SAC only).
- **Type**: Integer

---

### 15. Learning Rate Tracking

#### `final_learning_rate_mean`
Average learning rate at the end of training.
- **Type**: Float
- **Context**: May differ from initial learning rate if using schedules/decay

#### `final_learning_rate_sum`
Sum of learning rates across agents.
- **Type**: Float
- **Context**: Aggregate learning rate metric

---



**Project**: BCS2720 Project 2.1 - Machine Learning in Unity Game Engine  
**Group**: 16  