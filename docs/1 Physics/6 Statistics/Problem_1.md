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

###  Python Code Snippet (Uniform Example)

```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

np.random.seed(42)

# Generate a uniform population
population = np.random.uniform(0, 1, size=100000)

# Function to sample and calculate sample means
def sample_means(dist, n, reps=1000):
    return [np.mean(np.random.choice(dist, n)) for _ in range(reps)]

sample_sizes = [5, 10, 30, 50]
plt.figure(figsize=(12, 8))

for i, n in enumerate(sample_sizes, 1):
    means = sample_means(population, n)
    plt.subplot(2, 2, i)
    sns.histplot(means, bins=30, kde=True, color='skyblue')
    plt.title(f'Sample Size = {n}')
    plt.xlabel('Sample Mean')
    plt.ylabel('Frequency')

plt.tight_layout()
plt.suptitle("Sampling Distribution of Sample Mean (Uniform)", y=1.02)
plt.show()
