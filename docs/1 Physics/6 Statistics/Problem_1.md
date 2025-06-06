# Problem 1
# Statistics – Problem 1

## Exploring the Central Limit Theorem Through Simulations

---

###  Motivation

The **Central Limit Theorem (CLT)** states:

> _The distribution of sample means approximates a **normal distribution** as the sample size increases, regardless of the population’s original distribution._

This theorem is foundational in:

- Estimating population parameters  
- Constructing confidence intervals  
- Hypothesis testing  
- Machine learning and statistical modeling

Simulating CLT helps build **intuition** behind its power and conditions.

---

## 1 Simulating Sampling Distributions

Choose three distinct population distributions:

- **Uniform Distribution** \( U(a, b) \)  
- **Exponential Distribution** \( \text{Exp}(\lambda) \)  
- **Binomial Distribution** \( \text{Bin}(n, p) \)

For each distribution:

- Generate a large population dataset (e.g., 100,000 points)  
- Visualize the **original distribution**

---

## 2 Sampling and Visualization

### Steps:

1. Choose sample sizes: 5, 10, 30, 50  
2. Draw 1,000 random samples for each sample size  
3. Compute the **mean of each sample**  
4. Plot a **histogram** of the sample means for each size

Expected behavior:

- Small \( n \): Sampling distribution resembles original population  
- Larger \( n \): Sampling distribution approaches a **bell-shaped** curve

---


