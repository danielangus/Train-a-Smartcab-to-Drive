# Train a Smartcab to Drive

This is the final project for Udacity's Machine Learning Nanodegree course in reinforcement learning. Reinforcement learning involves training a software agent to react intelligently to its environment. For this project, we work in a simulated traffic environment. There are traffic lights; there are other cars, with blinkers to indicate their next move; and there are passengers with start and end goals in the city. Finally there is the smartcab, which we must program to react to cars and traffic lights, while also getting the passenger safely from point A to point B. Within the simulated environment, the smartcab perceives rewards and penaltites based on the legality of every action taken.

## Procedure

The project proceeds as follows:
- Implement a Basic Driving Agent - have the smartcab take random actions, without responding to penalties
- Inform the Driving Agent - determine the information the smartcab needs to drive safely, without excessive extraneous information
- Implement a Q-learning Driving Agent - teach the smartcab to learn
- Improve the Q-learning Driving Agent - adjust parameters to optimize learning

## Technologies

This project was completed using Python 2.7. Matplotlib was used for visualizations.

## Challenges

The main challenge in this project is optimizing the Q-learning agent. There are many parameters that can be modified, and for best results you need to really understand how these parameters affect learning. Some important parameters are:

- 'alpha': this parameter is known as the learning rate. It may be thought that having a high learning rate is the best way to learn, but that isn't so. The learning rate is multiplied by the reward for each action taken and added to the accumulated value associated with that action. As such, it can also be thought of as how well the learning agent remembers. For the smartcab to learn properly, alpha needs to decay to ensure both past and current experiences are taken into account.
 - 'epsilon': this parameter controls the frequency with which the smartcab takes a random step. This is important to avoid 'local minima,' places where the agent has learned an incorrect action but cannot get enough of a positive reward to escape choosing the action. This could happen if the smartcab goes straight through a green light while the passenger's destination is in a different direction: it gets a small positive reward for obeying traffic laws, but not the large reward it could get for following the waypoint. 
 

## Results

I had alpha and epsilon both starting at 1, with alpha decay 0.985 each trial, and epsilon decay linearly, subtracting 0.005 each time. The training trails stop when epsilon reacher 0.05, so there are 190 trials. Following these 190 trials, testing trials occur, where alpha and epsilon are both 0. On the testing trials, the smartcab scores A+ on both safety and reliability, meaning that it commits no traffic violations and always reaches the destination in time. 
