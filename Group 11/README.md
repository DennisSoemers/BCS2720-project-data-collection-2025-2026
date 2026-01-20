# Group 11

## Research Questions
1. Can we predict average and peak RAM and CPU a training will reach?
2. Can we predict how deep into a training process an agent will be able to reach a certain relevant threshold level of performance?

## Dataset
### Training data
1. The file [```PushBlock-training-20251127.csv```] provides the first sample of data collected for the Unity environment PushBlock. Below is an explanatory   table for each feature provided in the file.

### Dataset Explanation
| **Feature**                   | **Description**                                                 |
|-------------------------------|-----------------------------------------------------------------|
| `run_id`                      | Unique identifier per training (time-based)                     |
| `config_name`                 | Configuration file name                                         |
| `total_ram_mb`                | Total RAM capacity in MB                                        |
| `cpu_cores`                   | Number of cores in machine                                      |
| `batch_size`                  | Batch size per update                                           |
| `buffer_size`                 | Buffer size before training updates                             |
| `learning_rate`               | Learning rate                                                   |
| `beta`                        | Regularization term for entropy in PPO                          |
| `epsilon`                     | Clipping parameter in PPO that limits policy deviation          |
| `lambd`                       | Controls Generalized Advantage Estimation                       |
| `num_epoch`                   | Number of epochs per update                                     |
| `num_layers`                  | Number of layers in policy network                              |
| `hidden_units`                | Number of neurons per layer                                     |
| `gamma`                       | Discount factor for future rewards                              |
| `strength`                    | Coefficient for curiosity or intrinsic reward signals           |
| `time_horizon`                | Number of steps before experiences are added to the buffer      |
| `summary_freq`                | Frequency of steps of logging training statistics               |
| `keep_checkpoints`            | Number of model checkpoints to keep during training             |
| `max_steps`                   | Maximum steps per training                                      |
| `cpu_avg_unity`               | Average CPU of Unity per training                               |
| `cpu_peak_unity`              | Peak CPU of Unity per training                                  |
| `ram_avg_unity`               | Average RAM of Unity per training                               |
| `ram_peak_unity`              | Peak RAM of Unity per training                                  |
| `cpu_avg_python`              | Average CPU of Python script (running ml-agents) per training   |
| `cpu_peak_python`             | Peak CPU of Python script (running ml-agents) per training      |
| `ram_avg_python`              | Average RAM of Python script (running ml-agents) per training   |
| `ram_peak_python`             | Peak RAM of Python script (running ml-agents) per training      |
| `duration_sec`                | Training duration in seconds                                    |

2. The file [```MeanReward_training_data.csv```] provides the data collected in the PushBlock environment to answer the second research question. Below is a short explanation of how the data is displayed.
### Dataset Explanation
| **Feature**                   | **Description**                                                 |
|-------------------------------|-----------------------------------------------------------------|
| `runNr`                       | Unique identifier per training                                  |
| `nrSteps`                     | Step count                                                      |
| `timeUnit`                    | A time unit is 60k steps                                        |
| `meanReward`                  | It is the threshold we measure to answer our researach question |
