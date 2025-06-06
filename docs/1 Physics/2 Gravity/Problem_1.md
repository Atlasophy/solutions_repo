# Problem 1
# Mechanics – Problem 1

## Orbital Period and Orbital Radius

---

###  Motivation

The relationship between the **square of the orbital period** and the **cube of the orbital radius**, known as **Kepler's Third Law**, is a cornerstone of **celestial mechanics**.

This law connects gravitational principles to real-world phenomena, such as:

- Planetary motion  
- Satellite orbits  
- Galaxy rotation

Understanding this relationship allows us to calculate:

- Orbital parameters  
- Planetary masses  
- Distances between celestial bodies

---

###  Theoretical Foundation

Start with **Newton’s Law of Gravitation** and **centripetal force** for a circular orbit.

####  Gravitational Force:
$$
F = \frac{G M m}{r^2}
$$

####  Centripetal Force:
$$
F = \frac{m v^2}{r}
$$

Set them equal for orbital motion:

$$
\frac{G M m}{r^2} = \frac{m v^2}{r}
$$

Simplify:

$$
v^2 = \frac{G M}{r}
$$

Now express the orbital period \( T \) in terms of orbital speed:

$$
T = \frac{2\pi r}{v}
$$

Substitute \( v \):

$$
T = \frac{2\pi r}{\sqrt{\frac{G M}{r}}} = 2\pi \sqrt{\frac{r^3}{G M}}
$$

###  Kepler’s Third Law

This result gives the **mathematical form** of Kepler’s Third Law:

$$
T^2 \propto r^3
$$

Where:

- \( T \): Orbital period  
- \( r \): Orbital radius  
- \( G \): Gravitational constant  
- \( M \): Mass of the central object

---

###  Applications in Astronomy

-  **Satellites**: Predicting geostationary orbits and launch parameters  
-  **Moon-Earth**: Confirming gravitational parameters  
-  **Solar System**: Measuring planetary distances from orbital data  
-  **Exoplanets**: Estimating mass and radius of distant systems

---

###  Computational Implementation

Simulate circular orbits with a Python program. Given \( M \), simulate values of \( r \), compute \( T \), and plot:

- \( T^2 \) vs. \( r^3 \)
- Orbit paths for visualization

[Simulation](Gravity1.html)