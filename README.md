# optimising-numerical-code
Practical guide on writing fast and memory efficient code in python.

<div align="center">
  
# 🚀 Optimizing Numerical Code in Python
  
*A practical deep-dive into writing blazingly fast, memory-efficient, and production-ready numerical computations.*

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-Optimized-blue.svg)](https://numpy.org/)
[![Numba](https://img.shields.io/badge/Numba-JIT_Compiled-orange.svg)](https://numba.pydata.org/)

</div>

---

## 📖 Overview
Python is incredibly versatile, but standard `for` loops can become a severe bottleneck when processing massive numerical datasets. Optimizing numerical code is about transcending these speed limits to reduce computation time, memory usage, and unnecessary overhead. 

Imagine dealing with millions of data points. As data grows, computation time increases drastically if inefficient code is used. By leveraging vectorization and Just-In-Time (JIT) compilation, you can execute complex operations at near C-level speeds while maintaining Python's clean, readable syntax.

---

## 🛠️ The Arsenal (Core Concepts)

This repository, based on the `Optimising_numerical_code.ipynb` notebook, breaks down four critical performance pillars:

| Concept | Description | Key Benefit |
| :--- | :--- | :--- |
| **🎯 Vectorized Patterns** | Replaces explicit Python loops with operations on entire arrays using NumPy. | Leverages optimized C and Fortran under the hood for broadcasting, extreme memory efficiency, and speed. |
| **⚡ JIT Compilation (Numba)** | Uses tools like Numba (`@jit`) to compile Python code to machine code at runtime. | The perfect second-level accelerator for accelerating math-heavy loops that cannot be vectorized easily. |
| **⏱️ Macro Profiling** | Measuring how long different paths of your code take to run using `%timeit`, `cProfile`, or the `time` module. | Provides a high-level view of function-call overhead (e.g., matrix inversions and dot products) to identify bottlenecks before scaling. |
| **🔬 Line-by-Line Profiling** | Using the `line_profiler` module to analyze the execution time of code line-by-line. | Grants granular, targeted insights into exactly which specific operations are slowing down your computations. |

---

## 💼 Real-World Applications

Writing code that works is the baseline; writing code that scales is the mark of a professional. The techniques demonstrated here directly apply to:

* **Machine Learning:** Quickly process large datasets and matrix multiplications with minimal overhead.
* **High-Performance Computing:** Accelerate complex mathematical transformations to near C-speed.
* **Data Engineering:** Build optimized data pipelines that save on cloud computing costs and execution time.
* **Algorithmic Efficiency:** Debug and profile real-world applications intelligently rather than guessing where the bottlenecks are.

---

## 💻 Code Snapshot: Combining the Tools

Here is a quick look at how vectorization and JIT compilation combine to provide ultimate flexibility and speed for complex computations:

```python
import numpy as np
from numba import jit

# Combining JIT acceleration with vectorized NumPy functions
@jit
def complex_transform(arr):
  res = np.zeros_like(arr)
  for i in range(arr.size):
    # Numba accelerates the loop, NumPy handles the math efficiently
    res[i] = np.sin(arr[i] ** 2 + np.log1p(arr[i]))
  return res

# 1. Create a large dataset
arr = np.arange(1, 1000000)

# 2. Execute the optimized transformation
result = complex_transform(arr)

print(f"Processed {arr.size} elements efficiently!")
```

## Getting started (how to run locally)
1. Clone repository: git clone [https://github.com/aksharma-15/optimizing-numerical-code.git](https://github.com/aksharma-15/optimizing-numerical-code.git)
2. Install dependencies (make sure you've installed Python 3): pip install numpy numba line_profiler
3. Launch notebook: jupyter notebook Optimising_numerical_code.ipynb
