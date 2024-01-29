# Solutions for Homework 0 Conceptual Questions

---
tags: hw0, conceptual
---
# Homework 0 Conceptual: Warm-up w/ Solutions

:::info
Conceptual section due **Friday, February 3 at 6:00 PM EST**
Programming section due **Friday, February 3 at 6:00 PM EST**
:::

:::info
Conceptual section due **Friday, February 3 at 6:00 PM EST**
Programming section due **Friday, February 3 at 6:00 PM EST**
:::

Welcome to the first (conceptual) homework assignment of CSCI1470/2470! This assignment is just meant to be a short math review of concepts from Linear Algebra and Probability that you will need for this course, and also get you set up with a course virtual environment so that you will be ready to start the first programming assignment (Homework 1).

First we'll go over some concepts that you will need from linear algebra, and ask you to answer some questions. This document contains the answers, but do try to answer these questions on your own first. While this doesn't have to be necessarily easy, it should prepare you for some of the early material and can be used to judge comfort with things that will come up a lot in the course. 

## Theme
![](https://cdn.dribbble.com/users/55017/screenshots/2074320/fishworkout.gif)
*This fish is warming up for his race this Friday*

# Conceptual Questions

## Vectors

The following are some common (and _important_) properties and definitions about vectors:

1. Given two column vectors $\mathbf{a} \in \mathbb{R}^{r\times1}$ and $\mathbf{b} \in \mathbb{R}^{c\times1}$, the _outer product_ is: 

$$
    \mathbf{a} \times \mathbf{b} = 
    \begin{bmatrix}a_0 \\ \vdots \\ a_{r-1}\end{bmatrix} 
    \times 
    \begin{bmatrix}b_0 \\ \vdots \\ b_{c-1}\end{bmatrix} = 
    \begin{bmatrix}
        a_0 b^T\\ \vdots \\
        a_{r-1} b^T\\   
    \end{bmatrix} 
    = \begin{bmatrix}
        a_0 b_0 & \cdots & a_0 b_{c-1}\\
        \vdots & \ddots & \vdots \\
        a_{r-1} b_0 & \cdots & a_{r-1} b_{c-1}\\
    \end{bmatrix} 
    \in \mathbb{R}^{r\times c}
$$
        
2. Given two column vectors $\mathbf{a}$ and $\mathbf{b}$ both in $\mathbb{R}^{r\times 1}$, the _inner product_ (or the _dot product_) is defined as:
 
    $$ 
    \mathbf{a} \cdot \mathbf{b}  = \mathbf{a}^T\mathbf{b} 
    = \begin{bmatrix} a_0\ \cdots\ a_{r-1} \end{bmatrix} 
        \begin{bmatrix}b_0 \\ \vdots \\ b_{r-1}\end{bmatrix}
    = \sum_{i=0}^{r} a_i b_i
    $$
    where $\mathbf{v}^T$ is the _transpose_ of a vector, which converts between column and row vector alignment. The same idea extends to matrices as well. 
    
3. Given a matrix $\mathbf{M} \in \mathbb{R}^{r\times c}$, a matrix product is defined as: 
    $$\mathbf{Mx} \ =\ \mathbf{M}\begin{bmatrix} x_0\\ \vdots \\ x_{c-1}\\ \end{bmatrix} 
        \ =\ \begin{bmatrix} \mathbf{M_0}\\ \vdots \\ \mathbf{M_{r-1}}\\ \end{bmatrix}\mathbf{x}
        \ =\ \begin{bmatrix} \ \mathbf{M_0 x}\ \\ \vdots \\ \ \mathbf{M_{r-1} x}\ \\ \end{bmatrix}
    $$

4. $\mathbf{M} \in \mathbb{R}^{r\times c}$ implies that the function $f(x) = \mathbf{Mx}$ can map $\mathbb{R}^{c\times 1} \to \mathbb{R}^{r\times 1}$.

5. $\mathbf{M_1} \in \mathbb{R}^{d\times c}$ and $\mathbf{M_2} \in \mathbb{R}^{r\times d}$ implies $f(x) = \mathbf{M_2M_1x}$ can map $\mathbb{R}^c \to \mathbb{R}^r$.



### Questions (Vectors)

Given the vector rules above and your own knowledge, try solving these: 

1. **Prove that $(2) + (3)$ implies $(4)$**. In other words, use your understanding of the inner and matrix-vector products to explain why $(d)$ has to be true.
:::success 
:::spoiler **[ANSWER]** Please Attempt It First!
$\mathbf{M_ix}$ is a $c$-entry row vector which has the same shape as a transposed column vector, where $\mathbf{M_i}$ is a row of $\mathbf{M}$. As $x$ is a $c$-entry column vector, a row vector multiplied by a compatible column vector defines a dot product. Each row corresponds to a dot product, and there are $r$ rows, so the result is a $r$-entry column vector.
:::
     

2. **Prove that $(4)$ implies $(5)$**. 

   
:::success 
:::spoiler **[ANSWER]** Please Attempt It First!
Let $g_1(\mathbf{x}) = \mathbf{M_1x}$ and $g_2(\mathbf{x}) = \mathbf{M_2x}$. 
    
By (d), $g_1 : \mathbb{R}^{c} \to \mathbb{R}^{d}$ and $g_2 : \mathbb{R}^{d} \to \mathbb{R}^{r}$. Thereby, $g_2 \circ g_1 :  \mathbb{R}^{c} \to \mathbb{R}^{d} \to \mathbb{R}^{r}$. 
    
Broken down a bit, $g_1$ converts from $c$-row vector to $d$-row vector since $\mathbf{M_1}$ has $c$ columns and $d$ rows. In other words, $\mathbf{M_1x}$ necessarily results in a $d$-row vector for a compatible input vector $\mathbf{x}$. As such, $\mathbf{M_2(M_1x)}$ is a matrix product of $\mathbf{M_2}$ and a resulting $d$-row vector. $\mathbf{M_2}$ has $d$ columns and $r$ rows, so the result is a $r$-row vector, which is indeed in $\mathbb{R}^{r}$ as it only has $r$ elements.
:::


## Differentiation

Recall that differentiation is finding the rate of change of one variable relative to another variable. Some nice reminders:

\begin{align}
\frac{dy}{dx} & \text{ is how $y$ changes with respect to $x$}.\\
\frac{\partial y}{\partial x} & \text{ is how $y$ changes with respect to $x$ (and ignoring other factors)}.\\
\frac{dz}{dx} &= \frac{dy}{dx} \cdot \frac{dz}{dy} \text{ via chain rule if these factors are easier to compute}.  
\end{align}

Some common derivative patterns include: 
$$\frac{d}{dx}(2x^3 + 4x + 5) = 6x^2 + 4
$$$$\frac{\partial}{\partial y}(x^2y^3 + xy + 5x^2) = 3x^2y^2 + x
% $$$$\frac{d}{dx}(x^3 + 5)^3 = 3(x^3 + 5)^2 \times (3x^2)
$$$$\frac{d}{dx}\ln(x) = \frac{1}{x}
$$

### Questions (Differentiation)

Given the above and your own knowledge: 

1. Use (and internalize) the log properties to solve the following: 
    $$\frac{\partial}{\partial y}\ln(x^5/y^2)$$
    The properties are as follows: 
    
    1. $\log(x^p) = p\log(x)$
    2. $\log(xy) = \log(x) + \log(y)$
    3. $\log(x/y) = \log(x) - \log(y)$

:::success 
:::spoiler **[ANSWER]** Please Attempt It First!
\begin{align*}
                \frac{\partial}{\partial y}\ln(x^5/y^2) &=
                    \frac{\partial}{\partial y}\ln(x^5/y^2)            \\
                    &= \frac{\partial}{\partial y}\bigg(\ln(x^5) - \ln(y^2)\bigg) \\
                    &= \frac{d}{dy}\bigg(-2\ln(y)\bigg) \\
                    &=  -2\frac{d}{dy}\ln(y)\\ &= -2/y
            \end{align*}
:::
    
2. Let $g_1(x) = \sum_i x_iy_i$. Solve the following partial for a valid $j$ and all valid $i$:
    $$\frac{\partial}{\partial x_j} \ln g_1(x) = \frac{\partial}{\partial x_j}\ln\bigg[\sum_i x_iy_i\bigg]$$ 
    **_Hint_**: Consider using the chain rule...
    
:::success 
:::spoiler **[ANSWER]** Please Attempt It First!
... and let $g_2(x) = \ln(g_1(x))$. Per the chain rule, we can phrase this as: 
        $$\frac{\partial g_2}{\partial x_j} = \frac{\partial g_2}{\partial g_1} \cdot \frac{\partial g_1}{\partial x_j} = \frac{1}{g_1(x)} \cdot \frac{\partial}{\partial x_j} \sum_i x_iy_i$$
        
When $i = j$, then the partial is $y_j$. On all other entries, the partial is 0. As such, the sum of $y_j$ and a lot of zeroes further implies: 
$$\frac{\partial g_2}{\partial x_j} = \frac{y_j}{\sum_i x_iy_i}$$
:::

## Probability

There exist events that are **independent** of each other, meaning that the probability of each event stays the same regardless of the outcome of other events. 

For example, consider picking a particular 3-digit number at random:
$$P(x = 123) = P(x_0 = 1)P(x_1 = 2)P(x_2 = 3) = (1/10)^3 = 1/1000$$

Alternatively, some events are **dependent** on other events. For example, consider 3 draws from a set of 1 red, 1 green, and 1 blue ball.

\begin{align}
    P(b_0 = R) &= 1/3 \\
    P(b_1 = G\ |\ b_0 = R) &= 1/2 \\
    P(b_2 = B\ |\ (b_0 = R) \cup (b_1 = G)) &= 1/1
\end{align}

This starts off the notion of _conditional probability_, where some components are realized conditional to other components. An important formula for conditional probability is Bayes' Theorem: 

$$P(A|B) = \frac{P(B|A)P(A)}{P(B)}$$

Whenever events happen at random, they happen with some probability. This is governed by some _probability distribution_. For example, $X \sim P(x)$ is a _realization_ (or _variate_, or _random variable_) of the $P(x)$ distribution. Of note: 

1. The distribution may be parameterized by some factors. For example, $X \sim \mathcal{N}(\mu=0, \sigma=1)$ is a distribution _similar to_ (AKA an instance of) the unit normal distribution.
2. The distribution may depend on something. For example, the variate may depend on the realizations of some other distribution i.e. with $P(X|Z)$. 

These distributions are equipped with _expectation_ functions $\mathbb{E}$ and $\mathbb{V}$ that reveal their expected behavior (mean and variance, respectively). These also usually suggest the _long-term equilibrium behavior_, or the distribution of realizations after many realizations are drawn and accumulated.  

- **Discrete Probability Distribution** governs discrete events $\{e_0, e_1, ...\}$.
    - If the number of possible events is finite such that $x \in \{e_0, e_1, ..., e_n\}$, there are finite set of associated probabilities $\{P(e_0), P(e_1), ..., P(e_n)\}$.
    - The list of probabilities must add up to 1. This implies there is a 100\% chance of an event being... one of the possible events.

- **Continuous Probability Distribution** governs continuous values. For example, the unit normal distribution mentioned before.

### Questions (Probability)

Given the above probability review and your own knowledge:

1. You're trying to train up a cat/dog classifier which outputs prediction between 0 and 1. Given that the input is in fact an image of a cat or dog, the truth is always one of those two. As such, the output is a probability distribution $Y$ with unknown $P(Y = y)$ for all possible $y$ in the domain of $Y$. Your friend knows that their dataset $\mathbb{D} = (\mathbb{X}, \mathbb{Y})$ is balanced between cats and dogs, and so argues that $P(Y=y)$ is equal for all plausible $y$. 
    1. If your friend's assumption were correct, what value of $P(Y=y)$ would make this a valid probability distribution for all $y$ in the domain of $Y$?
    2. Is your friend's assumption correct? Why or why not?
  
:::success 
:::spoiler **[ANSWER]** Please Attempt It First!
1. $0.5$ would make this a valid probability distribution because $P(Y=0) + P(Y=1) = 1$. 

2. Overall answer is no. As justification, two options are valid:
    - The student assumes that the cat/dog distribution is uniformly random regardless of the input. A more realistic assumption would be $P(Y = 0\ |\ X=x) + P(Y = 1\ |\ X=x) = 1$ for $x \sim X$. Maybe true but not \textbf{always} correct. 
    - If no input is given, then the student's assumption may be correct, but it is also possible that the true prior distribution P(Y) is different from what is estimated from the dataset. 
:::

## Conceptual Questions: Submission

Once you have completed the above questions, please submit your answers to the **Homework 0: Conceptual** assignment on Gradescope. 

:::info
Your solutions for the conceptual component must be **typeset**. We highly recommend using _LaTeX_ to write clean mathematical formulas.
:::
