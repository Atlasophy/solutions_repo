# Problem 2
# Probability & Simulation – Problem 2

## Estimating π Using Monte Carlo Methods

---

###  Motivation

**Monte Carlo simulations** leverage randomness to solve problems that may be deterministic in nature. One elegant application is **estimating the value of π (pi)** through geometric probability.

This problem demonstrates how **random sampling** and **basic geometry** can be combined to approximate mathematical constants—highlighting important concepts in **probability**, **numerical methods**, and **simulation science**.

---

##  PART 1: Estimating π Using a Circle

---

### 1 Theoretical Foundation

Consider a **unit circle** inscribed in a square of side length 2 (centered at the origin). The area of:

- The circle is:  
  $$
  A_{\text{circle}} = \pi r^2 = \pi \cdot 1^2 = \pi
  $$

- The square is:  
  $$
  A_{\text{square}} = (2r)^2 = 4
  $$

Thus, the ratio of the two areas is:  
$$
\frac{A_{\text{circle}}}{A_{\text{square}}} = \frac{\pi}{4} \Rightarrow \pi \approx 4 \cdot \frac{\text{Points inside circle}}{\text{Total points}}
$$

---

[Simulation](problem2sim.html)