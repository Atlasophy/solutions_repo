# Problem 1
# Experimental Physics – Problem 1

## Measuring Earth’s Gravitational Acceleration with a Pendulum

---

###  Motivation

The acceleration due to gravity \( g \) is a **universal physical constant** influencing all falling objects. A **simple pendulum** provides a time-tested method for measuring local \( g \), offering an opportunity to:

- Apply experimental methods  
- Perform **uncertainty analysis**  
- Compare with theoretical standards

This activity emphasizes precision, statistical analysis, and the **real-world challenges** of measurement.

---

##  Procedure

### 1 Materials

- A string (1–1.5 meters)
- Small mass (e.g., keys, weight, sugar bag)
- Stopwatch or smartphone timer
- Measuring tape or ruler (noting resolution)

---

### 2 Setup

- Suspend the pendulum from a fixed support
- Measure pendulum **length** \( L \) from the suspension point to the **center of mass**
- Record:
  - Measured \( L \)
  - Tool resolution \( \delta L_{\text{res}} \)
  - Uncertainty in length:  
    $$
    u_L = \frac{\delta L_{\text{res}}}{2}
    $$

---

### 3 Data Collection

- Displace pendulum <15° (small angle approximation)
- Measure time for **10 full oscillations**, repeat **10 times**

---

###  Example Data Table

| Trial | Time for 10 Oscillations \( t_{10} \) [s] |
|-------|--------------------------------------------|
| 1     | 20.12                                      |
| 2     | 20.08                                      |
| 3     | 20.15                                      |
| 4     | 20.05                                      |
| 5     | 20.10                                      |
| 6     | 20.13                                      |
| 7     | 20.09                                      |
| 8     | 20.14                                      |
| 9     | 20.07                                      |
| 10    | 20.11                                      |

---

##  Calculations

### 1 Mean and Standard Deviation

Let:
- \( \overline{t_{10}} \): Mean time for 10 oscillations  
- \( s_{t_{10}} \): Standard deviation of \( t_{10} \)  
- \( n = 10 \): Number of trials

Then:
- Mean time for **1 oscillation** (period):
  $$
  T = \frac{\overline{t_{10}}}{10}
  $$

- Uncertainty in mean:
  $$
  u_T = \frac{s_{t_{10}}}{10 \sqrt{n}}
  $$

---

### 2 Determining \( g \)

The pendulum period equation:

$$
T = 2\pi \sqrt{\frac{L}{g}} \Rightarrow g = \frac{4\pi^2 L}{T^2}
$$

---

### 3 Uncertainty in \( g \)

Using uncertainty propagation:

$$
u_g = g \cdot \sqrt{\left(\frac{u_L}{L}\right)^2 + \left(2 \cdot \frac{u_T}{T}\right)^2}
$$

---

##  Example Results

Assume:

- \( L = 1.000 \, \text{m} \pm 0.005 \, \text{m} \)  
- \( \overline{t_{10}} = 20.10 \, \text{s} \Rightarrow T = 2.010 \, \text{s} \)  
- \( s_{t_{10}} = 0.03 \Rightarrow u_T = 0.00095 \, \text{s} \)

Then:

- \( g = \frac{4 \pi^2 \cdot 1.000}{2.010^2} \approx 9.78 \, \text{m/s}^2 \)  
- \( u_g \approx 0.08 \, \text{m/s}^2 \)

Final Result:

$$
g = 9.78 \pm 0.08 \, \text{m/s}^2
$$

---

##  Analysis

###  Comparison

- Standard \( g = 9.80665 \, \text{m/s}^2 \)
- Deviation is within expected uncertainty bounds

---

###  Discussion

- **Resolution effect**: Coarse measuring tools increase \( u_L \), thus increasing \( u_g \)
- **Timing variability**: Manual stopwatch leads to uncertainty in \( T \)
- **Experimental assumptions**:
  - Small angle approximation valid only for θ < 15°
  - Neglects air resistance and friction

---

##  Deliverables

###  Markdown Output:

- 📊 Table with raw data \( t_{10} \)  
- 📉 Calculated:
  - \( T \), \( u_T \), \( g \), \( u_g \)  
- 📈 Final result with uncertainty

###  Interpretation:

- Comparison with standard gravity  
- Discussion on uncertainty sources  
- Suggestions for improvement (e.g., photogates, longer pendulums)

---

##  Hints & Extensions

- Try different lengths to test \( T \propto \sqrt{L} \)  
- Plot \( T^2 \) vs \( L \) and fit a line to estimate \( g \)  
- Use statistical tools (e.g., `numpy.std`, `scipy.stats.sem`)  
- Repeat with a digital timer for more precision

---
[Simulation](Measurementsim.html)

