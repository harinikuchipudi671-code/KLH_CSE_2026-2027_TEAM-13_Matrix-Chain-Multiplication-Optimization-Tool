# Matrix Chain Multiplication Optimization Tool

## 1. Project Overview

The **Matrix Chain Multiplication Optimization Tool** is a Data Structures and Algorithms (DSA-3) project that uses Dynamic Programming to find the most efficient order for multiplying a sequence of matrices.

Matrix multiplication is associative, which means the order of grouping matrices can change without changing the final result. However, different multiplication orders may require different numbers of scalar multiplications.

This project calculates the minimum multiplication cost, compares it with the traditional left-to-right multiplication strategy, and displays the results through a web interface.

## 2. Problem Statement

Given a sequence of matrices with compatible dimensions, determine the optimal parenthesization that minimizes the total number of scalar multiplications.

The project also compares the optimal cost with the cost of multiplying the matrices from left to right and displays the cost table and split table used by the Dynamic Programming algorithm.

## 3. Objectives

- Implement Matrix Chain Multiplication using Dynamic Programming.
- Minimize the number of scalar multiplications.
- Compare optimal multiplication cost with left-to-right multiplication cost.
- Generate the optimal parenthesization.
- Display the cost table and split table.
- Visualize cost differences using a comparison chart.
- Provide a step-by-step explanation of the DP algorithm.
- Support sample datasets and CSV upload and download.
- Provide a simple, responsive web interface.

## 4. Technologies Used

- **Java:** Implements the Dynamic Programming algorithm and backend server.
- **HTML:** Structures the web interface.
- **CSS:** Styles the website and its responsive layout.
- **JavaScript:** Handles user interactions, API requests, charts, tables, and CSV operations.
- **CSV:** Stores sample matrix dimension test cases.
- **Git and GitHub:** Used for version control and project documentation.

## 5. Project Structure

```text
website/
├── WebServer.java
├── MatrixChain.java
├── matrix_dataset.csv
├── README.md
├── README_Member1.md
├── README_Member2.md
├── README_Member3.md
└── web/
    ├── index.html
    ├── style.css
    └── script.js
```

## 6. Algorithm Used

The project uses the Matrix Chain Multiplication Dynamic Programming algorithm.

Let the dimension sequence be:

`p0, p1, p2, ..., pn`

The matrices have dimensions:

- A1: p0 × p1
- A2: p1 × p2
- A3: p2 × p3
- And so on.

Let `m[i][j]` represent the minimum number of scalar multiplications required to multiply matrices Ai through Aj.

### Base Case

A single matrix does not require multiplication.

`m[i][i] = 0`

### Recurrence Relation

For a chain containing more than one matrix:

`m[i][j] = min(m[i][k] + m[k+1][j] + p[i-1] × p[k] × p[j])`

Here, `k` represents each possible split point between matrices Ai and Aj, using the conventional one-based matrix indexing.

The algorithm evaluates different subchains and stores the minimum cost for each interval.

### Complexity Analysis

- **Time Complexity:** O(n³)
- **Space Complexity:** O(n²)

Here, `n` is the number of matrices.

## 7. Features

### Matrix Dimension Input
Users can enter a sequence of positive matrix dimensions.

### Optimal Cost Calculation
The application calculates the minimum number of scalar multiplications using Dynamic Programming.

### Cost Comparison
The tool compares the optimal strategy with left-to-right multiplication and calculates the cost saved.

### Optimal Parenthesization
The application displays the multiplication order that achieves the minimum cost.

### Cost and Split Tables
The cost table stores minimum multiplication costs for matrix intervals. The split table stores the selected split positions.

### Cost Comparison Chart
A bar chart visually compares the left-to-right cost with the optimal Dynamic Programming cost.

### DP Walkthrough
The interface explains the algorithm's stages, recurrence relation, and final result.

### CSV Dataset Management
Users can load sample test cases, upload a CSV dataset, and download the dataset.

## 8. Sample Input and Output

**Input dimensions:**

`40 20 30 10`

This represents three matrices:

- A1: 40 × 20
- A2: 20 × 30
- A3: 30 × 10

**Expected results:**

| Metric | Result |
|---|---:|
| Optimal multiplication cost | 14,000 |
| Left-to-right multiplication cost | 36,000 |
| Cost saved | 22,000 |
| Cost reduction | 61.11% |
| Number of matrices | 3 |

Optimal parenthesization:

`(A1 × (A2 × A3))`

## 9. Installation and Execution

### Prerequisites

- Java Development Kit (JDK) installed.
- Visual Studio Code or another code editor.
- A modern web browser.

### Step 1: Open the project folder

Open the terminal in the folder containing `WebServer.java` and `MatrixChain.java`.

### Step 2: Compile the Java files

```bash
javac WebServer.java MatrixChain.java
```

### Step 3: Start the server

```bash
java WebServer
```

### Step 4: Open the application

Visit:

`http://localhost:8080`

Keep the terminal running while using the website.

## 10. Testing

The project can be tested using different matrix dimension sequences.

Testing should cover:

- Two matrices and longer matrix chains.
- Inputs that benefit from optimal parenthesization.
- Inputs with equal or varied dimensions.
- Invalid or non-positive dimensions.
- CSV dataset loading, uploading, and downloading.
- Correctness of the cost table and split table.
- Correctness of the cost comparison chart and displayed results.

## 11. Applications

- Studying Dynamic Programming.
- Understanding optimization problems.
- Comparing alternative computational strategies.
- Demonstrating time and space complexity.
- Learning how algorithms can be integrated into web applications.

## 12. Limitations

- The algorithm's cubic time complexity can make very large inputs computationally expensive.
- Memory usage increases quadratically with the number of matrices.
- Actual runtime depends on hardware and implementation details.
- The tool minimizes scalar multiplication count; it does not directly optimize real hardware execution time or memory transfers.

## 13. Future Enhancements

- Display individual split calculations and intermediate DP table updates.
- Add downloadable optimization reports.
- Add more test cases and automated correctness tests.
- Improve input validation and error messages.
- Add performance measurements for different matrix-chain sizes.

## 14. Team Contributions

The project is divided into three main areas:

- **Member 1:** Dynamic Programming algorithm and Java backend.
- **Member 2:** Website interface, styling, visualization, and walkthrough.
- **Member 3:** Dataset management, integration, testing, and documentation.

All members contribute to integration, validation, debugging, and final project review.

## 15. Conclusion

The Matrix Chain Multiplication Optimization Tool demonstrates how Dynamic Programming can solve a computational optimization problem efficiently by storing and reusing subproblem results. The web interface makes the algorithm easier to explore by presenting multiplication costs, optimal parenthesization, comparison charts, and DP tables in one application.
