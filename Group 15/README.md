# Group 15

This dataset contains metadata and performance metrics from ML-Agents training runs using PPO and SAC reinforcement learning algorithms.
We had to compress our data into ZIP file as it wouldn't fit otherwise.
From ZIP file you will get 3 csv files, named **static.csv** , **training.csv** and **summary.csv**

## Dataset Overview
- **Total runs recorded**: 5710
- **Algorithms used**: PPO, SAC
- **Environments**: 3DBall, 3DBallHard, Crawler, GridFoodCollector, GridWorld, Hallway, PushBlock, Pyramids, Sorter, Walker, Worm
__________________________________________________________

### Static data explanation

| Column | Column Description  |
| --------| -------------------- |
| run id  | Unique identifier for each experiment run |
| os  | Machine Operating System |
| cpu  | CPU model name |
| physical cores  | Number of physical CPU cores |
| system ram gb  | Total system RAM in gigabytes |
| gpu  | GPU model name |
| GPU ram mb  | GPU memory size in megabytes |
| cuda version  | CUDA toolkit version used |
| training type  | Type of RL algorithm used (PPO, SAC) |
| game name | name of the trained game |
| batch size  | Number of samples per training batch | 
| learning rate  | Initial learning rate | 
| buffer size  | Buffer size | 
| beta  | Entropy regularization coefficient | 
| episolon  | Exploration rate | 
| lambd  | Lambda parameter | 
| num epochs  | Number of epochs | 
| learning rate schedule  | Type of lr scheduler ( constant, linear) | 
| normalize  | Whether input observations are normalized | 
| hidden units  | Number of hidden units | 
| num layers | Total number of hidden layers | 
| vis encode type  | Visual encoder type | 
| reward extrinsic gamma  | Extrinsic reward gamma | 
| reward extrinsic strength  | Extrinsic reward strength | 
| keep checkpoints  | Number of saved model checkpoints to keep | 
| max steps  |Maximum number of environment steps per run | 
| time horizon  | Time horizon | 
| summary freq  | Frequency of summary |  

_____________________________________________________________________

### Training data explanation

| Column | Column Description | 
| ------- | -----------------|
| run id | Identifier for the specific training run | 
| step | Current training step count | 
| beta | |
| cpu frequency mhz  | CPU clock speed at the time of logging (MHz) | 
| cpu usage percent | CPU utilization percentage at the time of logging |
| cumulative reward  | Total reward accumulated in the current episode |
| entropy  | Policy entropy value at this update step | 
| episode length | duration of last episode (seconds) |
| episode time |  |
| epsilon | Exploration rate |
| extrinsic reward | Extrinsic reward |
| extrinsic value estimate |  Extrinsic value function’s estimate of the current state’s return.|
| game cpu usage | Trainig cpu usage (MHz) | 
| game memory usage | Training memory usage (MB) | 
| gpu usage percent | GPU utilization percentage at the time of logging (if -1, gpu wasnt used) |
| learning rate | Rate of learning for last step |
| loss value  | Value function loss calculated at this update step |
| policy loss | Policy loss calculated at this update step | 
| ram usage mb  | System RAM usage at the time of logging (MB) |
| step length | length of steps (ms) |
| steps per second | number of steps in a second |
| time elapsed ms  | Time elapsed since the start of the run (seconds) |
| vram usage mb  | VRAM (GPU memory) usage at the time of logging (MB) | 

______________________________________________________________________________

### Summary data explanation

|Column | Column Description |
| ------- | ----------------- |
| run id | Run ID |
| final reward | Mean of final rewards achieved across all agents or episodes |
| max reward | Highest mean reward achieved during training |
| time to max reward sec  | Time taken to reach the maximum mean reward (in seconds) |
| total duration sec | Total duration of the training session in seconds | 
| mean policy loss | Average policy loss throughout training |
| mean value loss  | Average value function loss during training |
| mean entropy  | Average entropy across all training steps, representing exploration level |
| final entropy  | Entropy value recorded at the end of training |
| max cpu usage percent | Maximum CPU utilization observed during training |
| mean cpu usage percent | Mean CPU utilization percentage throughout training |
| max ram used mb  | Peak RAM usage in MB |
| mean ram used mb | Average RAM usage in MB | 
| mean cpu fequency | Average CPU frequency during training |
| max cpu frequency | Maximum CPU frequency during training |
| max gpu usage percent | Maximum GPU utilization during training |
| mean gpu usage percent | Average GPU utilization percentage across training |
| max vram used mb | Maximum VRAM (GPU memory) usage in MB |
| mean vram used mb | Mean VRAM usage in MB during training |






