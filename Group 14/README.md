# Group 14

# Data Metrics Documentation

The list below contains the metrics that the scripts calculate and store. The names of the columns in the CSV table are the same as these:

- **step** - The number of steps performed.
- **mean_reward** - The mean reward for the current run.
- **mean_group_reward** - The mean reward of the group for the current run, applicable only to multi-agent environments.
- **std_reward** - The standard deviation of the reward.
- **time_elapsed** - The time elapsed of the current run.
- **memory_usage_avg_mb** - Average memory usage in MB.
- **memory_usage_peak_mb** - Peak memory usage in MB.
- **cpu_usage_avg_percent** - Average CPU usage in percent.
- **cpu_usage_peak_percent** - Peak CPU usage in percent.
- **gpu_usage_avg_mb** - Average GPU usage in MB (can not be calculated if your system has an integrated graphics card).
- **gpu_usage_peak_mb** - Peak GPU usage in MB.
- **trainer_type** - The algorithm used by the agent.
- **policy_entropy** - Policy entropy.
- **losses_policy_loss** - Policy loss.
- **losses_value_loss** - Value loss.

Recorded hyperparameter values:

- **batch_size**
- **buffer_size**
- **learning_rate**
- **beta**
- **epsilon**
- **lambd**
- **num_epoch**
- **learning_rate_schedule**
