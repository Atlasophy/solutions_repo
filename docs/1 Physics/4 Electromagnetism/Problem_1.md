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
-  Mass spectrometers.  
-  Astrophysics and cosmic ray deflection.  
-  Plasma confinement in fusion reactors.

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
[Simulation](circuitsim.html)