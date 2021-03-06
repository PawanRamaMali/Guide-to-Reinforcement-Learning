
# Guide-to-Reinforcement-Learning

Reinforcement learning is the training of machine learning models to make a sequence of decisions. The agent learns to achieve a goal in an uncertain, potentially complex environment. The computer employs trial and error to come up with a solution to the problem. To get the machine to do what the programmer wants, the artificial intelligence gets either rewards or penalties for the actions it performs. Its goal is to maximize the total reward.


```
```
# What is Reinforcement Learning?

Machine Learning does not include the process of taking actions and interacting with an environment like we humans do. 
As intelligent human beings, what we constantly keep doing is the following:
  * We observe some input, whether it's what we see with our eyes, what we hear with our ears, or what we remember in our memory.
  * These inputs are then processed in our brain.
  * Eventually, we make decisions and take actions.
This process of interacting with an environment is what we are trying to reproduce in terms of Artificial Intelligence. And to that extent, the branch of AI that works on this is Reinforcement Learning.


## The five principles of Reinforcement Learning

Here are the five fundamental principles:

* 1: The input and output system
* 2: The reward
* 3: The AI environment
* 4: The Markov decision process
* 5: Training and inference



```
```
### Principle #1 – The input and output system

Reinforcement Learning models, will take something as input, and will return another thing as output.

* The input is also called the state, or input state. 
* The output is the action performed by the AI. 
* And in the middle, we have a function (policy) that takes a state as input and returns an action as output.

Summary : It is an intelligent system (a policy) that takes some elements as input, does its magic in the middle, and returns some actions to perform as output. 

Remember that the inputs are also called the states.

```
```
### Principle #2 – The reward

The reward is simply a metric that will tell the AI how well it does over time.

* The simplest example is a binary reward: 0 or 1. 
* Imagine an AI that has to guess an outcome. 
* If the guess is right, the reward will be 1, and if the guess is wrong, the reward will be 0. 
* This could very well be the reward system defined for an AI; yes as simple as that!
* A reward doesn't have to be binary, however. It can be continuous.

Different AIs will have different reward structures.

The ultimate goal of the AI will always be to maximize the accumulated reward over time.

```
```
### Principle #3 – The AI environment

It is a very simple framework where we define three things at each time (t):

* The input (the state)
* The output (the action)
* The reward (the performance metric)

We always define an environment composed of the preceding elements. It is, however, important to understand that there are more than these three elements in a given AI environment.

For example, In the example of a self-driving car, the environment will also contain all the roads along which the AI is driving and the objects that surround those roads. But what you will always find in common when building any AI, are the three elements of state, action, and reward. 


```
```
### Principle #4 – The Markov decision process

The Markov decision process is a process that models how the AI interacts with the environment over time. 

The process starts at t = 0, and then, at each next iteration, meaning at t = 1, t = 2, … t = n units of time (where the unit can be anything, for example, 1 second), the AI follows the same format of transition:

* The AI observes the current state
* The AI performs the action
* The AI receives the reward
* The AI enters the following state

The goal of the AI is always the same in Reinforcement Learning: it is to maximize the accumulated rewards over time, that is, the sum of all the received at each transition.

The following graphic will help you visualize and remember an MDP better, the basis of Reinforcement Learning models:

