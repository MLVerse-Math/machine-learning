---
noteId: "c02d64b078ff11f182b133857b56b558"
tags: []

---

# Mathematics of Events

> **MLVerse-Math · Chapter 02 — Events**  
> A Beginner → Intermediate → Advanced mathematical journey through the language of probability.

---

## Learning Objectives

By the end of this chapter, you should be able to:

1. distinguish an **outcome**, **sample space**, and **event**;
2. represent events using precise **set notation**;
3. classify events as simple, compound, certain, impossible, complementary, mutually exclusive, exhaustive, equally likely, or independent;
4. perform event algebra using union, intersection, difference, and complement;
5. apply the major algebraic laws of events, including **De Morgan's laws**;
6. interpret events geometrically with regions and Venn diagrams;
7. compute probabilities of events in finite equally likely sample spaces;
8. derive and use the union and complement rules;
9. recognize event-based reasoning inside statistics, machine learning, AI, and LLM systems.

---

# 1. Introduction

## 1.1 What is an Event?

Probability begins with uncertainty. We observe an experiment whose exact result is not known in advance:

- a coin is tossed;
- a die is rolled;
- tomorrow's weather is observed;
- an email is classified as spam or not spam;
- a medical test returns positive or negative;
- a language model generates the next token.

Each possible result is called an **outcome**. A collection of outcomes that satisfies some condition is called an **event**.

> **Intuition:** An event is a mathematical statement about what may happen.

For example, when rolling a six-sided die:

- “the die shows 4” is an event;
- “the result is even” is an event;
- “the result is greater than 3” is an event;
- “the result is 9” is an impossible event.

Events convert natural-language questions into precise mathematical objects.

---

## 1.2 Why Events Matter in Probability

Probability does not usually assign uncertainty to vague sentences. It assigns probability to well-defined events.

If $E$ is an event, then

$$
P(E)
$$

means the probability that event $E$ occurs.

Examples:

$$
P(\text{rain tomorrow})
$$

$$
P(\text{transaction is fraudulent})
$$

$$
P(\text{predicted class is correct})
$$

$$
P(\text{next token is ``the''})
$$

Thus, events are the bridge between:

1. an uncertain experiment;
2. a mathematical set of possible outcomes;
3. a numerical probability.

---

## 1.3 Relationship Between Sample Space and Events

The **sample space** contains every outcome under consideration. An event selects some of those outcomes.

Let

$$
S = \{1,2,3,4,5,6\}
$$

be the sample space for one fair die roll.

The event “an even number occurs” is

$$
E = \{2,4,6\}.
$$

Because every outcome in $E$ is also in $S$,

$$
E \subseteq S.
$$

This subset relationship is the central mathematical idea of the chapter.

---

## 1.4 Why AI Engineers Should Understand Events

Many AI problems can be expressed as events.

| AI problem | Possible event |
|---|---|
| Binary classification | $E=\{\text{model predicts positive}\}$ |
| Computer vision | $E=\{\text{image contains a pedestrian}\}$ |
| NLP | $E=\{\text{sentence expresses positive sentiment}\}$ |
| Fraud detection | $E=\{\text{transaction is fraudulent}\}$ |
| Reinforcement learning | $E=\{\text{agent reaches goal before timeout}\}$ |
| Autonomous driving | $E=\{\text{collision occurs within 3 s}\}$ |
| LLM generation | $E=\{X_{t+1}\in V_{\text{code}}\}$ |

Understanding events is essential before studying:

- conditional probability;
- Bayes' theorem;
- random variables;
- likelihood;
- Bayesian networks;
- stochastic processes;
- decision theory;
- probabilistic machine learning.

---

# 2. Mathematical Definition

## 2.1 Sample Space

A **sample space** is the set of all outcomes considered possible for an experiment.

It is commonly denoted by

$$
S
$$

or, in more advanced probability theory,

$$
\Omega.
$$

For one coin toss:

$$
S = \{H,T\}.
$$

For one six-sided die roll:

$$
S = \{1,2,3,4,5,6\}.
$$

---

## 2.2 Outcome

An **outcome** is one individual element of the sample space.

If

$$
S = \{1,2,3,4,5,6\},
$$

then

$$
\omega = 4
$$

is one outcome, and

$$
4 \in S.
$$

In advanced notation, an elementary outcome is often written as

$$
\omega \in \Omega.
$$

---

## 2.3 Event

An **event** is a subset of the sample space.

$$
\boxed{E \subseteq S}
$$

Equivalently, with $\Omega$ notation,

$$
E \subseteq \Omega.
$$

An event occurs when the observed outcome belongs to that event.

If the realized outcome is $\omega$, then

$$
E \text{ occurs } \iff \omega \in E.
$$

### Example

Suppose

$$
S = \{1,2,3,4,5,6\}
$$

and define

$$
E = \{2,4,6\}.
$$

Then:

- if $\omega=4$, event $E$ occurs because $4\in E$;
- if $\omega=3$, event $E$ does not occur because $3\notin E$.

---

## 2.4 Intuition: Events as Filters

Think of the sample space as a database of all possible outcomes. An event acts like a Boolean filter.

For a die roll,

$$
S=\{1,2,3,4,5,6\}.
$$

Define

$$
E=\{x\in S:x\text{ is even}\}.
$$

Applying the condition “is even” gives

$$
E=\{2,4,6\}.
$$

This set-builder viewpoint is extremely useful:

$$
E=\{\omega\in S:\text{condition on }\omega\text{ is true}\}.
$$

AI systems frequently use exactly this logic when defining threshold events, error events, safety events, or classification events.

---

## 2.5 Event Space: A More Advanced View

If $S$ is the sample space, the collection of events is called an **event space**.

For a finite sample space, one may often use the power set

$$
\mathcal{P}(S),
$$

which contains every subset of $S$.

If

$$
S=\{H,T\},
$$

then

$$
\mathcal{P}(S)
=
\{\varnothing,\{H\},\{T\},\{H,T\}\}.
$$

In rigorous probability theory, events belong to a **$\sigma$-algebra** $\mathcal{F}$:

$$
E\in\mathcal{F}\subseteq\mathcal{P}(S).
$$

A probability model is then written as

$$
(S,\mathcal{F},P).
$$

> **Advanced note:** For finite introductory problems, treating every subset as an event is usually sufficient. For infinite or continuous spaces, measurable event collections become important.

---

# 3. Examples

