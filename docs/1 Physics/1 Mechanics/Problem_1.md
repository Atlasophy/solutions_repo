# Projectile Motion Analysis: Range vs Angle of Projection

import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # gravitational acceleration (m/s^2)
v0 = 20.0  # initial velocity (m/s)
h = 0  # launch height (m)

# Function to calculate range given angle (in degrees)
def calculate_range(theta_deg):
    theta_rad = np.radians(theta_deg)
    range_ = (v0**2 * np.sin(2 * theta_rad)) / g
    return range_

# Angles from 0 to 90 degrees
angles = np.linspace(0, 90, 500)
ranges = calculate_range(angles)

# Plotting
plt.figure(figsize=(10, 6))
plt.plot(angles, ranges)
plt.title("Projectile Range as a Function of Launch Angle")
plt.xlabel("Angle of Projection (degrees)")
plt.ylabel("Range (m)")
plt.grid(True)
plt.show()

# Observations and Limitations
print("""
Observations:
- The range is maximum at 45 degrees for symmetric launch and landing.
- The range is zero at 0° and 90°.

Limitations:
- Assumes no air resistance.
- Assumes flat horizontal landing height.
- For uneven terrain or different launch/landing heights, more complex models are needed.

Next Steps:
- Extend to include launch height effects.
- Incorporate air resistance using numerical simulation (e.g., Euler method).
""")
