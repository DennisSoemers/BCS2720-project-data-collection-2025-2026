# Group 6

## Additional files
[```summary_report.md```](https://github.com/omarelfiki/unity-ml-drl-data/blob/main/data/summary_report.md) and [```validation_report.md```](https://github.com/omarelfiki/unity-ml-drl-data/tree/main/data/validation_report.md) provide a quick glance on results with plots and data validation checks.

[```thresholds/```](https://github.com/omarelfiki/unity-ml-drl-data/blob/main/data/thresholds) provides the archived threshold at each data collection point based on datetime.

## Understanding Results

### Research Question
Can we predict the time-to-threshold, denoting number of training steps and wall-clock time required for
an agent to reach a performance threshold using initial configuration and early learning-curve signals?

#### Targets (to predict)
* Wall clock time (s) (observed seconds).
* Time-to-threshold (derived) from per-step reward logs: steps/time to reach a target reward.

### Column Dictionary

| **Column**                    | **Type** | **Description**                                                 |
|-------------------------------|----------|-----------------------------------------------------------------|
| `run_id`                      | string   | Unique identifier for a run                                     |
| `environment`                 | string   | Unity environment (e.g., `3DBall`, `Basic`, `Sorter`)           |
| `seed`                        | int      | Random seed for reproducibility (`-1` indicates default/random) |
| `num_agents`                  | int      | Number of simultaneous agents/instances                         |
| `algorithm`                   | string   | DRL algorithm (e.g., `PPO`)                                     |
| `steps`                       | int      | Completed total training steps                                  |
| `batch_size`                  | int      | Minibatch size per update                                       |
| `buffer_size`                 | int      | Experience buffer size                                          |
| `learning_rate`               | float    | Optimizer learning rate                                         |
| `epochs`                      | int      | Epochs per update (if applicable)                               |
| `total_time`                  | float    | Wall-clock time in seconds                                      |
| `average_cpu`                 | float    | Average CPU utilization (0–100)                                 |
| `average_ram`                 | float    | Average RAM utilization (0–100)                                 |
| `step_interval`               | int      | Step interval used for computing running means                  |
| `reward_mean`                 | float    | Average policy reward                                           |
| `reward_mean_step`            | int      | Step index where reward aggregation starts                      |
| `p_loss_mean`                 | float    | Average policy loss                                             |
| `p_loss_mean_step`            | int      | Step index where policy-loss aggregation starts                 |
| `v_loss_mean`                 | float    | Average value loss                                              |
| `v_loss_mean_step`            | int      | Step index where value-loss aggregation starts                  |
| `entropy_mean`                | float    | Average policy entropy                                          |
| `entropy_mean_step`           | int      | Step index where entropy aggregation starts                     |
| `threshold_value`             | float    | Target reward threshold                                         |
| `threshold_version`           | datetime | Thresholds used at the time of training                         |
| `steps_to_threshold`          | int      | Step taken to reach threshold                                   |
| `time_to_threshold`           | int      | Time in seconds to reach the threshold                          |
| `run_reached_threshold`       | bool     | Whether the threshold was reached                               |
| `best_reward_before_timeout`  | int      | Best policy reward reached before training timeout              |
| `step_of_best_reward`         | int      | Step where best reward was reached                              |
