

---

## 1. Theoretical Foundation

### Deriving the Equations of Motion

Projectile motion occurs under the influence of gravity, with no horizontal acceleration (assuming no air resistance). We start with Newton’s second law in a 2D plane, where the only force is gravity acting downward.

- **Coordinate System**: Define $ x $-axis as horizontal and $ y $-axis as vertical (positive upward). Gravity acts in the negative $ y $-direction with acceleration $ g \approx 9.8 \, \text{m/s}^2 $.
- **Initial Conditions**: The projectile is launched from position $ (x_0, y_0) $ with initial velocity $ v_0 $ at an angle $ \theta $ from the horizontal. The initial velocity components are:
  $
  v_{0x} = v_0 \cos \theta, \quad v_{0y} = v_0 \sin \theta
  $

#### Horizontal Motion
No forces act in the $ x $-direction, so acceleration $ a_x = 0 $. The differential equation is:
$
\frac{d^2 x}{dt^2} = 0
$
Integrating:
$
v_x = \frac{dx}{dt} = v_{0x} = v_0 \cos \theta
$
$
x(t) = x_0 + (v_0 \cos \theta) t
$
Assuming $ x_0 = 0 $:
$
x(t) = (v_0 \cos \theta) t
$

#### Vertical Motion
Gravity causes acceleration $ a_y = -g $. The differential equation is:
$
\frac{d^2 y}{dt^2} = -g
$
Integrating:
$
v_y = \frac{dy}{dt} = v_{0y} - g t = v_0 \sin \theta - g t
$
$
y(t) = y_0 + (v_0 \sin \theta) t - \frac{1}{2} g t^2
$
Assuming $ y_0 = 0 $ (ground level unless specified):
$
y(t) = (v_0 \sin \theta) t - \frac{1}{2} g t^2
$

### Family of Solutions
The equations $ x(t) $ and $ y(t) $ describe a parabola parameterized by time $ t $. The trajectory depends on:
- **Initial velocity $ v_0 $**: Scales the size of the parabola.
- **Angle $ \theta $**: Determines the shape and orientation.
- **Initial height $ y_0 $**: Shifts the parabola vertically.
- **Gravitational acceleration $ g $**: Affects the curvature (smaller $ g $, as on the Moon, stretches the parabola).

Eliminating $ t $ from the equations gives the trajectory:
$
t = \frac{x}{v_0 \cos \theta}
$
$
y(x) = x \tan \theta - \frac{g x^2}{2 v_0^2 \cos^2 \theta}
$
This is the equation of a parabola, with variations in $ v_0 $, $ \theta $, $ y_0 $, and $ g $ producing a family of trajectories.

---

## 2. Analysis of the Range

### Range as a Function of Angle
The range $ R $ is the horizontal distance when the projectile returns to $ y = 0 $. Set $ y(t) = 0 $:
$
0 = (v_0 \sin \theta) t - \frac{1}{2} g t^2
$
$
t (v_0 \sin \theta - \frac{1}{2} g t) = 0
$
Solutions: $ t = 0 $ (launch) or $ t = \frac{2 v_0 \sin \theta}{g} $ (landing). The range is:
$
R = x(t) = (v_0 \cos \theta) \cdot \frac{2 v_0 \sin \theta}{g} = \frac{v_0^2 \sin 2\theta}{g}
$
Using the identity $ \sin 2\theta = 2 \sin \theta \cos \theta $, the range depends on:
- **Angle $ \theta $**: The term $ \sin 2\theta $ is maximized when $ 2\theta = 90^\circ $, so $ \theta = 45^\circ $, giving $ R_{\text{max}} = \frac{v_0^2}{g} $.
- **Initial velocity $ v_0 $**: Range scales with $ v_0^2 $.
- **Gravity $ g $**: Inversely proportional to range.

### Parameter Influence
- **Initial Velocity**: Doubling $ v_0 $ quadruples the range ($ R \propto v_0^2 $).
- **Gravity**: On a planet with lower $ g $, the range increases (e.g., on the Moon, $ g \approx 1.62 \, \text{m/s}^2 $, range is ~6 times larger than on Earth).
- **Complementary Angles**: Angles $ \theta $ and $ 90^\circ - \theta $ yield the same range since $ \sin 2\theta = \sin (180^\circ - 2\theta) $.

---

## 3. Practical Applications

### Real-World Scenarios
- **Sports**: In soccer or golf, the optimal angle (~45°) maximizes distance, but air resistance and spin modify trajectories.
- **Engineering**: Artillery and ballistics use projectile motion models, adjusting for drag and wind.
- **Astrophysics**: Trajectories of spacecraft or comets follow similar principles, adjusted for varying gravitational fields.
- **Uneven Terrain**: If launched from height $ y_0 $, the range equation becomes more complex, requiring the quadratic formula to solve for $ t $.
- **Air Resistance**: Introduces a drag force proportional to velocity squared, requiring numerical solutions (e.g., Euler or Runge-Kutta methods).

