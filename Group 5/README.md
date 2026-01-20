# Group 5 Data Documentation
| Column                   | Description                                             |
| ------------------------ | ------------------------------------------------------- |
| `group_id`               | Identifier of the group that generated the training run |
| `run_id`                 | Unique identifier for a single training run             |
| `time_start`             | Timestamp when training started                         |
| `time_end`               | Timestamp when training finished                        |
| `total_steps`            | Total number of environment steps completed             |
| `total_duration`         | Total training runtime in seconds                       |
| `cpu_vendor`             | CPU manufacturer (e.g., Intel, AMD)                     |
| `cpu_cores`              | Number of physical CPU cores                            |
| `cpu_threads`            | Number of logical CPU threads                           |
| `cpu_frequency_khz`      | CPU base frequency in kHz                               |
| `cpu_architecture`       | CPU architecture (e.g., x86_64, ARM)                    |
| `ram_total_bytes`        | Total system RAM in bytes                               |
| `ram_available_bytes`    | Available RAM at runtime                                |
| `ram_type`               | RAM technology (if available)                           |
| `gpu_count`              | Number of GPUs detected                                 |
| `gpu_0_name`             | Name of the first GPU                                   |
| `gpu_0_vendor`           | Vendor of the first GPU                                 |
| `gpu_0_vram_gb`          | VRAM of the first GPU in GB                             |
| `gpu_1_name`             | Name of the second GPU (if present)                     |
| `gpu_1_vendor`           | Vendor of the second GPU                                |
| `gpu_1_vram_gb`          | VRAM of the second GPU in GB                            |
| `trainer_type`           | Reinforcement learning algorithm used (e.g., PPO, SAC)  |
| `batch_size`             | Number of experiences used per learning update          |
| `buffer_size`            | Size of the experience replay buffer                    |
| `learning_rate`          | Learning rate of the optimizer                          |
| `beta`                   | Entropy regularization strength                         |
| `epsilon`                | PPO clipping parameter                                  |
| `lambd`                  | GAE lambda parameter                                    |
| `num_epoch`              | Number of passes over the buffer per update             |
| `learning_rate_schedule` | Learning rate scheduling strategy                       |
| `shared_critic`          | Whether actor and critic share parameters               |
| `normalize`              | Whether observations are normalized                     |
| `hidden_units`           | Number of neurons per hidden layer                      |
| `num_layers`             | Number of hidden layers                                 |
| `vis_encode_type`        | Visual encoder architecture                             |
| `memory`                 | Whether recurrent memory is used                        |
| `goal_conditioning_type` | Goal conditioning configuration                         |
| `deterministic`          | Whether training is deterministic                       |
| `extrinsic_gamma`        | Discount factor for future rewards                      |
| `extrinsic_strength`     | Weight of the extrinsic reward signal                   |
| `init_path`              | Path to a pretrained checkpoint (if any)                |
| `threaded`               | Whether multithreading is enabled                       |
| `max_steps`              | Maximum number of environment steps                     |
| `time_horizon`           | Steps collected before each policy update               |
| `summary_freq`           | TensorBoard logging frequency                           |
| `self_play`              | Whether self-play training is enabled                   |
| `behavioral_cloning`     | Whether behavioral cloning is used                      |