## 3.1 Coin Toss

For one coin toss,

$$
S=\{H,T\}.
$$

Event “Head occurs”:

$$
A=\{H\}.
$$

Event “Tail occurs”:

$$
B=\{T\}.
$$

For two coin tosses,

$$
S=\{HH,HT,TH,TT\}.
$$

Event “exactly one head occurs”:

$$
E=\{HT,TH\}.
$$

Event “at least one head occurs”:

$$
F=\{HH,HT,TH\}.
$$

---

## 3.2 Dice Roll

For one die roll,

$$
S=\{1,2,3,4,5,6\}.
$$

Event “even outcome”:

$$
A=\{2,4,6\}.
$$

Event “outcome greater than 4”:

$$
B=\{5,6\}.
$$

Event “prime outcome”:

$$
C=\{2,3,5\}.
$$

---

## 3.3 Card Drawing

For a standard 52-card deck, let

$$
S=\{\text{all 52 distinct cards}\}.
$$

Event “draw a heart”:

$$
H=\{A\heartsuit,2\heartsuit,\dots,K\heartsuit\}.
$$

Hence

$$
|H|=13.
$$

Event “draw a king”:

$$
K=\{K\heartsuit,K\diamondsuit,K\clubsuit,K\spadesuit\}.
$$

Event “draw a red king”:

$$
R_K=H_K\cup D_K
=\{K\heartsuit,K\diamondsuit\}.
$$

---

## 3.4 Weather Prediction

Suppose tomorrow's simplified weather state belongs to

$$
S=\{\text{sunny},\text{cloudy},\text{rainy},\text{stormy}\}.
$$

Event “precipitation occurs”:

$$
P=\{\text{rainy},\text{stormy}\}.
$$

Event “non-severe weather”:

$$
N=\{\text{sunny},\text{cloudy},\text{rainy}\}.
$$

---

## 3.5 Email Classification

Suppose a simplified classifier assigns one class from

$$
S=\{\text{spam},\text{promotion},\text{social},\text{primary}\}.
$$

Event “email is unwanted”:

$$
U=\{\text{spam},\text{promotion}\}.
$$

Event “email is personal/non-promotional”:

$$
N=\{\text{social},\text{primary}\}.
$$

For a probabilistic classifier with output score $p_{\text{spam}}(x)$, a threshold event may be

$$
E=\{x:p_{\text{spam}}(x)\ge 0.9\}.
$$

This illustrates how events can be defined by numeric conditions, not only by explicit enumeration.

---

# 4. Types of Events

## 4.1 Simple Event

A **simple event** contains exactly one outcome.

$$
|E|=1.
$$

Example for a die:

$$
E=\{4\}.
$$

> **Intuition:** A simple event identifies one exact possible result.

---

## 4.2 Compound Event

A **compound event** contains two or more outcomes.

$$
|E|\ge 2.
$$

Example:

$$
E=\{2,4,6\}.
$$

This event represents “the die result is even.”

---

## 4.3 Certain Event

The **certain event** is the entire sample space.

$$
E=S.
$$

Therefore,

$$
P(E)=P(S)=1.
$$

Example:

$$
E=\{\text{die result is between 1 and 6}\}=S.
$$

---

## 4.4 Impossible Event

The **impossible event** contains no outcomes.

$$
E=\varnothing.
$$

Therefore,

$$
P(E)=P(\varnothing)=0.
$$

Example for a standard die:

$$
E=\{x\in S:x=9\}=\varnothing.
$$

---

## 4.5 Complementary Event

The complement of $A$ contains every outcome in $S$ that is not in $A$.

$$
A^c=S\setminus A.
$$

Example:

$$
S=\{1,2,3,4,5,6\},
$$

$$
A=\{2,4,6\}.
$$

Then

$$
A^c=\{1,3,5\}.
$$

The pair $A$ and $A^c$ satisfies

$$
A\cup A^c=S
$$

and

$$
A\cap A^c=\varnothing.
$$

---

## 4.6 Mutually Exclusive Events

Two events are **mutually exclusive** or **disjoint** if they cannot occur simultaneously.

$$
A\cap B=\varnothing.
$$

Example for a die:

$$
A=\{1,3,5\},
$$

$$
B=\{2,4,6\}.
$$

Then

$$
A\cap B=\varnothing.
$$

> **Key idea:** Mutually exclusive means “no shared outcomes.”

---

## 4.7 Exhaustive Events

Events $E_1,E_2,\dots,E_n$ are **exhaustive** if together they cover the entire sample space.

$$
\bigcup_{i=1}^{n}E_i=S.
$$

Example:

$$
E_1=\{1,2\},\qquad
E_2=\{3,4\},\qquad
E_3=\{5,6\}.
$$

Then

$$
E_1\cup E_2\cup E_3=S.
$$

Exhaustive events need not always be mutually exclusive.

---

## 4.8 Equally Likely Events

Events are **equally likely** when they have equal probability.

For events $A$ and $B$,

$$
P(A)=P(B).
$$

Example for a fair die:

$$
A=\{1\},\qquad B=\{6\}.
$$

Then

$$
P(A)=P(B)=\frac{1}{6}.
$$

> Equal cardinality alone does not guarantee equal probability unless the underlying outcomes are equally likely.

---

## 4.9 Independent Events — Brief Introduction

Two events $A$ and $B$ are independent when occurrence of one does not change the probability of the other.

Mathematically,

$$
P(A\cap B)=P(A)P(B).
$$

Example: toss a fair coin twice.

Let

$$
A=\{\text{first toss is H}\}
$$

and

$$
B=\{\text{second toss is H}\}.
$$

Then

$$
P(A)=\frac12,
\qquad
P(B)=\frac12,
$$

and

$$
P(A\cap B)=\frac14
=\frac12\cdot\frac12.
$$

Therefore $A$ and $B$ are independent.

> **Warning:** Independent events are generally **not** the same as mutually exclusive events.

---

## 4.10 Comparison Table

| Event type | Mathematical condition | Intuition | Example |
|---|---|---|---|
| Simple | $|E|=1$ | one exact outcome | $\{4\}$ |
| Compound | $|E|\ge 2$ | several outcomes | $\{2,4,6\}$ |
| Certain | $E=S$ | must occur | die result in $\{1,\dots,6\}$ |
| Impossible | $E=\varnothing$ | cannot occur | roll 9 on a standard die |
| Complementary | $A^c=S\setminus A$ | “not $A$” | odd vs. even |
| Mutually exclusive | $A\cap B=\varnothing$ | cannot co-occur | odd and even on one roll |
| Exhaustive | $\cup_i E_i=S$ | cover all possibilities | low/medium/high partitions |
| Equally likely | $P(A)=P(B)$ | same probability | roll 1 vs. roll 6 on fair die |
| Independent | $P(A\cap B)=P(A)P(B)$ | no probabilistic influence | results of separate fair tosses |

