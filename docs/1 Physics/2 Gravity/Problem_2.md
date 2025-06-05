# Problem 2
# Mechanics – Problem 2

## Escape Velocities and Cosmic Velocities

---

###  Motivation

Understanding **escape velocity** and **cosmic velocities** is fundamental in space science and celestial mechanics. These velocities define the minimum speeds required to:

- **Achieve stable orbit** (First Cosmic Velocity)
- **Escape a planet’s gravity** (Second Cosmic Velocity)
- **Break free from a star system** (Third Cosmic Velocity)

These principles enable:

- Satellite launches  
- Planetary missions  
- Interstellar exploration

---

### Theoretical Foundation

Let \( M \) be the mass of the central celestial body and \( R \) its radius.

#### **1 First Cosmic Velocity** (orbital velocity)

This is the velocity needed to stay in **stable circular orbit** near the surface:

$$
v_1 = \sqrt{\frac{G M}{R}}
$$

#### **2 Second Cosmic Velocity** (escape velocity)

This is the minimum velocity needed to **leave the gravitational field** of the body:

$$
v_2 = \sqrt{2} \cdot v_1 = \sqrt{\frac{2 G M}{R}}
$$

#### **3 Third Cosmic Velocity**

The velocity needed to **escape the gravity of the star system**, e.g. leaving the Sun’s influence from Earth’s orbit:

$$
v_3 = \sqrt{v_2^2 + v_{\text{orbit,planet}}^2}
$$

Where \( v_{\text{orbit,planet}} \) is the orbital velocity of the planet around the star (e.g., Earth's orbital speed around the Sun).

---

###  Numerical Examples

Using:

- \( G = 6.67430 \times 10^{-11} \, \text{m}^3 \text{kg}^{-1} \text{s}^{-2} \)

We can compute these velocities for:

| Body     | Mass (kg)             | Radius (m)           |
|----------|------------------------|-----------------------|
| Earth    | \( 5.972 \times 10^{24} \) | \( 6.371 \times 10^6 \) |
| Mars     | \( 6.39 \times 10^{23} \)  | \( 3.39 \times 10^6 \)  |
| Jupiter  | \( 1.898 \times 10^{27} \) | \( 6.9911 \times 10^7 \) |

---

###  Computational Implementation

#### Example Python Code:
```python
import numpy as np
import matplotlib.pyplot as plt

G = 6.67430e-11  # gravitational constant

# Celestial bodies: name, mass (kg), radius (m)
bodies = {
    "Earth":    (5.972e24, 6.371e6),
    "Mars":     (6.39e23, 3.39e6),
    "Jupiter":  (1.898e27, 6.9911e7)
}

v1_list = []
v2_list = []
labels = []

for body, (mass, radius) in bodies.items():
    v1 = np.sqrt(G * mass / radius)
    v2 = np.sqrt(2 * G * mass / radius)
    v1_list.append(v1)
    v2_list.append(v2)
    labels.append(body)

x = np.arange(len(labels))
width = 0.35

plt.bar(x - width/2, v1_list, width, label='First Cosmic Velocity')
plt.bar(x + width/2, v2_list, width, label='Second Cosmic Velocity')
plt.ylabel('Velocity (m/s)')
plt.title('Cosmic Velocities of Celestial Bodies')
plt.xticks(x, labels)
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()