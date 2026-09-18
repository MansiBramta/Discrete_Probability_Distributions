# Common Discrete Probability Distributions

This repository contains the concepts, mathematical derivations, examples, and Python implementations discussed in my article on **Common Discrete Probability Distributions**.

The article focuses on understanding these distributions through the **questions they answer**, rather than only memorizing their formulas.

## Distributions Covered

The repository covers six commonly used discrete probability distributions:

1. **Bernoulli Distribution** — What is the outcome of a single trial with two possible outcomes?
2. **Binomial Distribution** — How many successes occur in a fixed number of independent trials?
3. **Multinomial Distribution** — How many times does each category occur across multiple trials?
4. **Geometric Distribution** — How many trials do we need until the first success?
5. **Negative Binomial Distribution** — How many trials do we need until the \(r\)-th success?
6. **Poisson Distribution** — How many times does an event occur within a fixed interval?

## What This Repository Covers

For each distribution, the repository covers:

* Intuition behind the distribution
* Probability Mass Function (PMF)
* Mean
* Variance
* Mathematical derivations
* Worked examples
* Python implementation using `scipy.stats`

## Mathematical Summary

| Distribution | What does it answer? | Mean | Variance |
|---|---|---|---|
| Bernoulli | Success or failure in one trial | $p$ | $p(1-p)$ |
| Binomial | Number of successes in $n$ trials | $np$ | $np(1-p)$ |
| Multinomial | Counts across multiple categories | $np_i$ | $np_i(1-p_i)$ |
| Geometric | Trials until the first success | $\frac{1}{p}$ | $\frac{1-p}{p^2}$ |
| Negative Binomial | Trials until the $r$-th success | $\frac{r}{p}$ | $\frac{r(1-p)}{p^2}$ |
| Poisson | Number of events in a fixed interval | $\lambda$ | $\lambda$ |
## Python Libraries Used

The examples use:

```python
from scipy.stats import bernoulli
from scipy.stats import binom
from scipy.stats import multinomial
from scipy.stats import geom
from scipy.stats import nbinom
from scipy.stats import poisson
```

The main library used is **SciPy**, particularly `scipy.stats`, for calculating PMFs, means, and variances.

## Important Note on Negative Binomial

There are different conventions for defining the Negative Binomial distribution.

In this article, \(X\) represents:

> **The number of trials until the \(r\)-th success.**

However, SciPy's `nbinom` uses:

> **The number of failures before the \(r\)-th success.**

For example, if the 3rd success occurs on the 8th trial:

* Total trials = 8
* Successes = 3
* Failures = \(8-3=5\)

Therefore, in SciPy:

```python
probability = X.pmf(5)
```

The difference in parameterization is important when implementing the Negative Binomial distribution in Python.

## Repository Structure

```text
common-discrete-probability-distributions/
│
├── bernoulli/
├── binomial/
├── multinomial/
├── geometric/
├── negative-binomial/
├── poisson/
│
└── README.md
```

## Learning Goal

The main goal of this repository is to build an intuitive understanding of **why each distribution exists, what question it answers, and how its mathematical formula connects to the underlying experiment**.

Instead of memorizing six separate formulas, the distributions can be understood by asking:

**What exactly are we counting or waiting for?**

---

## Next Topic

This article covers **Discrete Probability Distributions**.

The next part of the series will move towards **Continuous Probability Distributions**.