---

# 5. Event Algebra

Events are sets, so we can manipulate them using set operations.

Let $A,B\subseteq S$.

---

## 5.1 Union

The union of $A$ and $B$ is

$$
A\cup B.
$$

Definition:

$$
A\cup B
=
\{\omega\in S:\omega\in A\text{ or }\omega\in B\}.
$$

In probability, “or” is normally **inclusive**: $A$, $B$, or both.

### Example

Let

$$
S=\{1,2,3,4,5,6\},
$$

$$
A=\{2,4,6\},
$$

$$
B=\{4,5,6\}.
$$

Then

$$
A\cup B=\{2,4,5,6\}.
$$

### Region intuition

```text
+---------------------------------------+
| Sample space S                        |
|                                       |
|       _______       _______           |
|      /       \_____/       \          |
|     /    A     A∩B     B    \         |
|     \                       /         |
|      \_____________________/          |
|                                       |
+---------------------------------------+

A ∪ B = every point lying in either circle.
```

---

## 5.2 Intersection

The intersection of $A$ and $B$ is

$$
A\cap B.
$$

Definition:

$$
A\cap B
=
\{\omega\in S:\omega\in A\text{ and }\omega\in B\}.
$$

### Example

Using

$$
A=\{2,4,6\},
\qquad
B=\{4,5,6\},
$$

we obtain

$$
A\cap B=\{4,6\}.
$$

### Region intuition

```text
+---------------------------------------+
| Sample space S                        |
|                                       |
|       _______       _______           |
|      /       \#####/       \          |
|     /    A    #####    B    \         |
|     \         #####         /         |
|      \_______/     \_______/          |
|                                       |
+---------------------------------------+

##### = A ∩ B
```

---

## 5.3 Difference

The difference of $A$ and $B$ is

$$
A-B
$$

or equivalently

$$
A\setminus B.
$$

Definition:

$$
A-B
=
\{\omega\in S:\omega\in A\text{ and }\omega\notin B\}.
$$

Also,

$$
A-B=A\cap B^c.
$$

### Example

If

$$
A=\{2,4,6\},
\qquad
B=\{4,5,6\},
$$

then

$$
A-B=\{2\}.
$$

while

$$
B-A=\{5\}.
$$

Therefore, in general,

$$
A-B\ne B-A.
$$

---

## 5.4 Complement

The complement of $A$ is

$$
A^c.
$$

Definition:

$$
A^c
=
\{\omega\in S:\omega\notin A\}.
$$

Equivalently,

$$
A^c=S-A.
$$

### Example

If

$$
S=\{1,2,3,4,5,6\}
$$

and

$$
A=\{2,4,6\},
$$

then

$$
A^c=\{1,3,5\}.
$$

### Region intuition

```text
+---------------------------------------+
|############ Sample space S ###########|
|##########     _________     ##########|
|#########     /         \     #########|
|########     /     A     \     ########|
|########     \           /     ########|
|#########     \_________/     #########|
|#######################################|
+---------------------------------------+

# = A^c, the region inside S but outside A
```

---

## 5.5 Event Algebra in Natural Language

| Natural language | Event notation |
|---|---|
| $A$ or $B$ | $A\cup B$ |
| $A$ and $B$ | $A\cap B$ |
| not $A$ | $A^c$ |
| $A$ but not $B$ | $A-B$ |
| neither $A$ nor $B$ | $(A\cup B)^c$ |
| exactly one of $A$ and $B$ | $(A-B)\cup(B-A)$ |
| at least one of $A,B$ | $A\cup B$ |
| both $A$ and $B$ | $A\cap B$ |

The event “exactly one of $A$ and $B$” is the **symmetric difference**:

$$
A\triangle B
=(A-B)\cup(B-A).
$$

---

# 6. Properties of Events

Because events are sets, they obey the laws of set algebra.

Let $A,B,C\subseteq S$.

---

## 6.1 Commutative Laws

Order does not matter for union or intersection:

$$
A\cup B=B\cup A,
$$

$$
A\cap B=B\cap A.
$$

> **Intuition:** “$A$ or $B$” describes the same region as “$B$ or $A$.”

---

## 6.2 Associative Laws

Grouping does not matter:

$$
(A\cup B)\cup C
=
A\cup(B\cup C),
$$

$$
(A\cap B)\cap C
=
A\cap(B\cap C).
$$

This allows notation such as

$$
A\cup B\cup C
$$

without ambiguity.

---

## 6.3 Distributive Laws

Intersection distributes over union:

$$
A\cap(B\cup C)
=
(A\cap B)\cup(A\cap C).
$$

Union distributes over intersection:

$$
A\cup(B\cap C)
=
(A\cup B)\cap(A\cup C).
$$

### Membership derivation

Take any outcome $\omega$. Then

$$
\omega\in A\cap(B\cup C)
$$

means

$$
\omega\in A
\quad\text{and}\quad
(\omega\in B\text{ or }\omega\in C).
$$

By ordinary logic, this is equivalent to

$$
(\omega\in A\text{ and }\omega\in B)
\quad\text{or}\quad
(\omega\in A\text{ and }\omega\in C).
$$

Therefore,

$$
\omega\in(A\cap B)\cup(A\cap C),
$$

so

$$
A\cap(B\cup C)
=
(A\cap B)\cup(A\cap C).
$$

---

## 6.4 Identity Laws

Union with the empty event changes nothing:

$$
A\cup\varnothing=A.
$$

Intersection with the universal event changes nothing:

$$
A\cap S=A.
$$

Additional useful forms are

$$
A\cup S=S,
$$

$$
A\cap\varnothing=\varnothing.
$$

---

## 6.5 Complement Laws

An event and its complement cover the sample space:

$$
A\cup A^c=S.
$$

They have no common outcomes:

$$
A\cap A^c=\varnothing.
$$

Double complement returns the original event:

$$
(A^c)^c=A.
$$

Also,

$$
S^c=\varnothing,
$$

