# Group 8
First, group members add generated data to the [forked repository](https://github.com/qba24qba/BCS2720-project-data-collection-2025-2026.git) where they can still be edited.
 The finalized data are merged into the [collaborative collection repository](https://github.com/DennisSoemers/BCS2720-project-data-collection-2025-2026) via the pull request and are not deleted nor overwritten as they might be currently used by others. 

 ## Data Documenation

One row equals one ML-Agents training run. Features capture hardware, environment, [hyperparameters configuration](https://unity-technologies.github.io/ml-agents/Training-Configuration-File/) (from YAML). Targets capture runtime and performance outcomes.
The data is stored in CSV file (UTF-8).

| **Name**                 | **Type**      | **Unit**  | **Role**          | **Notes / Example**                         |
|---------------------------|---------------|------------|-------------------|---------------------------------------------|
| schema_version            | string        | --         | meta              | 1.0                                         |
| run_id                    | string        | --         | meta              | 2025-10-23_G8_01                            |
| date                      | date          | --         | meta              | YYYY-MM-DD                                  |
| machine_id                | string        | --         | meta              | filippo-laptop                              |
| os_name                   | string        | --         | feature           | Windows 11 / Ubuntu 22.04 / macOS 14        |
| cpu_model                 | string        | --         | feature           | Intel i7-12700H / M2 Pro                    |
| cpu_cores                 | int           | count      | feature           | 14                                          |
| cpu_clock_ghz             | float         | GHz        | feature           | 3.5                                         |
| ram_gb                    | int           | GB         | feature           | 16 / 32 / 64                                |
| gpu_model                 | string        | --         | feature           | RTX 3060 / Apple M2 GPU                     |
| gpu_vram_gb               | float - null | GB      | feature           | 6.0 / null                                  |
| env_id                    | string        | --         | feature           | FoodCollector / 3DBall                      |
| env_variant               | string        | --         | feature           | default / hard                              |
| algo                      | string        | --         | feature           | PPO / SAC / Imitation / POCA                |
| seed                      | int           | --         | meta              | random                                      |
| learning_rate             | float         | --         | feature           | 3e-4                                        |
| batch_size                | int           | samples    | feature           | 1024 / 2048 / 4096                          |
| buffer_size               | int           | samples    | feature           | 20480 / 40960 / 65536                       |
| gamma                     | float         | --         | feature           | 0.99 / 0.995                                |
| lambda                    | float         | --         | feature           | 0.95 / 0.97                                 |
| hidden_units              | int           | neurons    | feature           | 128 / 256 / 512                             |
| num_layers                | int           | layers     | feature           | 2 / 3                                       |
| steps_planned             | int           | steps      | feature           | 120000--300000                              |
| steps_completed           | int           | steps      | meta              | = steps_planned                             |
| wallclock_s               | float         | s          | **target**        | e.g., 3589.4                                |
| time_to_threshold_s       | float - null | s      | **target**        | null if not reached                         |
| final_reward              | float         | --         | **target**        | e.g., 1.52                                  |
| cpu_util_mean_pct         | float         | %          | feature           | ~55--80                                     |
| ram_peak_mb               | float         | MB         | **target**        | e.g., 7350                                  |
| gpu_util_mean_pct         | float - null | %      | feature           | e.g., 45.0 / null                           |
| notes                     | string        | --         | meta              | free text                                   |

## File naming

Files should be stored in the directory ```env``` with the name ```YYYYMMDD__HHMM__machine.csv``` where:
- ```env``` refers the enviroment id, named in the same way as [ML_agents](https://github.com/DennisSoemers/ml-agents/tree/develop/Project/Assets/ML-Agents/Examples)
- ```YYYYMMDD__HHMM``` describes time with precision to minutes
- ```machine``` is the value of machine_id column specified in the file