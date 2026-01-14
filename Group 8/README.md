# Group 8

## Data collection process

First, generated data are added to the [forked repository](https://github.com/qba24qba/BCS2720-project-data-collection-2025-2026.git) where they can still be edited.
 The finalized data are merged into the [collaborative collection repository](https://github.com/DennisSoemers/BCS2720-project-data-collection-2025-2026) via the pull request and are not deleted nor overwritten as they might be currently used by other groups. New runs will be added to consecutive *training_data* directories. Description of datasets can be found at the end of this Readme. 

 ## Data Documentation

**Main** file captures data like hardware specifications, information about environment and algorithm used together with [hyperparameters configuration](https://unity-technologies.github.io/ml-agents/Training-Configuration-File/). Data for *final* parameters are added at the end of each run. Here one row equals one ML-Agents training run.  

The parameters that we use, can be found in the following table:


### Main Table

| **Name**                         | **Type**   | **Unit** | **Group** | **Notes**|
|----------------------------------|------------|----------|------------------|----------------------|
| run_id                           | string     | --       | common           | machine_id + algo + config name |
| machine_id                       | string     | --       | common           | username + os_name |
| run_log_file                     | string     | --       | common           | path to the run logging file |
| algo                             | string     | --       | common           | PPO / SAC |
| seed                             | int        | --       | common           | random int |
| env_name                         | string     | --       | common           | 3D Ball |
| os_name                          | string     | --       | hardware         | Windows / Ubuntu / macOS|
| cpu_physical_cores               | int        | count    | hardware         |  
| cpu_logical_cores                | int        | threads  | hardware         |  
| cpu_clock_ghz                    | float      | GHz      | hardware         | 
| ram_mb                           | int        | MB       | hardware         | 
| avg_cpu_usage                    | float      | %        | hardware         | 
| avg_ram_usage                    | float      | MB       | hardware         | 
| peak_cpu_usage                   | float      | %        | hardware         | 
| peak_ram_usage                   | float      | MB       | hardware         | 
| learning_rate                    | float      | --       | common yaml      | 
| learning_rate_schedule           | string     | --       | common yaml      | 
| batch_size                       | int        | samples  | common yaml      | 
| buffer_size                      | int        | samples  | common yaml      | 
| normalize                        | bool       | --       | common yaml      | 
| hidden_units                     | int        | neurons  | common yaml      | 
| num_layers                       | int        | layers   | common yaml      | 
| vis_encode_type                  | string     | --       | common yaml      | 
| gamma                            | float      | --       | common yaml      | 
| strength                         | float      | --       | common yaml      | reward strength |
| keep_checkpoints                 | int        | count    | common yaml      | number of checkpoints |
| max_steps                        | int        | steps    | common yaml      | planned steps |
| time_horizon                     | int        | steps    | common yaml      |
| summary_freq                     | int        | steps    | common yaml      | logging frequency |
| buffer_init_steps                | int        | steps    | sac              |  |
| tau                              | float      | --       | sac              |  |
| steps_per_update                 | int        | steps    | sac              | |
| save_replay_buffer               | bool       | --       | sac              | 
| init_entcoef                     | float      | --       | sac              | 
| reward_signal_steps_per_update   | int        | steps    | sac              |  |
| beta                             | float      | --       | ppo              |  |
| epsilon                          | float      | --       | ppo              | |
| lambd                            | float      | --       | ppo              |  |
| num_epoch                        | int        | epochs   | ppo              |  |
| train_duration_s                 | float      | s        | final            | total training time |
| final_mean_reward                | float      | --       | final        | final mean reward |
| final_std_reward                 | float      | --       | final         | final standard deviation of the reward |
| time_to_convergence              | float/null | s        | final            | null if no convergence |
| steps_to_convergence             | int/null   | steps    | final            | null if no convergence |

---

### Encoded_dataset

**Encoded_dataset** is derived from *main* dataset. It was adjusted to use in our own models. The differences are:
- description columns like: *run_id*, *machine_id*, *run_log_file*, *env_name* were dropped
- *algo* column changed into binary *algo_sac*, which indicates sac if TRUE ppo if FALSE
- *os_name* column was dropped and binary *os_name_Windows*, *os_name_macOS* were added
- column with binary variable *converged* was added
- N.A. values were changed to numerical 0.0

## Datasets description per version

### training_data_1
Environment used: **3D Ball**

Algortihms used: **PPO** and **SAC**

For both PPO and SAC configurations *buffer_size*, *hidden_units* and *num_layers* were the randomized parameters.

In SAC configutarions also *gamma*, *time_horizon*, *buffer_init_steps*, *tau*, *steps_per_update*, *init_entcoef* and *reward_signal_steps_per_update* were randomized.

SAC runs data collection took too long, in possible future datasets it won't be included

End of the run is defined as reaching convergence or max_steps (in this dataset max_steps ie either: 10000000 or 2000000).

A run is considered converged when:

- mean_reward ≥ 100  
- std_reward / mean_reward ≤ 1

The first window that satisfies these conditions determines:

- `steps_to_convergence`
- `time_to_convergence`

If no window satisfies the criteria, these values remain `NA`.

