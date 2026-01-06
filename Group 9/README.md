Group 9

Dataset Explanation:


| Variable name | Meaning |
| ------------- | ------------- |
| run_id   | Unique identifier for each training run/experiment |
| bath_size | Number of samples processed before updating model weights |
| buffer_size   | Size of experience replay memory for storing past experiences |
| efficiency_score   | Mean reward divided by total time. |
| ELO   | Skill rating score (1200 = baseline, higher = better performance) |
| env_name   | Name of the training environment scenario |
| epoch   | Number of times the model reviews the same batch of data |
| gamma   | Discount factor for future rewards (0.99 = values future rewards highly) |
| group_cumulative_reward   | Total sum of rewards accumulated during entire training |
| lambda   | Parameter for Generalized Advantage Estimation (GAE) algorithm |
| learning_rate   | Step size for updating model weights during optimization |
| mean_entropy   | Average randomness/exploration in action selection |
| mean_group_entropy   | Average exploration across all agents in the group |
| mean_policy_loss   | 	Error in action selection (lower = more stable training) |
| mean_gropup_reward   | Average reward per episode/step across all agents |
| total_steps   | Total number of environment interactions during training |
| training_time   | Total time spent training (in seconds) |


