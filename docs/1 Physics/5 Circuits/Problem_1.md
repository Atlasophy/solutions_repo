# Circuits – Problem 1

## Equivalent Resistance Using Graph Theory

---

###  Motivation

Calculating **equivalent resistance** is crucial in circuit design and analysis. Traditional methods using series and parallel rules become inefficient for **complex networks**.

By using **graph theory**, we can:

- Represent circuits as weighted graphs  
- Systematically reduce complex topologies  
- Automate simplification using algorithms  
- Explore deeper connections between **electrical engineering** and **mathematics**

---

##  Task Options

---

###  OPTION 1: Algorithm Description (Simplified Task)

---

###  Theoretical Foundation

Represent the circuit as an **undirected graph**:

- **Nodes**: Circuit junctions  
- **Edges**: Resistors (with weights = resistance values)

#### Key Concepts:

- **Series Connection**: A node with degree 2 connecting two resistors  
- **Parallel Connection**: Multiple edges between the same pair of nodes

---

###  Algorithm Steps

1. **Input**: Graph \( G = (V, E) \) with weighted edges  
2. **Repeat until only two nodes remain** (source and sink):

   a. **Find all series nodes**:
   - If a node has degree 2 and is not source/sink  
   - Replace its two adjacent edges with one edge:
     $$
     R_{eq} = R_1 + R_2
     $$

   b. **Find all parallel edges**:
   - If multiple edges connect the same node pair  
   - Replace them with one edge:
     $$
     \frac{1}{R_{eq}} = \sum_{i} \frac{1}{R_i}
     $$

3. **Output**: The remaining edge's weight = equivalent resistance

---
[Simulation](circuitsim.html)