$$
\varnothing^c=S.
$$

---

## 6.6 Idempotent Laws

Combining an event with itself does not change it:

$$
A\cup A=A,
$$

$$
A\cap A=A.
$$

> **Intuition:** Repeating the same condition adds no new outcomes.

---

## 6.7 De Morgan's Laws

De Morgan's laws are among the most important identities in event algebra.

### First Law

$$
\boxed{(A\cup B)^c=A^c\cap B^c}
$$

Interpretation:

> “Not ($A$ or $B$)” means “not $A$ and not $B$.”

### Second Law

$$
\boxed{(A\cap B)^c=A^c\cup B^c}
$$

Interpretation:

> “Not ($A$ and $B$)” means “not $A$ or not $B$.”

### Step-by-step proof of the first law

For any $\omega\in S$,

$$
\omega\in(A\cup B)^c
$$

iff

$$
\omega\notin A\cup B
$$

iff

$$
\omega\notin A
\quad\text{and}\quad
\omega\notin B
$$

iff

$$
\omega\in A^c
\quad\text{and}\quad
\omega\in B^c
$$

iff

$$
\omega\in A^c\cap B^c.
$$

Hence

$$
(A\cup B)^c=A^c\cap B^c.
$$

---

## 6.8 Absorption Laws

Two additional useful identities are

$$
A\cup(A\cap B)=A,
$$

$$
A\cap(A\cup B)=A.
$$

> **Intuition:** The smaller nested region adds nothing beyond the event already present.

---

## 6.9 Summary of Event Laws

| Law | Union form | Intersection form |
|---|---|---|
| Commutative | $A\cup B=B\cup A$ | $A\cap B=B\cap A$ |
| Associative | $(A\cup B)\cup C=A\cup(B\cup C)$ | $(A\cap B)\cap C=A\cap(B\cap C)$ |
| Distributive | $A\cup(B\cap C)=(A\cup B)\cap(A\cup C)$ | $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$ |
| Identity | $A\cup\varnothing=A$ | $A\cap S=A$ |
| Domination | $A\cup S=S$ | $A\cap\varnothing=\varnothing$ |
| Idempotent | $A\cup A=A$ | $A\cap A=A$ |
| Complement | $A\cup A^c=S$ | $A\cap A^c=\varnothing$ |
| De Morgan | $(A\cap B)^c=A^c\cup B^c$ | $(A\cup B)^c=A^c\cap B^c$ |

---

# 7. Event Relationships

## 7.1 Disjoint Events

Events $A$ and $B$ are disjoint if

$$
A\cap B=\varnothing.
$$

Example:

$$
A=\{1,2\},
\qquad
B=\{5,6\}.
$$

There is no shared outcome.

---

## 7.2 Overlapping Events

Events overlap if

$$
A\cap B\ne\varnothing.
$$

Example:

$$
A=\{2,4,6\},
$$

$$
B=\{4,5,6\}.
$$

Then

$$
A\cap B=\{4,6\}.
$$

---

## 7.3 Subset Events

$A$ is a subset of $B$ when every outcome of $A$ is also an outcome of $B$:

$$
A\subseteq B.
$$

Equivalent logical statement:

$$
\omega\in A\implies\omega\in B.
$$

Example:

$$
A=\{6\},
$$

$$
B=\{4,5,6\}.
$$

Then

$$
A\subseteq B.
$$

A useful probability consequence is

$$
A\subseteq B
\implies
P(A)\le P(B).
$$

---

## 7.4 Equal Events

Two events are equal if they contain exactly the same outcomes:

$$
A=B.
$$

Equivalent condition:

$$
A\subseteq B
\quad\text{and}\quad
B\subseteq A.
$$

Example:

$$
A=\{2,4,6\}
$$

and

$$
B=\{x\in S:x\text{ is even}\}.
$$

For $S=\{1,2,3,4,5,6\}$,

$$
A=B.
$$

---

## 7.5 Universal Event

The universal event is the complete sample space:

$$
S.
$$

Every event satisfies

$$
E\subseteq S.
$$

Probability axiom:

$$
P(S)=1.
$$

---

## 7.6 Empty Event

The empty event is

$$
\varnothing.
$$

It contains no outcomes:

$$
|\varnothing|=0.
$$

Probability axiom consequence:

$$
P(\varnothing)=0.
$$

---

## 7.7 Relationship Map

```text
                         Sample Space S
+------------------------------------------------------+
|                                                      |
|          +-------------------------------+           |
|          |               B               |           |
|          |      +-------------+          |           |
|          |      |      A      |          |           |
|          |      |   A ⊆ B     |          |           |
|          |      +-------------+          |           |
|          +-------------------------------+           |
|                                                      |
|     +---------+                  +---------+          |
|     |    C    |                  |    D    |          |
|     +---------+                  +---------+          |
|                                                      |
+------------------------------------------------------+

A ⊆ B       : subset relationship
C ∩ D = ∅   : disjoint relationship
S           : universal event
∅           : empty event, containing no point
```

---

# 8. Venn Diagram Interpretation

Venn diagrams represent events as geometric regions.

## 8.1 Sample Space

The outer rectangle represents $S$:

```text
+------------------------------------+
|                  S                 |
|                                    |
|                                    |
|                                    |
+------------------------------------+
```

Every possible outcome lies somewhere inside this rectangle.

---

## 8.2 Event

An event $A\subseteq S$ is drawn as a region inside $S$:

```text
+------------------------------------+
|                  S                 |
|          ____________              |
|         /            \             |
|        /      A       \            |
|        \              /            |
|         \____________/             |
+------------------------------------+
```

---

## 8.3 Union

$$
A\cup B
$$

contains every point in $A$ or $B$ or both.

```text
+------------------------------------+
|       _______     _______          |
|      /#######\___/#######\         |
|     /#####################\        |
|     \#####################/        |
|      \#######/   \#######/         |
+------------------------------------+

# = A ∪ B
```

---

## 8.4 Intersection

$$
A\cap B
$$

contains only shared points.

```text
+------------------------------------+
|       _______     _______          |
|      /       \___/       \         |
|     /    A    ###    B    \        |
|     \         ###         /        |
|      \_______/   \_______/         |
+------------------------------------+

# = A ∩ B
```

---

## 8.5 Complement

$$
A^c=S\setminus A.
$$

It is the region inside $S$ but outside $A$.

---

## 8.6 Difference

$$
A-B=A\cap B^c.
$$

