İşte “Projectile Motion: Investigating the Range as a Function of the Angle of Projection” başlıklı problemi, tüm bölümleriyle birlikte Markdown + MathJax uyumlu HTML formatında yazılmış hali. Bu dosyayı doğrudan GitHub Pages, Jupyter Notebook veya Markdown destekli bir bloga ekleyebilirsin.

⸻


# Mechanics – Problem 1

## Investigating the Range as a Function of the Angle of Projection

---

### 🎯 Motivation

Projectile motion demonstrates key physical principles through accessible equations. The relationship between range and angle is **non-linear** and highly **sensitive** to parameters like **initial speed** and **gravity**. By analyzing this systematically, we reveal how small changes in conditions lead to drastically different outcomes — useful in sports, engineering, and military contexts.

---

### 📐 Theoretical Foundation

From **Newton’s Second Law**, the motion of a projectile (ignoring air resistance) is described by:

- **Horizontal motion:**

  $$
  x(t) = v_0 \cdot \cos(\theta) \cdot t
  $$

- **Vertical motion:**

  $$
  y(t) = v_0 \cdot \sin(\theta) \cdot t - \frac{1}{2} g t^2
  $$

---

### ⏱ Time of Flight (T)

Assuming the projectile lands at the same height it was launched:

$$
T = \frac{2 v_0 \cdot \sin(\theta)}{g}
$$

---

### 📏 Range (R)

Substitute \( T \) into the horizontal position equation:

$$
R = v_0 \cdot \cos(\theta) \cdot T = \frac{v_0^2 \cdot \sin(2\theta)}{g}
$$

---

### 📊 Analysis of the Range

- For a fixed \( v_0 \) and \( g \), the range is **symmetric** around \( \theta = 45^\circ \).
- Increasing initial velocity \( v_0 \) **quadratically increases** the range.
- Higher gravitational acceleration \( g \) **reduces** the range.

---

### 🌍 Practical Applications

- **Sports**: Optimizing throw angles in javelin, football, or basketball.
- **Military**: Calculating artillery or missile trajectories.
- **Engineering**: Drone launches, rocket design, ballistic modeling.

---

### ⚠️ Limitations and Extensions

- **Air Resistance**: Reduces range and shifts the optimal angle **below 45°**.
- **Uneven Terrain**: Requires solving with a **non-zero final height**.
- **Wind Effects**: Add lateral and vertical components that require solving **differential equations**.

---

### 🧪 3D Simulation and Visualization

- The range can be visualized as a function of the launch angle \( \theta \) using simulations.
- 2D plots with `matplotlib` or 3D simulations using `plotly` or `vpython` can illustrate this.
- Example plots: **Range vs. Angle** for different initial speeds.

---

### 🗂️ Deliverables

- 📄 A Markdown or HTML document with theory, equations, and explanation.
- 💻 Python simulation script for projectile motion.
- 📈 Graphs showing how the range changes with angle and velocity.
- 🧠 Discussion on limitations and how to improve the model (e.g., air resistance, terrain).

---


⸻

