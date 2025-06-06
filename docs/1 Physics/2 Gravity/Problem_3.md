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

[Simulation](Gravity/Sim5.html)