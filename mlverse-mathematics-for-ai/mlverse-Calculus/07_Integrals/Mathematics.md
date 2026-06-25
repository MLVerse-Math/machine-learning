---
noteId: "8a5bd470704e11f1afaab1217c55b3ec"
tags: []

---

# Integrals

## Learning Objectives

After completing this chapter, learners should understand:

- Antiderivatives
- Indefinite Integrals
- Definite Integrals
- Area Under Curves
- Fundamental Theorem of Calculus
- Riemann Sums
- Numerical Integration
- Double Integrals
- Triple Integrals
- Probability Integrals
- Expected Value
- Integrals in Machine Learning and AI

---

# 1. Motivation

Derivatives tell us how things change.

Integrals tell us how things accumulate.

**Examples:**

- Total distance traveled
- Total revenue earned
- Total probability mass
- Total reward in Reinforcement Learning

**Question:**

If we know the rate of change, can we recover the original quantity?

Integration provides the answer.

---

# 2. What is an Integral?

Integration is the reverse operation of differentiation.

If:

$$F'(x) = f(x)$$

then:

$$\int f(x) \, dx = F(x) + C$$

where:

- $F(x)$ is an **antiderivative**
- $C$ is the **constant of integration**

---

# 3. Antiderivatives

**Definition:**

An antiderivative of a function is another function whose derivative equals the original function.

**Example:**

$$\frac{d}{dx} \left( \frac{x^3}{3} \right) = x^2$$

Therefore:

$$\int x^2 \, dx = \frac{x^3}{3} + C$$

---

# 4. Indefinite Integrals

**General form:**

$$\int f(x) \, dx$$

**Interpretation:**

Find all possible antiderivatives.

**Examples:**

$$\int x^3 \, dx = \frac{x^4}{4} + C$$

$$\int \cos(x) \, dx = \sin(x) + C$$

---

# 5. Constant of Integration

Why do we add $+C$?

Because differentiation removes constants.

**Example:**

$$\frac{d}{dx}(x^2 + 5) = 2x$$

$$\frac{d}{dx}(x^2 + 10) = 2x$$

Therefore:

$$\int 2x \, dx = x^2 + C$$

---

# 6. Definite Integrals

**Definition:**

$$\int_a^b f(x) \, dx$$

Measures accumulated quantity between limits.

**Example:**

$$\int_0^2 x^2 \, dx$$

Using antiderivative:

$$F(x) = \frac{x^3}{3}$$

Result:

$$F(2) - F(0) = \frac{8}{3}$$

---

# 7. Geometric Interpretation

A definite integral represents **area under a curve**.

**Visualize:**

- Function curve
- Area between curve and x-axis
- Integration limits

Explain positive and negative area.

---

# 8. Fundamental Theorem of Calculus

One of the most important theorems in mathematics.

If:

$$F'(x) = f(x)$$

Then:

$$\int_a^b f(x) \, dx = F(b) - F(a)$$

Explain how differentiation and integration are inverse operations.

---

# 9. Basic Integration Rules

## Power Rule

$$\int x^n \, dx = \frac{x^{n+1}}{n+1} + C, \quad n \neq -1$$

**Examples:**

$$\int x^2 \, dx = \frac{x^3}{3} + C$$

$$\int x^5 \, dx = \frac{x^6}{6} + C$$

---

## Constant Rule

$$\int c \, dx = cx + C$$

---

## Sum Rule

$$\int (f(x) + g(x)) \, dx = \int f(x) \, dx + \int g(x) \, dx$$

---

# 10. Trigonometric Integrals

**Examples:**

$$\int \sin(x) \, dx = -\cos(x) + C$$

$$\int \cos(x) \, dx = \sin(x) + C$$

Discuss intuition.

---

# 11. Exponential Integrals

**Examples:**

$$\int e^x \, dx = e^x + C$$

$$\int a^x \, dx = \frac{a^x}{\ln(a)} + C$$

---

# 12. Logarithmic Integrals

Special case:

$$\int \frac{1}{x} \, dx = \ln|x| + C$$

Explain why it differs from the power rule.

---

# 13. Riemann Sums

Before integration, approximate area using rectangles.

**Formula:**

$$\sum_{i=1}^{n} f(x_i) \Delta x$$

Explain:

- Left Riemann Sum
- Right Riemann Sum
- Midpoint Rule

Show convergence as $n \rightarrow \infty$.

---

# 14. Numerical Integration

When symbolic integration is difficult.

**Methods:**

- Rectangle Rule
- Midpoint Rule
- Trapezoidal Rule
- Simpson's Rule

Discuss accuracy comparisons.

---

# 15. Double Integrals

Functions of two variables:

$$f(x, y)$$

**Integral:**

$$\iint_R f(x, y) \, dA$$

**Interpretation:**

Volume under a surface.

---

# 16. Triple Integrals

Functions of three variables.

**Formula:**

$$\iiint_V f(x, y, z) \, dV$$

**Interpretation:**

Accumulated quantity in 3D space.

---

# 17. Integrals in Probability

Probability Density Functions must satisfy:

$$\int_{-\infty}^{\infty} p(x) \, dx = 1$$

Explain normalization.

---

# 18. Expected Value

Continuous random variable:

$$E[X] = \int_{-\infty}^{\infty} x \, p(x) \, dx$$

Interpret expected value geometrically.

---

# 19. Gaussian Distribution

Introduce:

$$p(x) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$

Explain why integration determines probabilities.

---

# 20. Bayesian Learning

Integrals appear in Bayesian inference.

**Example:**

Posterior normalization.

Discuss conceptually.

---

# 21. Reinforcement Learning

Expected reward:

$$E[R]$$

depends on integrating over possible outcomes.

Explain intuition.

---

# 22. Neural ODEs

Modern AI uses continuous-time models.

Neural ODEs solve:

$$\frac{dh}{dt} = f(h, t, \theta)$$

using integration.

Explain significance.

---

# 23. Physics-Informed Neural Networks

PINNs combine:

- Differential Equations
- Integration
- Deep Learning

Discuss how integrals help enforce physical laws.

---

# 24. Integrals in Generative AI

**Applications:**

- Diffusion Models
- Continuous Probability Distributions
- Variational Inference

Explain high-level intuition.

---

# 25. Common Mistakes

- Forgetting $+C$
- Wrong power rule application
- Confusing definite and indefinite integrals
- Ignoring integration limits
- Sign errors

---

# 26. Summary

**Key Ideas:**

- Antiderivatives
- Indefinite Integrals
- Definite Integrals
- Area Under Curves
- Fundamental Theorem of Calculus
- Riemann Sums
- Numerical Integration
- Double Integrals
- Triple Integrals
- Probability Density Functions
- Expected Value
- Bayesian Learning
- Reinforcement Learning
- Neural ODEs
- Generative AI

**Final Insight:**

Integrals are the mathematical language of accumulation. They connect Calculus to Probability, Statistics, Optimization, Reinforcement Learning, Deep Learning, and modern AI systems.
