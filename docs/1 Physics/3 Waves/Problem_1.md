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

###  Python Simulation

#### Example Code (Square Configuration)
```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
A = 1.0            # amplitude
wavelength = 1.0   # lambda
frequency = 1.0    # f
k = 2 * np.pi / wavelength
omega = 2 * np.pi * frequency
t = 0              # fixed time

# Source positions at square vertices
side = 2.0
polygon_sides = 4
radius = 1.0
sources = [
    (radius * np.cos(2*np.pi*i/polygon_sides),
     radius * np.sin(2*np.pi*i/polygon_sides))
    for i in range(polygon_sides)
]

# Grid
res = 500
x = np.linspace(-2, 2, res)
y = np.linspace(-2, 2, res)
X, Y = np.meshgrid(x, y)
Z = np.zeros_like(X)

# Superposition
for sx, sy in sources:
    R = np.sqrt((X - sx)**2 + (Y - sy)**2)
    Z += A * np.cos(k * R - omega * t)

# Plot
plt.figure(figsize=(8, 6))
plt.contourf(X, Y, Z, levels=200, cmap='RdBu')
plt.colorbar(label='Displacement η(x, y)')
plt.title('Interference Pattern – Square Wave Sources')
plt.xlabel('x')
plt.ylabel('y')
plt.axis('equal')
plt.show()