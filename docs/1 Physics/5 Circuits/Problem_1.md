# Problem 1
# Electromagnetism – Problem 1

## Simulating the Effects of the Lorentz Force

---

###  Motivation

The **Lorentz Force**, defined by:

$$
\vec{F} = q (\vec{E} + \vec{v} \times \vec{B})
$$

is the fundamental law governing the motion of **charged particles** in **electric** and **magnetic fields**.

This concept is crucial in:

-  Particle accelerators (e.g., cyclotrons, synchrotrons)  
-  Mass spectrometers  
-  Astrophysics and cosmic ray deflection  
-  Plasma confinement in fusion reactors

Simulation offers an intuitive way to visualize these effects and better understand real-world applications.

---

## 1 Exploration of Applications

### Real-World Systems

| Application           | Role of Lorentz Force |
|------------------------|------------------------|
| Particle Accelerators  | Guides particles in circular paths with magnets |
| Mass Spectrometers     | Separates ions by mass/charge ratio using \( \vec{E} \) and \( \vec{B} \) |
| Magnetic Traps         | Constrains plasma particles using magnetic mirrors |
| Earth’s Magnetosphere  | Deflects charged cosmic particles |

---

## 2 Simulating Particle Motion

We solve Newton’s second law for a charged particle:

$$
m \frac{d\vec{v}}{dt} = q (\vec{E} + \vec{v} \times \vec{B})
$$

Numerical integration (e.g., Euler, Runge-Kutta) allows us to simulate:

- Motion in uniform \( \vec{B} \)-field  
- Motion in uniform \( \vec{E} \)-field  
- Crossed \( \vec{E} \) and \( \vec{B} \) fields

---

###  Python Implementation (Basic Case)

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
q = 1.6e-19     # charge (C)
m = 9.1e-31     # mass (kg)
B = np.array([0, 0, 1])     # uniform magnetic field
E = np.array([0, 0, 0])     # electric field

# Initial conditions
v = np.array([1e5, 0, 0])
r = np.array([0, 0, 0])
dt = 1e-11
steps = 1000

trajectory = []

for _ in range(steps):
    F = q * (E + np.cross(v, B))
    a = F / m
    v += a * dt
    r += v * dt
    trajectory.append(r.copy())

trajectory = np.array(trajectory)
plt.plot(trajectory[:,0], trajectory[:,1])
plt.xlabel("x (m)")
plt.ylabel("y (m)")
plt.title("Charged Particle in Uniform Magnetic Field")
plt.axis('equal')
plt.grid(True)
plt.show()
