# Waves – Problem 1

## Interference Patterns on a Water Surface

---

###  Motivation

When waves from different sources **overlap**, they **interfere**, producing beautiful and informative **interference patterns**. On a **water surface**, this phenomenon is especially easy to observe:

- **Constructive interference**: Waves **reinforce** each other.
- **Destructive interference**: Waves **cancel** each other.

Studying these patterns allows us to explore:

- Phase relationships  
- Wavefront interaction  
- The fundamentals of **superposition**

This problem provides a hands-on, visual way to understand key wave principles.

---

###  Theoretical Foundation

A **circular wave** from a point source located at \( \vec{r}_i \) can be modeled as:

$$
\eta_i(\vec{r}, t) = A \cdot \cos(k \cdot |\vec{r} - \vec{r}_i| - \omega t + \phi)
$$

Where:

- \( \eta_i(\vec{r}, t) \): Displacement at position \( \vec{r} \) and time \( t \)  
- \( A \): Amplitude  
- \( k = \frac{2\pi}{\lambda} \): Wave number  
- \( \omega = 2\pi f \): Angular frequency  
- \( \vec{r}_i \): Position of source \( i \)  
- \( \phi \): Initial phase (can be taken as 0 for all sources)

---

###  Problem Statement

Analyze the interference pattern from **multiple point sources** placed at the **vertices of a regular polygon**.

#### Steps:

1. **Select a Regular Polygon**: E.g., equilateral triangle, square, or pentagon.  
2. **Position the Sources**: Distribute them evenly around a circle.  
3. **Construct Wave Equations**: One for each source.  
4. **Apply Superposition Principle**:

$$
\eta(\vec{r}, t) = \sum_{i=1}^N \eta_i(\vec{r}, t)
$$

5. **Visualize**: At fixed time \( t \), compute and plot \( \eta(\vec{r}) \) on a 2D grid.  
6. **Interpret**: Identify constructive and destructive regions.

---
[Simulation](Sim6.html)