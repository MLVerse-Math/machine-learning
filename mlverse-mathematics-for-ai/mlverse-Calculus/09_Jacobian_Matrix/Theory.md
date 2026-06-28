---
noteId: "e6c8766072aa11f1a976cfa2eab379f5"
tags: []
---

# Jacobian Matrix Theory

## What is the Jacobian Matrix?

The Jacobian Matrix generalizes derivatives to vector-valued functions.

Instead of measuring how one output changes, it measures how multiple outputs change with respect to multiple inputs.

---

## Mathematical Definition

For

$$
F:\mathbb{R}^n\rightarrow\mathbb{R}^m
$$

the Jacobian is

$$
J=
\left[
\frac{\partial f_i}{\partial x_j}
\right]
$$

---

## Why It Matters

The Jacobian captures the local behavior of multivariable systems.

It is used to:

- Approximate nonlinear functions
- Compute gradients
- Perform coordinate transformations
- Train neural networks
- Model robot motion

---

## Intuition

Imagine stretching a rubber sheet.

The Jacobian describes how every tiny neighborhood is stretched, compressed, rotated, or sheared.