This is the part of $A$ not shared with $B$.

```text
+------------------------------------+
|       _______     _______          |
|      /#######\___/       \         |
|     /#########   overlap   \        |
|     \#########             /        |
|      \#######/   \_______/         |
+------------------------------------+

# = A - B
```

> **Mathematical interpretation:** Venn diagrams are visualizations of set membership. Shading a region is equivalent to writing a logical condition on $\omega\in S$.

---

# 9. Probability of Events

## 9.1 Probability Notation

For an event $E$,

$$
P(E)
$$

is the probability that $E$ occurs.

A probability satisfies

$$
0\le P(E)\le 1.
$$

Special cases:

$$
P(\varnothing)=0,
$$

$$
P(S)=1.
$$

---

## 9.2 Classical Probability Formula

For a finite sample space with equally likely outcomes,

$$
\boxed{P(E)=\frac{|E|}{|S|}}
$$

where:

- $|E|$ is the number of favourable outcomes;
- $|S|$ is the total number of possible outcomes.

### Why the formula works

Suppose

$$
S=\{\omega_1,\omega_2,\dots,\omega_n\}
$$

and every outcome is equally likely. Then

$$
P(\{\omega_i\})=\frac{1}{n}.
$$

If event $E$ contains $k$ outcomes,

$$
E=\{\omega_{i_1},\dots,\omega_{i_k}\},
$$

then, because these elementary outcomes are disjoint,

$$
P(E)
=
\sum_{j=1}^{k}P(\{\omega_{i_j}\}).
$$

Therefore,

$$
P(E)
=
\sum_{j=1}^{k}\frac{1}{n}
=
\frac{k}{n}.
$$

Since $k=|E|$ and $n=|S|$,

$$
\boxed{P(E)=\frac{|E|}{|S|}}.
$$

---

## 9.3 Example: Even Number on a Die

Let

$$
S=\{1,2,3,4,5,6\}
$$

and

$$
E=\{2,4,6\}.
$$

Then

$$
|E|=3,
\qquad
|S|=6.
$$

Hence

$$
P(E)=\frac{3}{6}=\frac12.
$$

---

## 9.4 Example: At Least One Head in Two Tosses

Sample space:

$$
S=\{HH,HT,TH,TT\}.
$$

Event:

$$
E=\{HH,HT,TH\}.
$$

Therefore,

$$
P(E)=\frac{|E|}{|S|}
=\frac34.
$$

---

## 9.5 The Equally Likely Assumption

The formula

$$
P(E)=\frac{|E|}{|S|}
$$

is not universally valid. It requires equally likely elementary outcomes.

Suppose a biased coin satisfies

$$
P(H)=0.8,
\qquad
P(T)=0.2.
$$

Although

$$
|\{H\}|=|\{T\}|=1,
$$

we have

$$
P(H)\ne P(T).
$$

So cardinality alone cannot determine probability in a non-uniform model.

---

# 10. Event Operations with Probability

## 10.1 Union Rule

For any two events $A$ and $B$,

$$
\boxed{P(A\cup B)=P(A)+P(B)-P(A\cap B)}.
$$

This is also called the two-event inclusion-exclusion rule.

---

## 10.2 Why We Subtract the Intersection

Suppose we add

$$
P(A)+P(B).
$$

The overlap $A\cap B$ is counted once inside $P(A)$ and once inside $P(B)$.

Therefore it is counted twice.

To correct the double counting, subtract one copy:

$$
P(A\cup B)
=
P(A)+P(B)-P(A\cap B).
$$

---

## 10.3 Step-by-Step Set Derivation

Decompose $A\cup B$ into disjoint pieces:

$$
A\cup B
=
(A-B)\cup(A\cap B)\cup(B-A).
$$

The three pieces are pairwise disjoint, so

$$
P(A\cup B)
=
P(A-B)+P(A\cap B)+P(B-A).
$$

Also,

$$
P(A)
=
P(A-B)+P(A\cap B),
$$

and

$$
P(B)
=
P(B-A)+P(A\cap B).
$$

Adding,

$$
P(A)+P(B)
=
P(A-B)+P(B-A)+2P(A\cap B).
$$

Subtract $P(A\cap B)$:

$$
P(A)+P(B)-P(A\cap B)
$$

$$
=
P(A-B)+P(B-A)+P(A\cap B).
$$

But that is exactly

$$
P(A\cup B).
$$

Hence

$$
\boxed{P(A\cup B)=P(A)+P(B)-P(A\cap B)}.
$$

---

## 10.4 Example of the Union Rule

Roll a fair die.

Let

$$
A=\{2,4,6\}
$$

be the event “even,” and

$$
B=\{4,5,6\}
$$

be the event “greater than 3.”

Then

$$
A\cap B=\{4,6\}.
$$

So

$$
P(A)=\frac36,
$$

$$
P(B)=\frac36,
$$

$$
P(A\cap B)=\frac26.
$$

Therefore,

$$
P(A\cup B)
=
\frac36+\frac36-\frac26
=
\frac46
=
\frac23.
$$

Indeed,

$$
A\cup B=\{2,4,5,6\},
$$

which has four of six outcomes.

---

## 10.5 Addition Rule for Mutually Exclusive Events

If

$$
A\cap B=\varnothing,
$$

then

$$
P(A\cap B)=0.
$$

Therefore the union rule simplifies to

$$
\boxed{P(A\cup B)=P(A)+P(B)}.
$$

This is the addition rule for mutually exclusive events.

---

## 10.6 Complement Rule

Because

$$
A\cup A^c=S
$$

and

$$
A\cap A^c=\varnothing,
$$

we have

$$
P(A\cup A^c)
=
P(A)+P(A^c).
$$

But

$$
P(S)=1.
$$

Therefore,

$$
P(A)+P(A^c)=1,
$$

so

$$
\boxed{P(A^c)=1-P(A)}.
$$

---

## 10.7 Why the Complement Rule Is Powerful

Many “at least one” probabilities are easier to compute through complements.

Example: toss a fair coin three times.

Let

$$
A=\{\text{at least one head}\}.
$$

Its complement is

$$
A^c=\{TTT\}.
$$

Therefore,

$$
P(A)
=1-P(A^c)
$$

$$
=1-\frac18
$$

$$
=\frac78.
$$

This is much easier than listing all seven favourable outcomes.

---

# 11. Geometric Interpretation

## 11.1 Events as Regions

