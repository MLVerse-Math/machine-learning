---
noteId: "aede3a10749311f19355cb4285936243"
tags: []
---

# 📐 Mathematics of Sample Space

# Sample Space

---

## Learning Objectives

After completing this chapter, you will understand:

- The mathematical definition of a sample space
- Random experiments and outcomes
- Set representation of sample spaces
- Finite and infinite sample spaces
- Countable and uncountable sample spaces
- Cardinality of a sample space
- Equally likely outcomes
- Classical probability using sample spaces
- Counting techniques
- Applications in Machine Learning and Artificial Intelligence

---

# 1. Random Experiment

A **random experiment** is an experiment whose outcome cannot be predicted with certainty before it is performed.

Examples include:

- Tossing a coin
- Rolling a die
- Drawing a card
- Predicting tomorrow's weather

Mathematically, we denote a random experiment by

$$
E
$$

where the outcome is unknown before performing the experiment.

---

# 2. Outcome

An **outcome** is a single possible result of a random experiment.

If a die is rolled,

possible outcomes are

$$
1,;2,;3,;4,;5,;6
$$

Each value represents one outcome.

---

# 3. Sample Space

The **Sample Space** is the set of all possible outcomes.

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

# 4. Examples of Sample Spaces

## Example 1

### Tossing a Coin

$$
S={H,T}
$$

Number of outcomes

$$
|S|=2
$$

---

## Example 2

### Rolling a Die

$$
S={1,2,3,4,5,6}
$$

Cardinality

$$
|S|=6
$$

---

## Example 3

### Tossing Two Coins

$$
S=
{
HH,
HT,
TH,
TT
}
$$

Number of outcomes

$$
|S|=4
$$

---

## Example 4

### Rolling Two Dice

The sample space is

$$
S=
{
(1,1),(1,2),\ldots,(6,6)
}
$$

Total outcomes

$$
|S|=36
$$

---

# 5. Types of Sample Space

## Finite Sample Space

Contains a finite number of outcomes.

Example

$$
S={1,2,3,4,5,6}
$$

---

## Infinite Sample Space

Contains infinitely many outcomes.

Example

$$
S={0,1,2,3,\ldots}
$$

---

## Countably Infinite Sample Space

The outcomes can be counted one by one.

Example

$$
S=\mathbb{N}
$$

---

## Continuous Sample Space

Contains infinitely many values within an interval.

Example

$$
S=[0,\infty)
$$

Examples include:

- Height
- Weight
- Temperature
- Time

---

# 6. Set Notation

A sample space is simply a mathematical set.

For example,

$$
S={1,2,3,4,5,6}
$$

An outcome belongs to the sample space.

Example

$$
4\in S
$$

while

$$
8\notin S
$$

---

# 7. Cardinality

The number of elements in a sample space is called its **cardinality**.

Notation

$$
|S|
$$

Examples

Coin

$$
|S|=2
$$

Die

$$
|S|=6
$$

Two Coins

$$
|S|=4
$$

Two Dice

$$
|S|=36
$$

---

# 8. Counting Principle

Suppose

Experiment A has

$$
m
$$

possible outcomes.

Experiment B has

$$
n
$$

possible outcomes.

Then

$$
|S|=m\times n
$$

Example

Rolling two dice

$$
6\times6=36
$$

---

# 9. Equally Likely Outcomes

If every outcome has the same chance of occurring,

then the probability of an event is

$$
P(E)=
\frac{|E|}{|S|}
$$

where

- $|E|$ is the number of favorable outcomes
- $|S|$ is the total number of outcomes

---

# 10. Classical Probability

Suppose

$$
S={1,2,3,4,5,6}
$$

Event

$$
A={2,4,6}
$$

Then

$$
|A|=3
$$

and

$$
|S|=6
$$

Therefore

$$
P(A)=\frac{3}{6}=\frac12
$$

---

# 11. Tree Representation

For two coin tosses

First Toss

↓

Second Toss

Possible outcomes

$$
HH
$$

$$
HT
$$

$$
TH
$$

$$
TT
$$

Total outcomes

$$
4
$$

Tree diagrams are useful for systematically constructing sample spaces.

---

# 12. Cartesian Product

For two experiments

$$
A={a_1,a_2,\ldots,a_m}
$$

and

$$
B={b_1,b_2,\ldots,b_n}
$$

the combined sample space is

$$
A\times B
$$

with

$$
|A\times B|=mn
$$

Example

Rolling two dice

$$
{1,\ldots,6}\times{1,\ldots,6}
$$

---

# 13. Geometric Interpretation

The sample space represents the complete universe of possible outcomes.

Every probability problem begins by defining this universe correctly.

Events are subsets of this universe.

Probabilities are assigned to these subsets.

---

# 14. Applications in AI

Sample spaces are fundamental in:

- Machine Learning Classification
- Bayesian Inference
- Reinforcement Learning
- Robotics
- Computer Vision
- Natural Language Processing
- Hidden Markov Models
- Probabilistic Graphical Models
- Large Language Models

Every prediction made by an AI model is computed over a sample space of possible outcomes.

---

# 15. Mathematical Properties

A valid sample space satisfies:

- Every possible outcome belongs to the sample space.
- Outcomes are mutually distinguishable.
- No outcome is omitted.
- Every event is a subset of the sample space.

Mathematically,

$$
E\subseteq S
$$

---

# 16. Summary

The mathematical ideas introduced in this chapter include:

- Random Experiment
- Outcome
- Sample Space
- Set Representation
- Cardinality
- Counting Principle
- Cartesian Product
- Equally Likely Outcomes
- Classical Probability
- Set Inclusion

These concepts form the mathematical foundation for the remaining topics in probability, including **Events**, **Conditional Probability**, **Bayes' Theorem**, **Random Variables**, **Probability Distributions**, and **Markov Models**. A clear understanding of sample spaces is essential for building probabilistic reasoning systems used in modern Artificial Intelligence and Machine Learning.
