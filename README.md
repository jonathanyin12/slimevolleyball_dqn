# Deep Q-Learning for Slime Volleyball
Group Members: Jonathan Yin, Deyuan Li, Oliver Ye

https://user-images.githubusercontent.com/26175818/207496808-c5ef73e8-3663-4fe3-8c56-815f47134369.mov

Our trained agent, based on the Deep Q-learning algorithm is the yellow agent on the right, while the baseline agent is the blue agent on the right. We observe that our agent, trained via DQN, is able to move and adjust accordingly to consistently hit the ball over the net and prevent the ball from hitting the ground on its own side.

The game is Slime Volleyball. It is a two player game, where each person controls an agent and uses the arrow keys to move their agent left and right and to jump. There is a ball that is being passed back and forth, and the goal of the game is to hit the ball with your agent and getting it across the net. The balls and agents obey the laws of gravity, and the ball bounces on each agent's head as one would expect in physics. A player score a point if the ball touches the ground on the opponent's side, and a player loses a point if it lands on their side. The game is also capped at 3000 time steps, in which case the game is drawn, and no player scores any point. We created an agent that can play Slime Volleyball well, using a deep q-learning (DQN) model, trained against a well-performing Slime Volleyball bot that plays expertly. 

## Installation: 
For installation, you will need to pip install the required packages
```
pip install -r requirements.txt
```

## Basic Usage:
To train the deep q-network, run
```
python train.py
```
Training can take many hours before achieving decent intelligent gameplay. We used high-performance GPUs to speed up training as well, and have loaded in the model weights resulting from approximately 10 hours of training.

To evaluate the agent, run
``` 
python eval.py
```
This loads our best DQN agent and has it compete against the baseline agent from the Slime Volleyball Gym environment for 100 matches. It then generates match statistics. 

To visualize the agent's gameplay or manually play against it, run
``` 
python play.py
```
Our agent is the yellow slime on the right. By using the arrow keys, you can manually control the blue agent. Visualizing the agent using this command requires a display driver (which unfortunately does not exist in the Zoo).


## Results:
After training for over 500 epochs, our model achieved an average score of -0.35 against the baseline agent. Each game lasted on average 3000 time steps. Since the game ends after 3000 time steps, neither agent runs out of lives before the game ends. 

Although the baseline agent is better, we were impressed by the performance of our model nonetheless. Empirically, when playing manually against the baseline agent, we consistenly lose every round (corresponding to an average score of approximately -1), so our agent is able to perform significantly better. As seen in our video, our agent plays intelligently. Furthermore, it can win against the average human player consistently.


## References:
We use [Slime Volleyball Gym](https://github.com/hardmaru/slimevolleygym) as our gym environment to train our model. Our agent is trained against the baseline model provided by the environment.