An event is a subset of the sample space, so it can be interpreted as a geometric region.

Suppose

$$
S=[0,1]^2.
$$

An outcome is a point

$$
\omega=(x,y)
$$

inside the unit square.

Define

$$
A=\{(x,y)\in[0,1]^2:x+y\le 1\}.
$$

Then $A$ is the triangular region below the line

$$
x+y=1.
$$

---

## 11.2 Overlap

For regions $A$ and $B$,

$$
A\cap B
$$

is their geometric overlap.

Example:

$$
A=\{(x,y):x^2+y^2\le 1\},
$$

$$
B=\{(x,y):x\ge 0\}.
$$

Then

$$
A\cap B
$$

is the right half of the unit disk.

---

## 11.3 Complement

For $A\subseteq S$,

$$
A^c=S\setminus A
$$

is the region of the sample space not covered by $A$.

If

$$
S=[0,1]^2
$$

and

$$
A=\{(x,y):x+y\le 1\},
$$

then

$$
A^c=\{(x,y):x+y>1\}.
$$

---

## 11.4 Coverage

A collection of events $E_1,\dots,E_n$ is exhaustive when their geometric regions cover $S$:

$$
\bigcup_{i=1}^{n}E_i=S.
$$

This viewpoint is useful in:

- decision boundaries;
- class regions;
- uncertainty regions;
- partitioning state spaces;
- robot motion planning;
- Bayesian decision theory.

---

## 11.5 Probability as Geometric Measure

For a uniformly distributed random point over a region $S$, probability can sometimes be interpreted as a ratio of geometric measures:

$$
P(E)
=
\frac{\operatorname{Area}(E)}{\operatorname{Area}(S)}
$$

in two dimensions, or

$$
P(E)
=
\frac{\operatorname{Volume}(E)}{\operatorname{Volume}(S)}
$$

in three dimensions.

This is the continuous analogue of

$$
P(E)=\frac{|E|}{|S|}
$$

for equally likely finite outcomes.

---

# 12. Real-World Examples

## 12.1 Coin Toss

For two tosses,

$$
S=\{HH,HT,TH,TT\}.
$$

Event “at least one head”:

$$
A=\{HH,HT,TH\}.
$$

Complement:

$$
A^c=\{TT\}.
$$

Thus

$$
P(A)=1-P(A^c)=1-\frac14=\frac34.
$$

---

## 12.2 Dice Roll

Let

$$
S=\{1,2,3,4,5,6\}.
$$

Define

$$
A=\{2,4,6\}
$$

and

$$
B=\{2,3,5\}.
$$

Then

$$
A\cap B=\{2\}
$$

and

$$
A\cup B=\{2,3,4,5,6\}.
$$

---

## 12.3 Card Deck

Let

$$
S=\{\text{52 distinct cards}\}.
$$

Define

$$
A=\{\text{hearts}\}
$$

and

$$
B=\{\text{face cards}\}.
$$

Then

$$
|A|=13,
$$

$$
|B|=12,
$$

and

$$
|A\cap B|=3
$$

because $J\heartsuit,Q\heartsuit,K\heartsuit$ are heart face cards.

Therefore,

$$
P(A\cup B)
=
\frac{13}{52}+\frac{12}{52}-\frac{3}{52}
=
\frac{22}{52}
=
\frac{11}{26}.
$$

---

## 12.4 Weather Forecasting

Let tomorrow's weather state be a random outcome in

$$
S=\{\text{sunny},\text{cloudy},\text{rainy},\text{stormy}\}.
$$

Define

$$
R=\{\text{rainy},\text{stormy}\}
$$

as “rain occurs,” and

$$
D=\{\text{stormy}\}
$$

as “dangerous weather occurs.”

Then

$$
D\subseteq R.
$$

Consequently,

$$
P(D)\le P(R).
$$

This subset reasoning is common in risk forecasting.

---

## 12.5 Medical Diagnosis

Consider the patient population as sample space $S$.

Define

$$
D=\{\text{patient has disease}\}
$$

and

$$
T^+=\{\text{test result is positive}\}.
$$

Important combined events include:

True positive:

$$
D\cap T^+.
$$

False positive:

$$
D^c\cap T^+.
$$

False negative:

$$
D\cap(T^+)^c.
$$

True negative:

$$
D^c\cap(T^+)^c.
$$

These event intersections form the mathematical basis of diagnostic confusion matrices.

---

## 12.6 Credit Approval

Let $S$ be the set of loan applications.

Define

$$
A=\{\text{application approved}\},
$$

$$
H=\{\text{high income}\},
$$

$$
C=\{\text{credit score}\ge 750\}.
$$

A policy event might be

$$
E=H\cap C.
$$

An alternative approval rule might be

$$
E=H\cup C.
$$

These two policies are mathematically different:

- $H\cap C$: both conditions required;
- $H\cup C$: at least one condition required.

---

## 12.7 Fraud Detection

Let $S$ be all observed transactions.

Define

$$
F=\{\text{transaction is truly fraudulent}\}
$$

and

$$
M=\{\text{model flags transaction}\}.
$$

Then

$$
F\cap M
$$

is a detected fraud event,

$$
F^c\cap M
$$

is a false alarm event, and

$$
F\cap M^c
$$

is a missed fraud event.

A safety-focused objective often aims to reduce

$$
P(F\cap M^c).
$$

---

## 12.8 Quality Control

Let $S$ be the set of manufactured items.

Define

$$
D_1=\{\text{surface defect}\},
$$

$$
D_2=\{\text{dimension defect}\}.
$$

An item has at least one defect when

$$
D_1\cup D_2
$$

occurs.

An item has both defect types when

$$
D_1\cap D_2
$$

occurs.

An item is free from both when

$$
(D_1\cup D_2)^c.
$$

By De Morgan's law,

$$
(D_1\cup D_2)^c
=
D_1^c\cap D_2^c.
$$

---

# 13. Events in Artificial Intelligence

This section is conceptual. The goal is to recognize how AI problems are built from event statements.

---

## 13.1 Machine Learning Classification

Let $S$ represent possible input-label situations.

For a binary classifier, define

$$
Y^+=\{\text{true label is positive}\}
$$

and

$$
\hat{Y}^+=\{\text{model predicts positive}\}.
$$

Then:

True positive event:

$$
Y^+\cap\hat{Y}^+.
$$

False positive event:

$$
(Y^+)^c\cap\hat{Y}^+.
$$

