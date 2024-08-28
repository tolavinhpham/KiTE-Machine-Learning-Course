# Introduction

Until recently, nearly every computer program that you might have interacted with during an ordinary day was coded up as a rigid set of rules specifying precisely how it should behave.

To build the brains of our application, we might enumerate all the common events that our program should handle.

Sometimes the program that we are looking for follows a pattern that changes over time, so there is no fixed right answer (ex., a program that predicts tomorrow’s weather, or a program that presents users with products that they are likely to enjoy, etc.).

At other times, the relationship between factors may be too complicated, requiring thousands or millions of computations and following unknown principles.

Machine learning is the study of algorithms that can learn from experience.

![[Pasted image 20240713165731.png]]

It is only recently that AI has been in the limelight, mostly due to solutions to problems that were considered intractable previously and that are directly related to consumers. Many of such advances are attributed to deep learning.
- Intelligent assistants, such as Apple’s Siri, Amazon’s Alexa, and Google’s assistant, are able to respond to spoken requests with a reasonable degree of accuracy.
- A key ingredient in digital assistants is their ability to recognize speech accurately.
- Object recognition has likewise come a long way.
- Prowess in games used to provide a measuring stick for human ability.
- Another indication of progress in AI is the advent of self-driving vehicles.

Robotics, logistics, computational biology, particle physics, and astronomy owe some of their most impressive recent advances at least in parts to machine learning.

---
# Definitions and Examples

![[Pasted image 20240711110038.png]]

Following steps:
- collect a huge _dataset_ containing examples of audio snippets and associated labels, indicating which snippets contain the wake word.
- do not attempt to design a system _explicitly_ to recognize wake words.
- define a flexible program whose behavior is determined by a number of _parameters._
- use the dataset to determine the best possible parameter values, i.e., those that improve the performance of our program with respect to a chosen performance measure.

Once the parameters are fixed, we call the program a _model_. The “method” that uses our dataset to choose the parameters is called a _learning algorithm_.

_Training_ is the process by which we discover the right value of the _parameters_ for coercing the desired behavior from our model.

![[Pasted image 20240711110102.png]]

---
# Key Components

1. The _data_ that we can learn from.
2. A _model_ of how to transform the data.
3. An _objective function_ that quantifies how well (or badly) the model is doing.
4. An _algorithm_ to adjust the model’s parameters to optimize the objective function.

## Data

In fact, humans have held the desire to analyze data and to predict future outcomes for ages, and it is this desire that is at the root of much of natural science and mathematics. Two examples are the Bernoulli distribution, named after Jacob Bernoulli (1655–1705), and the Gaussian distribution discovered by Carl Friedrich Gauss (1777–1855).

Even in the middle ages, mathematicians had a keen intuition of estimates. For instance, the geometry book of Jacob Köbel (1460–1533) illustrates averaging the length of 16 adult men’s feet to estimate the typical foot length in the population.

![[Pasted image 20240717001335.png]]

Alan Turing (1912–1954) posed the question “*can machines think?*” in his famous paper Computing Machinery and Intelligence (Turing, 1950).

Data must have suitable numerical representations.

Each _example_ (or _data point_, _data instance_, _sample_) typically consists of a set of attributes called _features_ (sometimes called _covariates_ or _inputs_), based on which the model must make its predictions. 

![[Pasted image 20240711213040.png]]

![[Pasted image 20240711213140.png]]

In _supervised learning_ problems, our goal is to predict the value of a special attribute, called the _label_ (or _target_), that is not part of the model’s input.

When every example is characterized by the same number of numerical features, we say that the inputs are fixed-length vectors and we call the (constant) length of the vectors the _dimensionality_ of the data. 

Need to _standardize_ the input data → _Preprocess_. 

It is not enough to have lots of data and to process it cleverly. We need the _right_ data.

## Model

Most machine learning involves transforming the data in some sense.

By _model_, we denote the computational machinery for ingesting data of one type, and spitting out predictions of a possibly different type.

## Objective Functions

We need to have formal measures of how good (or bad) our models are. In machine learning, and optimization more generally, we call these _objective functions_.
 
By convention, we usually define objective functions so that lower is better → *loss functions*.

When trying to predict numerical values, the most common loss function is _squared error_, i.e., the square of the difference between the prediction and the ground truth target. 

For classification, the most common objective is to minimize error rate, i.e., the fraction of examples on which our predictions disagree with the ground truth.

We learn the best values of our model’s parameters by *minimizing the loss* incurred on a set consisting of some number of examples collected for training.

Split the available data into two partitions: 
- the _training dataset_ (or _training set_), for learning model parameters;
- and the _test dataset_ (or _test set_), which is held out for evaluation.

![[Pasted image 20240711212847.png]]

At the end of the day, we typically report how our models perform on both partitions.

When a model performs well on the training set but fails to generalize to unseen data, we say that it is _overfitting_ to the training data.

## Optimization Algorithms

We need an algorithm capable of searching for the best possible parameters for minimizing the loss function. 

Popular optimization algorithms for deep learning are based on an approach called _gradient descent_.

![[Pasted image 20240711212222.png]]

![[Pasted image 20240714212035.png]]

Good learning rate
![[Pasted image 20240716232615.png]]

Very high learning rate
![[Pasted image 20240716232625.png]]

![[Pasted image 20240714212049.png]]

