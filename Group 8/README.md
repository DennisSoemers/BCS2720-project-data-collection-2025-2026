# Group 8
First, group members add generated data to the [forked repository](https://github.com/qba24qba/BCS2720-project-data-collection-2025-2026.git) where they can still be edited.
 The finalized data are merged into the [collaborative collection repository](https://github.com/DennisSoemers/BCS2720-project-data-collection-2025-2026) via the pull request and are not deleted nor overwritten as they might be currently used by others. Committed files should be stored in the directory with the name ```YYYYMMDD__HHMM``` correspondning to the time of pull request to keep track of it.

 ## Data Documentation

Data from runs are stored in two different CSV files.  **Main** file captures all the data that don't change during the run. That includes hardware specifications, information about environment and algorithm used together with [hyperparameters configuration](https://unity-technologies.github.io/ml-agents/Training-Configuration-File/). Data for *final* parameters are added at the end of each run. Here one row equals one ML-Agents training run.  

In the **Run logging** file we store results of real-time hardware monitoring together with steps, time and reward observed. Here each row is a summary we get every couple thousand of steps.

The parameters that we use, can be found in the following tables:


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

### Run logging table

Since the run logging files have to be recognised by the main run file, their name is the same as run_id.


| **Name**        | **Type** | **Unit** | **Group** | **Notes** |
|-----------------|----------|----------|------------------|----------------------|
| avg_ram_usage   | float    | MB       | hardware         | average RAM usage |
| avg_cpu_usage   | float    | %        | hardware         | average CPU usage |
| avg_gpu_usage   | float    | %        | hardware         | null if no GPU |
| steps           | int      | steps    | observe          | current step count |
| time_elapsed    | float    | s        | observe          | elapsed time |
| mean_reward     | float    | --       | observe          | mean reward |
| std_of_reward   | float    | --       | observe          | reward standard deviation |

