# Group 7
## Overview
These datasets contain the training runs of Project Group 7. 
Each row is a single training run distinguished by run_id.
Each column is either navigation data, hardware specifications, ML hyperparameters, or recorded results for training time and performance.
Note: `old_dataset.csv` originally contained many more training runs but had significantly skewed data. The current dataset in use is `new_data.csv`, which aims to address and mitigate this issue. 


### Navigation data
| Column name | Description |
|------------|-------------|
| run_id | name of the run |
| timestamp | when the run occured |


### Hardware Specifications
| Column name | Description |
|------------|-------------|
| cpu_model | name of the CPU Model |
| cpu_cores | number of physical CPU cores |
| cpu_frequency | number of possible cycles the CPU can execute per second |
| total_ram | total RAM capacity in Gb |
| gpu_model | name of the GPU Model |
| operating_system | Operating System used for the training run |


### ML Hyperparameters
| Column name | Description |
|------------|-------------|
| drl_algorithm | name of the DRL algorithm used |
| batch_size | number of experiences in each gradient update |
| buffer_size | number of experiences to collect before updating the model |
| learning_rate | size of update steps  |
| beta | entropy regularization strength control |
| epsilon | update magnitude control  |
| lambda | bias-variance tradeoff control |
| num_epoch | number of passes through experience buffer for gradient descent |
| normalize | observation normalization enabler (T/F) |
| hidden_units | number of units per hidden layer |
| num_layers | number of hidden layers |
| gamma | discount factor for future rewards control |
| max_steps | total number of steps for training |
| time_horizon | number of experience steps before adding to experience buffer |


### Target Variables
| Column name | Description |
|------------|-------------|
| cumulative_reward_mean | core task performance |
| time_elapased_seconds | wall-clock training time in seconds |


## How values are recorded
- Hyperparameters are specified before ML training begins

- Source of Origin: User
  - run_id

- Source of Origin: Program
  - timestamp

- Source of Origin: System Query
  - cpu_model
  - cpu_cores
  - cpu_frequency
  - total_ram
  - gpu_model
  - operating_system 


- Source of Origin: Training Configuration File
  - drl_algorithm
  - batch_size
  - buffer_size
  - learning_rate
  - beta
  - epsilon
  - lambda
  - num_epoch
  - normalize
  - hidden_units
  - num_layers
  - gamma
  - max_steps
  - time_horizon

- Source of Origin: Data Log
-- cumulative_reward_mean 
-- time_elapased_seconds

- One row is written in the dataset once training ends with recorded results