False negative event:

$$
Y^+\cap(\hat{Y}^+)^c.
$$

Thus, the confusion matrix is fundamentally an algebra of events.

---

## 13.2 Computer Vision

Let $S$ be the space of possible images or video frames.

Define

$$
P=\{x\in S:x\text{ contains a pedestrian}\}.
$$

Define a high-confidence detector event

$$
D_{0.9}=\{x\in S:s_{\text{pedestrian}}(x)\ge 0.9\}.
$$

Then a high-confidence correct detection lies in

$$
P\cap D_{0.9}.
$$

A high-confidence false alarm lies in

$$
P^c\cap D_{0.9}.
$$

---

## 13.3 Natural Language Processing

Let $S$ be a set of possible texts.

Define

$$
T=\{x\in S:x\text{ is toxic}\}
$$

and

$$
M=\{x\in S:\text{moderation model flags }x\}.
$$

Then

$$
T\cap M
$$

is successful detection, while

$$
T\cap M^c
$$

is a missed toxic-content event.

Events can also be semantic:

$$
Q=\{x:x\text{ is a question}\},
$$

$$
C=\{x:x\text{ contains code}\}.
$$

A “question containing code” is

$$
Q\cap C.
$$

---

## 13.4 Reinforcement Learning

Let $S$ represent possible trajectories

$$
\tau=(s_0,a_0,s_1,a_1,\dots,s_T).
$$

Define

$$
G=\{\tau:\text{goal reached}\}
$$

and

$$
C=\{\tau:\text{collision occurs}\}.
$$

A safe successful trajectory belongs to

$$
G\cap C^c.
$$

A key reliability quantity may be

$$
P(G\cap C^c).
$$

---

## 13.5 Recommendation Systems

Let $S$ be the space of user-item interactions.

Define

$$
K=\{\text{user clicks item}\},
$$

$$
P=\{\text{user purchases item}\},
$$

$$
R=\{\text{item was recommended}\}.
$$

Then

$$
R\cap K
$$

represents recommended-and-clicked interactions.

A deeper conversion event is

$$
R\cap K\cap P.
$$

---

## 13.6 Bayesian Networks

A Bayesian network represents probabilistic relationships among variables. Events arise from statements about those variables.

For binary variables $R$ and $W$:

$$
A=\{R=1\}
$$

might mean “it rains,” while

$$
B=\{W=1\}
$$

might mean “the road is wet.”

Bayesian reasoning asks about quantities such as

$$
P(B\mid A)
$$

and

$$
P(A\mid B).
$$

Conditional probability, introduced next, is therefore a probability of one event given information that another event occurred.

---

## 13.7 Robotics

Let $S$ be a robot's state space.

Define

$$
O=\{s\in S:\text{state is inside an obstacle region}\},
$$

$$
G=\{s\in S:\text{state is inside the goal region}\}.
$$

Safe states form

$$
O^c.
$$

A safe goal state lies in

$$
G\cap O^c.
$$

This geometric event view is central to uncertainty-aware planning.

---

## 13.8 Autonomous Vehicles

Let $S$ represent possible near-future traffic trajectories.

Define

$$
C=\{\tau:\text{collision within 3 seconds}\}
$$

and

$$
L=\{\tau:\text{lane departure occurs}\}.
$$

A general hazard event is

$$
H=C\cup L.
$$

Its complement

$$
H^c=(C\cup L)^c
$$

represents trajectories with neither hazard. By De Morgan's law,

$$
H^c=C^c\cap L^c.
$$

---

## 13.9 Medical AI

Let

$$
D=\{\text{disease present}\}
$$

and

$$
M=\{\text{AI model predicts disease}\}.
$$

A dangerous miss is

$$
D\cap M^c.
$$

A false alarm is

$$
D^c\cap M.
$$

Clinical decision systems therefore reason about the probabilities of event intersections, not merely abstract model scores.

---

## 13.10 Large Language Models

An autoregressive language model assigns probabilities to possible next tokens.

Let the vocabulary be

$$
V=\{v_1,v_2,\dots,v_m\}.
$$

At time step $t+1$, the next token is a random outcome

$$
X_{t+1}\in V.
$$

A simple event is

$$
E=\{X_{t+1}=\text{``probability''}\}.
$$

A compound event might be

$$
C=\{X_{t+1}\in V_{\text{code}}\},
$$

where $V_{\text{code}}\subseteq V$ is a selected set of code-related tokens.

Another event is

$$
N=\{X_{t+1}\in V_{\text{numeric}}\}.
$$

Then

$$
C\cup N
$$

means “the next token is code-related or numeric,” and

$$
C\cap N
$$

contains tokens satisfying both definitions, if such overlap exists.

For a generated sequence

$$
X_{1:T}=(X_1,X_2,\dots,X_T),
$$

we may define a sequence-level event

$$
E_{\text{valid}}
=
\{X_{1:T}:X_{1:T}\text{ satisfies a specified constraint}\}.
$$

> **Core AI insight:** Even when models manipulate vectors, logits, embeddings, and neural networks, uncertainty is still interpreted through events such as “the output belongs to this region,” “the prediction is wrong,” or “the generated sequence satisfies this condition.”

---

# 14. Common Mistakes

## 14.1 Confusing Outcomes with Events

For a die roll,

$$
4
$$

is an outcome, while

$$
\{4\}
$$

is the simple event containing that outcome.

In informal contexts people blur this distinction, but mathematically it matters.

---

## 14.2 Assuming Mutually Exclusive Events Are Independent

Mutually exclusive means

$$
A\cap B=\varnothing.
$$

Independence means

$$
P(A\cap B)=P(A)P(B).
$$

If $A$ and $B$ are mutually exclusive and both have positive probability, then

$$
P(A\cap B)=0,
$$

but

$$
P(A)P(B)>0.
$$

Therefore they are not independent.

> **Important:** For positive-probability events, mutual exclusivity actually creates strong dependence: occurrence of one rules out the other.

---

## 14.3 Forgetting Complement Notation

The complement of $A$ is not another arbitrary event. It is defined relative to $S$:

$$
A^c=S\setminus A.
$$

Changing the sample space can change the complement.

---

## 14.4 Misusing Union and Intersection

- “$A$ or $B$” corresponds to

$$
A\cup B.
$$

- “$A$ and $B$” corresponds to

$$
A\cap B.
$$

A common error is reversing these.

---

