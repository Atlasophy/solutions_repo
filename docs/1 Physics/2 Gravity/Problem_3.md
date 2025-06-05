# Problem 3
# Mechanics – Problem 3

## Trajectories of a Freely Released Payload Near Earth

---

###  Motivation

When a payload is released from a **moving rocket near Earth**, its future path is determined by:

- Its **initial velocity**
- Its **position** relative to Earth
- The **gravitational pull** from Earth

These trajectories may result in:

- Orbital insertion  
- Earth reentry  
- Complete escape from Earth’s gravity

This analysis is crucial for space missions involving **satellite deployment**, **reentry capsules**, or **interplanetary probes**.

---

###  Theoretical Foundation

Use **Newton’s Law of Gravitation**:

$$
F = \frac{G M m}{r^2}
$$

From Newton’s Second Law:

$$
\vec{a} = - \frac{G M}{r^2} \cdot \hat{r}
$$

Where:

- \( G \): Gravitational constant  
- \( M \): Mass of Earth  
- \( r \): Distance from Earth’s center  
- \( \vec{a} \): Acceleration due to gravity  

---

###  Possible Trajectories

Depending on the **total mechanical energy** of the payload:

- **Elliptical Orbit**: Bound trajectory (energy < 0)
- **Parabolic Path**: Critical escape condition (energy = 0)
- **Hyperbolic Path**: Escape trajectory (energy > 0)

Specific energy \( \epsilon \):

$$
\epsilon = \frac{v^2}{2} - \frac{G M}{r}
$$

---

###  Numerical Simulation

Simulate motion using numerical integration (e.g., **Runge-Kutta 4th order**) of the equations of motion in Cartesian coordinates:

$$
\frac{d^2x}{dt^2} = - \frac{G M x}{(x^2 + y^2)^{3/2}} \\
\frac{d^2y}{dt^2} = - \frac{G M y}{(x^2 + y^2)^{3/2}}
$$

---

#### Example Python (Concept):
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

G = 6.67430e-11
M = 5.972e24

def equations(t, y):
    x, vx, y_, vy = y
    r = np.sqrt(x**2 + y_**2)
    ax = -G * M * x / r**3
    ay = -G * M * y_ / r**3
    return [vx, ax, vy, ay]

# Initial conditions
r0 = 7e6  # 700 km altitude
v0 = 7500  # initial velocity
y0 = [r0, 0, 0, v0]

sol = solve_ivp(equations, [0, 10000], y0, max_step=1)

plt.plot(sol.y[0], sol.y[2])
plt.xlabel("x (m)")
plt.ylabel("y (m)")
plt.title("Trajectory of Released Payload")
plt.axis('equal')
plt.grid(True)
plt.show()