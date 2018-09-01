# Project: Navigation
## Saminda Abeyruwan

In this project, we have trained and tested an agent that successfully navigates a square environment and collects _banana_ shaped objects.

The following video shows that the learned agent navigates the environment and collects +15 points.

[![Alt text](https://img.youtube.com/vi/B7dAbOEP5Ps/0.jpg)](https://www.youtube.com/watch?v=B7dAbOEP5Ps)

The agent receives a real feature vector containing 37 elements (size is (37,)). In order to capture the temporal quantities, I have also included a _num\_history_ of past features to create the input state representation of size _(num\_history, 37)_. I have used this design, as we explore the architecture of the deep Q-network (DQN), we can directly use nn.Conv1d, and nn.BatchNorm1d to develop a DQN with better modeling power and capacity. The implementation is available [here](ddqn.py#L124) and [here](Report.md). 

The agent has solved the problem within __600 episodes__, and the weights are saved in [checkpoint_solved.pth](checkpoint_solved.pth).

### Report

The [Report.md](Report.md) contains the detail description of the methodology used in the development of the agent.  

### Training

	python3 ddqn.py --unity_file_name=path/to/Banana.app

The agent was trained in GCP with a CUDA enabled instance. 	

### Testing

	python3 ddqn.py --unity_file_name=path/to/Banana.app --training_mode=0

Please provide the path of the simulator binary or app in the __unity\_file\_name__	argument. 
		
