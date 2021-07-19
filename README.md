
# Guide-to-Reinforcement-Learning

Reinforcement learning is the training of machine learning models to make a sequence of decisions. The agent learns to achieve a goal in an uncertain, potentially complex environment. The computer employs trial and error to come up with a solution to the problem. To get the machine to do what the programmer wants, the artificial intelligence gets either rewards or penalties for the actions it performs. Its goal is to maximize the total reward.


### The five principles of Reinforcement Learning

Here are the five fundamental principles:

* 1: The input and output system
* 2: The reward
* 3: The AI environment
* 4: The Markov decision process
* 5: Training and inference

```
```
### What is Reinforcement Learning?

Machine Learning does not include the process of taking actions and interacting with an environment like we humans do. 
As intelligent human beings, what we constantly keep doing is the following:
  * We observe some input, whether it's what we see with our eyes, what we hear with our ears, or what we remember in our memory.
  * These inputs are then processed in our brain.
  * Eventually, we make decisions and take actions.
This process of interacting with an environment is what we are trying to reproduce in terms of Artificial Intelligence. And to that extent, the branch of AI that works on this is Reinforcement Learning.

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
## Principle #4 – The Markov decision process

The Markov decision process is a process that models how the AI interacts with the environment over time. 

The process starts at t = 0, and then, at each next iteration, meaning at t = 1, t = 2, … t = n units of time (where the unit can be anything, for example, 1 second), the AI follows the same format of transition:

* The AI observes the current state
* The AI performs the action
* The AI receives the reward
* The AI enters the following state
* 
The goal of the AI is always the same in Reinforcement Learning: it is to maximize the accumulated rewards over time, that is, the sum of all the received at each transition.

The following graphic will help you visualize and remember an MDP better, the basis of Reinforcement Learning models:

![image](https://user-images.githubusercontent.com/11299574/126190399-d588b7fb-aa0b-4ecd-9ddd-a3a3c06a4387.png)
Figure 1: The Markov Decision process

The last principle is training and inference; in training, the AI learns, and in inference, it predicts.



