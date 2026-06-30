---
noteId: "67af6b00749311f19355cb4285936243"
tags: []
---

# 🎲 Theory of Sample Space

## Introduction

Probability is the mathematics of **uncertainty**. Every time we perform an experiment whose outcome cannot be predicted with complete certainty, we enter the world of probability.

Before calculating probabilities, we must first answer a fundamental question:

> **What are all the possible outcomes of the experiment?**

The complete collection of all possible outcomes is called the **Sample Space**.

It is the starting point of every probability problem and forms the mathematical foundation for statistics, machine learning, artificial intelligence, data science, and decision-making under uncertainty.

---

# Why Do We Need a Sample Space?

Imagine rolling a fair six-sided die.

Before asking:

- What is the probability of getting an even number?
- What is the probability of getting a six?

we must first know every possible outcome.

The possible outcomes are:

$$
S={1,2,3,4,5,6}
$$

This set is called the **sample space**.

Without defining the sample space, probability cannot be computed.

---

# Random Experiment

A **random experiment** is an action or process that produces one outcome from several possible outcomes, but the exact outcome cannot be predicted with certainty before performing the experiment.

### Examples

- Tossing a coin
- Rolling a die
- Drawing a card from a deck
- Predicting tomorrow's weather
- Selecting a customer at random
- Measuring sensor noise
- Predicting whether an email is spam

Although the outcome is uncertain, the set of all possible outcomes is known.

---

# Outcome

An **outcome** is a single possible result of a random experiment.

### Examples

For a coin toss:

$$
H
$$

or

$$
T
$$

For rolling a die:

$$
1
$$

$$
2
$$

$$
3
$$

$$
4
$$

$$
5
$$

$$
6
$$

Each individual result is called an outcome.

---

# Sample Space

A **Sample Space** is the set containing **all possible outcomes** of a random experiment.

It is usually denoted by

$$
S
$$

or

$$
\Omega
$$

Mathematically,

$$
S={\text{All Possible Outcomes}}
$$

---

# Examples of Sample Spaces

## Example 1 — Tossing One Coin

Possible outcomes:

$$
S={H,T}
$$

Number of outcomes:

$$
|S|=2
$$

---

## Example 2 — Rolling One Die

$$
S={1,2,3,4,5,6}
$$

Number of outcomes:

$$
|S|=6
$$

---

## Example 3 — Tossing Two Coins

Possible outcomes:

$$
S=
{
HH,
HT,
TH,
TT
}
$$

Total outcomes:

$$
|S|=4
$$

---

## Example 4 — Rolling Two Dice

Sample space contains

$$
6\times6=36
$$

possible ordered outcomes.

Examples:

$$
(1,1)
$$

$$
(2,5)
$$

$$
(6,6)
$$

---

# Types of Sample Spaces

## 1. Finite Sample Space

Contains a finite number of outcomes.

Example:

Rolling a die

$$
S={1,2,3,4,5,6}
$$

---

## 2. Infinite Sample Space

Contains infinitely many outcomes.

Example:

Number of customers arriving at a store.

$$
S={0,1,2,\ldots}
$$

---

## 3. Countably Infinite Sample Space

The outcomes can be counted one by one.

Example:

Number of emails received today.

---

## 4. Continuous Sample Space

Outcomes are measured over a continuous interval.

Examples:

- Height
- Weight
- Temperature
- Time
- Distance

Example:

$$
S=[0,\infty)
$$

---

# Representation of Sample Spaces

Sample spaces can be represented using:

- Sets
- Tree diagrams
- Tables
- Number lines
- Graphs
- Venn diagrams

The choice depends on the problem.

---

# Sample Space and Sets

Probability is built upon **set theory**.

Since a sample space is a set, we can apply set operations such as:

- Union
- Intersection
- Difference
- Complement

These operations are essential for defining events and computing probabilities.

---

# Cardinality of a Sample Space

The number of outcomes in a sample space is called its **cardinality**.

It is denoted by

$$
|S|
$$

Examples:

Coin:

$$
|S|=2
$$

Die:

$$
|S|=6
$$

Two Dice:

$$
|S|=36
$$

---

# Equally Likely Outcomes

Many introductory probability problems assume every outcome is equally likely.

Examples include:

- Fair coins
- Fair dice
- Shuffled cards

When outcomes are equally likely,

$$
P(E)=
\frac{\text{Number of Favorable Outcomes}}
{\text{Total Number of Outcomes}}
$$

This simple idea forms the basis of classical probability.

---

# Real-World Examples

## Weather Prediction

Possible outcomes:

$$
S=
{
Sunny,
Cloudy,
Rainy,
Snowy
}
$$

---

## Email Classification

$$
S=
{
Spam,
Not\ Spam
}
$$

---

## Autonomous Vehicle

Possible road conditions:

- Dry
- Wet
- Snow
- Ice

These outcomes define the sample space used by decision-making algorithms.

---

## Medical Diagnosis

Possible outcomes:

- Healthy
- Disease Present

Machine learning models estimate probabilities over this sample space.

---

# Applications in Artificial Intelligence

Sample spaces appear in almost every AI domain.

### Machine Learning

- Classification problems
- Prediction models
- Uncertainty estimation

### Natural Language Processing

Possible next words form a sample space.

Language models estimate probabilities over this space.

### Computer Vision

Object detection considers possible object classes as outcomes.

### Robotics

Robots model possible future states using sample spaces.

### Reinforcement Learning

The environment is described using:

- State Space
- Action Space

Both are generalized sample spaces.

### Large Language Models

Every generated token is selected from a sample space consisting of all possible vocabulary tokens.

Probability distributions over this sample space determine the next generated word.

---

# Common Mistakes

- Confusing an outcome with the sample space.
- Forgetting to include all possible outcomes.
- Counting duplicate outcomes.
- Assuming outcomes are equally likely when they are not.
- Mixing continuous and discrete sample spaces.

---

# Summary

In this chapter, we learned:

- What a random experiment is.
- What an outcome represents.
- How to define a sample space.
- Types of sample spaces.
- Cardinality of a sample space.
- Sample space representations.
- Classical probability using sample spaces.
- Real-world applications.
- AI applications.

Understanding the **sample space** is the first and most important step in probability theory. Every event, probability distribution, Bayesian model, and machine learning algorithm begins by defining the complete set of possible outcomes. It provides the mathematical framework for reasoning under uncertainty and serves as the foundation for the rest of probability and statistics.
