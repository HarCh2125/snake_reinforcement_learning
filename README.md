# Snake Reinforcement Learning
Implemented a reinforement learning agent for the famous Snake game. I have used Deep Q Learning for this task.

## REWARD
<ul>
    <li> Eat food: +10
    <li> Game Over: -10
    <li> Else: 0
</ul>

## ACTION
<ul>
    <li> [1, 0, 0] : Straight
    <li> [0, 1, 0] : Right
    <li> [0, 0, 1] : Left
</ul>
Notice that this scheme does not allow a 180 degree turn!

## STATE
11 values:

    [danger straight, danger right, danger left,

    direction left, direction right,
    direction up, direction down,

    food left, food right,
    food up, food down]

## MODEL
A neural network with linear activation from state to action, having one hidden layer with 256 neurons in between.

## DEEP Q LEARNING
Q value: Quality of action

<ul>
    <li> Initialise the Q value
    <li> Choose an action by calling the model (or a random move at the beginning at the game). Here, we face the tradeoff between <i><b>exploration</b></i> and <i><b>exploitation</b></i>
    <li> Perform the action
    <li> Measure the reward
    <li> Update the Q value and train the value. Iterate over!
</ul>

#### The Bellman Equation
$NewQ(s, a) = Q(s, a) + \alpha[R(s, a) + \gamma\, maxQ'(s', a') - Q(s, a)]$

#### Loss function
MSE Loss: $|Q_{new} - Q|^2$

## INSTALLING REQUIRED LIBRARIES
The libraries required for this project are:
<ul>
    <li> Pygame
    <li> PyTorch
    <li> NumPy
    <li> Matplotlib
    <li> IPython
</ul>

They can be installed by using the `requirements.txt` file using the following command in your terminal:
```
pip install -r requirements.txt
```

## RUNNING THE PROJECT
After you have installed the libraries, the project can be run by running the given command in your terminal:
```
python agent.py
```
***