![image](https://user-images.githubusercontent.com/11299574/126190399-d588b7fb-aa0b-4ecd-9ddd-a3a3c06a4387.png)

       Figure 1: The Markov Decision process
       

### Principle #5 – Training and inference

The last principle is training and inference; in training, the AI learns, and in inference, it predicts.

When building an AI, there is a time for the training mode, and a separate time for inference mode. 

* Training mode

The very first step of building an AI is to build an environment in which the input states, the output actions, and a system of rewards are clearly defined. 
Inside this environment we will build an AI to interact with it, trying to maximize the total reward accumulated over time.

There will be a preliminary (and long) period of time during which the AI will be trained to do that. 
That period of time is called the training.
The AI tries to accomplish a certain goal over and over again until it succeeds. 
After each attempt, the parameters of the AI model are modified in order to do better at the next attempt.

For example, let's say we're building a self-driving car and we want it to go from point A to point B. Let's also imagine that there are some obstacles that we want our self-driving car to avoid. Here is how the training process happens:

It's just like we would train a dog to sit: we give the dog a treat or say "good boy" (positive reward) if the dog sits. 
And we give the dog nothing if the dog disobeys (negative reward). That process is training, and it works the same way in Reinforcement Learning.

At the end of the attempt (also called an episode), we modify the parameters of the model in order to do better next time. 
The parameters are modified intelligently, either iteratively through equations (Q-Learning), or by using Machine Learning and Deep Learning techniques such as stochastic gradient descent or backpropagation. 
We repeat steps again and again, until we reach the desired performance; that is, until we have our AI!
So, that's training. 

* Inference mode

Inference mode simply comes after AI is fully trained and ready to perform well. 
It will simply consist of interacting with the environment by performing the actions to accomplish the goal the AI was trained to achieve before in training mode. 
In inference mode, no parameters are modified at the end of each episode.

For example, imagine we have an AI company that builds customized AI solutions for businesses, and one of our clients asked us to build an AI to optimize the flows in a smart grid. First, we will enter an R&D phase during which we would train our AI to optimize these flows (training mode), and as soon as we have reached a good level of performance, we will deliver our AI to our client and go into production. 
Our AI would regulate the flows in the smart grid only by observing the current states of the grid and performing the actions it has been trained to do. That's inference mode.

Sometimes, the environment is subject to change, in which case you have to alternate fast between training and inference modes so that your AI can adapt to the new changes in the environment. An even better solution is to train your AI model every day, and go into inference mode with the most recently trained model.


```
```
## The multi-armed bandit problem

Imagine we are in a room containing five slot machines. 
For each of them the game is the same: we bet a certain amount of money, say 1 dollar, we pull the arm, and then the machine will either take our money, or give us twice our money back.
Let's say that if the machine takes our money, our reward is -1, and if the machine returns us twice our money, our reward is +1.

We've defined the rewards; we'll define the states (inputs) and actions (outputs) later. Now, still in the process of defining the environment, let's say that we know, somehow, that one of these machines has a higher probability of giving us a +1 reward than the others when we pull its arm. It doesn't matter how we know this info, but it must be part of the problem assumptions. 

Your goal, as in any AI environment, is to obtain the highest accumulated reward during your time of play. Let's say you are going to bet 1,000 dollars in total, meaning that you are going to bet 1 dollar, 1,000 times, each time by pulling the arm of any of these five slot machines. 

The question is: What should be your strategy, so that after having played 1,000 times, you get the maximum amount of money to take home with you?

The first step of your strategy must be to figure out, in the minimum number of plays, which of these five slot machines has the highest chance of giving you a 1 reward. In other words, you have to quickly figure out the slot machine with the highest success rate. Then, as soon as you figure it out, you simply need to keep playing on that most successful slot machine.

Finding the most successful slot machine is not hard; one simple strategy could be to play 100 times on each of these five slot machines and then, at the end, look at which of them gave you more money. Statistically, this gives you a good chance of finding that most generous slot machine.

The hardest part is to find the best slot machine in a minimum number of trials. This is where our first AI model comes into play.



```
```
## The Thompson Sampling model

* Our problem is trying to find the best slot machine with the highest winning chance out of many. 
* A not-so-optimal solution would be to play 100 rounds on each of our slot machines and see which one has the highest winning rate. 
* A better solution is a method called Thompson Sampling.

Thompson Sampling uses a distribution function, called Beta, that takes two arguments. 
Higher the first argument is, the better our slot machine is, and the higher the second argument is, the worse our slot machine is.


Therefore, we can define this function as:  

   x = B(a,b)

where:

* x – a random choice from our Beta distribution
* B – our Beta function
* a – the first argument
* b – the second argument


```
```
## What is a distribution?

The distribution of a variable is a function that will give, for each value in the possible range of values the variable could take, the probability that this variable is equal to that value.

![image](https://user-images.githubusercontent.com/11299574/126373240-eac36761-00eb-4281-88d6-0c28e4dd377b.png)

Figure 1: The normal distribution

In any distribution, on the x-axis you have the range of values the variable could take, and on the y-axis you have the probability that the variable is equal to each value.


### Code simulation to select Best slot machine using Thompson Sampling method

``` Python 
# Importing the libraries
import numpy as np

# Setting conversion rates and the number of samples
conversionRates = [0.15, 0.04, 0.13, 0.11, 0.05]  # list of winning chances is conversionRates
N = 10000  # number of samples, N
d = len(conversionRates)  # d is the length of your conversion rates list; that is, the number of slot machines.

# Creating the dataset
X = np.zeros((N, d))  # Create a 2d-array full of zeros, of size N * d
# An array with N (in this case 10000) rows and d (in this case 5) columns.

# for loop, iterate through every row in that 2d-array X
for i in range(N):  # time step i - you have won or not by playing a certain slot
    for j in range(d):
        if np.random.rand() < conversionRates[j]:
            # check if a random float number from range (0,1) is smaller than
            # the conversion rate for the corresponding slot machine.
            X[i][j] = 1

# Making arrays to count our losses and wins
# nPosReward (number of wins) and nNegReward (number of losses).
nPosReward = np.zeros(d)
nNegReward = np.zeros(d)

# Taking our best slot machine through beta distribution and updating its losses and wins
# for loop that will iterate through every sample in our dataset and choose the best slot machine.
for i in range(N):
    # selected, which will tell you which slot machine was chosen, and maxRandom, which you will use to get the
    # highest Beta distribution guess across all slot machines
    selected = 0
    maxRandom = 0

    for j in range(d):  # core of Thompson Sampling
        # np.random.beta(a,b), returns random guess
        randomBeta = np.random.beta(nPosReward[j] + 1, nNegReward[j] + 1)
        if randomBeta > maxRandom:
            maxRandom = randomBeta
            selected = j

        if X[i][selected] == 1:
            nPosReward[selected] += 1
        else:
            nNegReward[selected] += 1

    # Showing which slot machine is considered the best
    nSelected = nPosReward + nNegReward

for i in range(d):
    # Display how many times each slot machine was chosen by your algorithm
    print('Machine number ' + str(i + 1) + ' was selected ' + str(nSelected[i]) + ' times')

print('Conclusion: Best machine is machine number ' + str(np.argmax(nSelected) + 1))

```


```
```
## Summary of Thompson Sampling model

Thompson Sampling is a powerful sampling technique that enables you to quickly figure out the highest of a number of unknown conversion rates.
It is always applied in the same frame, called the multi-armed bandit problem, which in the classic sense is composed of several slot machines, each one having a different conversion rate of positive outcomes.


```
```
## Q Learning 

* is a Reinforcement Learning model.
* works on the inputs (states) and outputs (actions) principle.
* works on a predefined environment, including the states (the inputs), the actions (the outputs), and the rewards.
* is modeled by a Markov decision process.
* uses a training mode, during which the parameters that are learned are called the Q-values, and an inference mode.

Two more fundamentals specific to Q-learning:

* There are a finite number of states (there is not an infinity of possible inputs).
* There are a finite number of actions (only a certain number of actions can be performed).

## Q Learning Summary 

* Q-learning model is only applied to environments that have a finite number of input states and a finite number of possible actions to perform.

* The AI learns Q-values through an iterative process, so that the higher the Q-value of a (state, action) pair, the closer the AI gets to the top reward.

* At each iteration the Q-values are updated through the Bellman equation, which simply consists of adding the temporal difference, discounted by a learning rate factor.

```
```
## What are CNNs used for?

* CNNs are mostly used with images or videos, and sometimes with text to tackle Natural Language Processing (NLP) problems. 
* They are often used in object recognition, for example, predicting whether there is a cat or a dog in a picture or video. 
* They are also often used with deep Q-learning, when the environment returns 2D states of itself, for example, when we are trying to build a self-driving car that reads outputs from cameras around it.

## Sources : 

* AI Crash Course | Packt | https://subscription.packtpub.com/book/data/9781838645359 