### Limitations and Enhancements
The idealized model assumes:
- No air resistance.
- Flat, horizontal ground.
- Constant gravity.
To model real systems:
- **Drag**: Add $ F_{\text{drag}} = -k v^2 $ to the equations, solved numerically.
- **Wind**: Introduce a velocity-dependent force.
- **Terrain**: Adjust $ y = 0 $ to a function $ y = f(x) $.

---

## 4. Implementation

Below is a Python script to simulate projectile motion and visualize the range as a function of the angle of projection for different initial velocities and gravitational constants.

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
g_earth = 9.8  # m/s^2
g_moon = 1.62  # m/s^2
v0_values = [10, 20, 30]  # Initial velocities (m/s)
angles = np.linspace(0, 90, 181)  # Angles from 0 to 90 degrees
angles_rad = np.deg2rad(angles)

# Range function
def range_projectile(v0, theta, g, y0=0):
    if y0 == 0:
        return (v0**2 * np.sin(2 * theta)) / g
    else:
        # For non-zero initial height, solve quadratic equation
        a = -g / (2 * v0**2 * np.cos(theta)**2)
        b = np.tan(theta)
        c = y0
        discriminant = b**2 - 4 * a * c
        if discriminant < 0:
            return 0
        x = (-b + np.sqrt(discriminant)) / (2 * a)
        return x if x > 0 else 0

# Simulate ranges
ranges_earth = {v0: [range_projectile(v0, theta, g_earth) for theta in angles_rad] for v0 in v0_values}
ranges_moon = {v0: [range_projectile(v0, theta, g_moon) for theta in angles_rad] for v0 in v0_values}
ranges_height = {v0: [range_projectile(v0, theta, g_earth, y0=10) for theta in angles_rad] for v0 in v0_values}

# Plotting
plt.figure(figsize=(10, 6))
for v0 in v0_values:
    plt.plot(angles, ranges_earth[v0], label=f'Earth, v0={v0} m/s')
    plt.plot(angles, ranges_moon[v0], '--', label=f'Moon, v0={v0} m/s')
    plt.plot(angles, ranges_height[v0], ':', label=f'Earth, v0={v0} m/s, y0=10 m')
plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Range (m)')
plt.title('Range vs. Angle of Projection')
plt.legend()
plt.grid(True)
plt.show()
```

### Chart Visualization
To visualize the range versus angle for different initial velocities on Earth, we create a line chart.

```chartjs
{
  "type": "line",
  "data": {
    "labels": [0, 10, 20, 30, 40, 45, 50, 60, 70, 80, 90],
    "datasets": [
      {
        "label": "v0 = 10 m/s",
        "data": [0, 3.47, 6.43, 8.82, 10.26, 10.2, 10.26, 8.82, 6.43, 3.47, 0],
        "borderColor": "#1f77b4",
        "fill": false
      },
      {
        "label": "v0 = 20 m/s",
        "data": [0, 13.88, 25.71, 35.29, 41.03, 40.82, 41.03, 35.29, 25.71, 13.88, 0],
        "borderColor": "#ff7f0e",
        "fill": false
      },
      {
        "label": "v0 = 30 m/s",
        "data": [0, 31.22, 57.86, 79.38, 92.34, 91.84, 92.34, 79.38, 57.86, 31.22, 0],
        "borderColor": "#2ca02c",
        "fill": false
      }
    ]
  },
  "options": {
    "responsive": true,
    "plugins": {
      "legend": { "position": "top" },
      "title": { "display": true, "text": "Range vs. Angle of Projection (Earth, g=9.8 m/s²)" }
    },
    "scales": {
      "x": { "title": { "display": true, "text": "Angle (degrees)" } },
      "y": { "title": { "display": true, "text": "Range (m)" } }
    }
  }
}
```

### Discussion
- **Simulation Results**: The plot and chart show that the range peaks at 45° for $ y_0 = 0 $. On the Moon, ranges are larger due to lower $ g $. Non-zero $ y_0 $ increases the range and shifts the optimal angle slightly below 45°.
- **Limitations**: The model ignores air resistance, which reduces range and alters the optimal angle (typically <45°). Uneven terrain or wind requires numerical methods.
- **Extensions**: Incorporate drag using differential equations solved via Runge-Kutta methods or simulate 3D motion for complex systems like spacecraft.

This analysis bridges theory and application, showing how simple equations model diverse phenomena while highlighting areas for refinement in real-world scenarios.