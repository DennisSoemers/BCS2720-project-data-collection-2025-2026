# Group 01

## Research Question 1: "Can we predict final performance from run metadata / hyperparameters?"
## Research Question 2: "Can we predict when a given performance threshold will be reached?"

### **DATA METRICS**
We use the collected metrics to study how different PPO training configurations affect agent performance and learning efficiency in two Unity environments (Worm and Pyramids). For each environment, we train five distinct configurations (baseline, faster, stabler, steadier, and higher-capacity), each repeated with two random seeds, while keeping the algorithm fixed (PPO). Our main outcome variables are final_perf (the final episodic reward at the end of training) and steps_to_threshold (the number of training steps required to reach an environment-specific performance threshold derived from baseline runs). We also include wallclock_seconds_total as a measure of time efficiency.

As input features for our models, we use the hyperparameters and system descriptors that vary across runs: learning_rate, batch_size, nn_arch_depth, the categorical env_name, and the hardware-related metrics cpu_cores_logical and ram_total_gb. This allows us to analyse how changes in learning rate, batch size, network depth, environment, and available computational resources relate to both final performance (RQ1) and the time/steps needed to reach the performance threshold (RQ2).

### Configurations Pyramids Environment

| Config               | learning_rate | batch_size | buffer_size | hidden_units | beta   |
|----------------------|----------------|------------|-------------|--------------|--------|
| **1 (baseline)**      | 0.0003         | 128        | 2048        | 512          | 0.01  |
| **2 (faster)**        | 0.0005         | 128        | 2048        | 512          | 0.01  |
| **3 (stabler)**       | 0.0003         | 256        | 4096        | 512          | 0.01 |
| **4 (more_capacity)** | 0.0003         | 128        | 2048        | 1024          | 0.01  |
| **5 (steadier)**      | 0.0002         | 128        | 2048        | 512          | 0.01  |


### Configurations Worms Environment 

| Config               | learning_rate | batch_size | buffer_size | hidden_units | beta   |
|----------------------|----------------|------------|-------------|--------------|--------|
| **1 (baseline)**      | 0.0003         | 128        | 4096        | 256          | 0.001  |
| **2 (faster)**        | 0.0005         | 128        | 4096        | 256          | 0.002  |
| **3 (stabler)**       | 0.0003         | 256        | 8192        | 256          | 0.0005 |
| **4 (more_capacity)** | 0.0003         | 128        | 4096        | 512          | 0.001  |
| **5 (steadier)**      | 0.0002         | 128        | 4096        | 256          | 0.001  |


### Scripts 
1. run_all.py: automated Python run script to execute multiple sequential trainings
2. tensorflow_to_csv.py: script for metric extraction from training logs (with our own performance and threshold definitions) to a csv file
3. unify_csvs.py : supported us into unifying all the csv files automatically instead of having to do it manually 
4. meanClac.py: to calculate the mean of the plateau_reward values calculated by 6 baseline runs (per environment)




