# Cardinality Estimation - Randomized Algorithms (Assignment #3)

This repository contains a C++ implementation and experimental analysis of various probabilistic cardinality estimation algorithms. The project compares algorithms like **HyperLogLog** and **Recordinality** against true cardinalities from real literary datasets and synthetic Zipfian streams.

## Implemented Algorithms
1.  **HyperLogLog (HLL)** - Standard implementation with small-range correction.
2.  **Recordinality (REC)** - $k$-Recordinality variant.
3.  **Bonus Algorithms:**
    * Probabilistic Counting (PCSA)
    * k-Minimum Values (KMV)
    * MinCount 
    * Adaptive Sampling

## Requirements

### C++
* A C++ compiler (e.g., `g++` or `clang++`).

### Python (For Plotting)
The program generates a Python script to automatically plot the results. You will need:
* **Python 3**
* **Libraries:** `matplotlib`, `pandas`

You can install the Python dependencies via pip:
```bash
pip install matplotlib pandas
```

## Dataset

The program expects a folder named `datasets/` in the project root directory.

This folder must contain the text files (`.txt`) and their corresponding true cardinality files (`.dat`) exactly as provided in the course ZIP file. File names and structure must not be modified.

### Expected Directory Structure

.
├── assignment3.cpp  
├── README.md  
└── datasets/  
&nbsp;&nbsp;&nbsp;&nbsp;├── crusoe.txt  
&nbsp;&nbsp;&nbsp;&nbsp;├── crusoe.dat  
&nbsp;&nbsp;&nbsp;&nbsp;├── dracula.txt  
&nbsp;&nbsp;&nbsp;&nbsp;├── dracula.dat  
&nbsp;&nbsp;&nbsp;&nbsp;├── iliad.txt  
&nbsp;&nbsp;&nbsp;&nbsp;├── iliad.dat  
&nbsp;&nbsp;&nbsp;&nbsp;├── mare-balena.txt  
&nbsp;&nbsp;&nbsp;&nbsp;├── mare-balena.dat  
&nbsp;&nbsp;&nbsp;&nbsp;├── midsummer-nights-dream.txt  
&nbsp;&nbsp;&nbsp;&nbsp;├── midsummer-nights-dream.dat  
&nbsp;&nbsp;&nbsp;&nbsp;├── quijote.txt  
&nbsp;&nbsp;&nbsp;&nbsp;├── quijote.dat  
&nbsp;&nbsp;&nbsp;&nbsp;├── valley-fear.txt  
&nbsp;&nbsp;&nbsp;&nbsp;├── valley-fear.dat  
&nbsp;&nbsp;&nbsp;&nbsp;└── war-peace.txt  
&nbsp;&nbsp;&nbsp;&nbsp;└── war-peace.dat  

---

## Compilation and Execution

### 1. Compile the C++ Code

Open a terminal in the project root and run:
```bash
g++ -Wall -O2 assignment3.cpp
```

### 2. Run the Experiment
```bash
./a.out
```

## Output

The program produces two types of output:

### Console Output

Detailed tables are printed to the terminal showing:
* Average Estimate
* Relative Error (%)
for every algorithm across all 8 datasets:
* crusoe.txt
* dracula.txt
* iliad.txt
* mare-balena.txt
* midsummer-nights-dream.txt
* quijote.txt
* valley-fear.txt
* war-peace.txt

The output also includes the results of the Alpha Skewness hypothesis test.

### Generated Figures (Plots) 

A Python script is automatically triggered to generate two PNG images in the project root directory:
* `hll_plot.png`
Visualizes how the HyperLogLog error decreases as the number of registers (m) increases.
* `rec_plot.png`
Visualizes how the Recordinality error decreases as the sample size (k) increases.