## 14.5 Treating “Or” as Exclusive by Default

In probability,

$$
A\cup B
$$

normally includes the overlap $A\cap B$.

Thus “$A$ or $B$” means:

- $A$ only;
- $B$ only;
- both $A$ and $B$.

For exactly one event, use

$$
A\triangle B.
$$

---

## 14.6 Ignoring the Sample Space

The event

$$
A^c
$$

cannot be interpreted without knowing $S$.

Example:

If

$$
S_1=\{1,2,3,4,5,6\}
$$

and

$$
A=\{2,4,6\},
$$

then

$$
A^c=\{1,3,5\}.
$$

But if

$$
S_2=\{1,2,3,4,5,6,7,8\},
$$

then

$$
A^c=\{1,3,5,7,8\}.
$$

The complement depends on the universe under consideration.

---

## 14.7 Applying the Classical Formula Without Equal Likelihood

Do not automatically use

$$
P(E)=\frac{|E|}{|S|}
$$

unless the elementary outcomes are equally likely.

For weighted or biased outcomes, probabilities must reflect the model's actual probability distribution.

---

## 14.8 Forgetting to Subtract Overlap

The incorrect formula

$$
P(A\cup B)=P(A)+P(B)
$$

fails for overlapping events.

The general formula is

$$
P(A\cup B)
=
P(A)+P(B)-P(A\cap B).
$$

Only when

$$
A\cap B=\varnothing
$$

may we simplify to direct addition.

---

# 15. Summary

## 15.1 Core Definitions

An outcome is one possible result:

$$
\omega\in S.
$$

An event is a subset of the sample space:

$$
E\subseteq S.
$$

An event occurs when

$$
\omega\in E.
$$

---

## 15.2 Event Space

For a finite model, events may be collected in

$$
\mathcal{P}(S).
$$

More generally, a probability space is

$$
(S,\mathcal{F},P),
$$

where $\mathcal{F}$ is the event collection.

---

## 15.3 Set Notation and Event Algebra

Union:

$$
A\cup B.
$$

Intersection:

$$
A\cap B.
$$

Complement:

$$
A^c.
$$

Difference:

$$
A-B=A\cap B^c.
$$

---

## 15.4 Important Relationships

Disjoint:

$$
A\cap B=\varnothing.
$$

Subset:

$$
A\subseteq B.
$$

Equal:

$$
A=B.
$$

Exhaustive:

$$
\bigcup_i E_i=S.
$$

---

## 15.5 Essential Laws

Commutative:

$$
A\cup B=B\cup A,
$$

$$
A\cap B=B\cap A.
$$

Distributive:

$$
A\cap(B\cup C)
=
(A\cap B)\cup(A\cap C).
$$

De Morgan:

$$
(A\cup B)^c=A^c\cap B^c,
$$

$$
(A\cap B)^c=A^c\cup B^c.
$$

---

## 15.6 Probability of Events

For finite equally likely outcomes:

$$
P(E)=\frac{|E|}{|S|}.
$$

Complement rule:

$$
P(A^c)=1-P(A).
$$

Union rule:

$$
P(A\cup B)
=
P(A)+P(B)-P(A\cap B).
$$

For disjoint events:

$$
P(A\cup B)=P(A)+P(B).
$$

---

## 15.7 AI Applications

Events provide a common mathematical language for:

- classification outcomes;
- model errors;
- detection regions;
- safe and unsafe states;
- fraud alerts;
- medical diagnoses;
- user interactions;
- trajectory success;
- token generation;
- sequence constraints.

A large class of AI questions can be written as:

$$
P(E),
$$

where $E$ is a carefully defined event.

---

# 16. What's Next?

The next chapter is:

# **Conditional Probability**

So far, we have asked questions such as

$$
P(A).
$$

But real-world reasoning often provides additional information.

For example:

- What is the probability of rain **given that** the sky is cloudy?
- What is the probability of disease **given that** a test is positive?
- What is the probability of fraud **given that** a transaction is unusually large?
- What is the probability of a token **given that** previous tokens have already been generated?

This leads to conditional probability:

$$
P(A\mid B).
$$

It asks:

> What is the probability of event $A$ when we know that event $B$ has occurred?

The key geometric idea is that conditioning changes the effective sample space from $S$ to $B$.

For $P(B)>0$,

$$
P(A\mid B)
=
\frac{P(A\cap B)}{P(B)}.
$$

Conditional probability will connect event algebra to:

- Bayes' theorem;
- statistical inference;
- Bayesian networks;
- diagnostic reasoning;
- probabilistic machine learning;
- sequence models;
- modern AI systems.

---

# Final Insight

> **Events are the language of probability.** Every probabilistic question—from rolling a die to predicting the next word in a Large Language Model—can be expressed as an event within a sample space. By mastering event algebra and its mathematical properties, learners build the foundation required for conditional probability, Bayesian inference, stochastic processes, and modern AI systems.

The conceptual journey is:

$$
\boxed{
\text{Outcomes}
\longrightarrow
\text{Sample Space}
\longrightarrow
\text{Events}
\longrightarrow
\text{Event Algebra}
\longrightarrow
\text{Probability}
\longrightarrow
\text{Conditional Reasoning}
}
$$

Once this structure becomes intuitive, probability stops being a collection of isolated formulas. It becomes a coherent mathematical language for reasoning under uncertainty.

---

## Chapter Checklist

Before moving forward, verify that you can answer the following:

- [ ] What is the difference between an outcome and an event?
- [ ] Why must every event satisfy $E\subseteq S$?
- [ ] What is the difference between $A\cup B$ and $A\cap B$?
- [ ] How is $A-B$ related to $A\cap B^c$?
- [ ] What makes two events mutually exclusive?
- [ ] Why are mutually exclusive positive-probability events not independent?
- [ ] How do De Morgan's laws transform complements of unions and intersections?
- [ ] When is $P(E)=|E|/|S|$ valid?
- [ ] Why does the union rule subtract $P(A\cap B)$?
- [ ] How can AI classification errors be represented as event intersections?
- [ ] How can an LLM next-token question be represented as an event?

---

## Suggested Repository Placement

```text
MLVerse-Math/
└── Probability/
    ├── 01_Sample_Space/
    │   └── Mathematics.md
    ├── 02_Events/
    │   └── Mathematics.md
    └── 03_Conditional_Probability/
        └── Mathematics.md
```

---

**End of Chapter 02 — Events**
