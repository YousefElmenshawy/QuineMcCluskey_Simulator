# 🔍 Quine-McCluskey Logic Minimization Simulator

**Team Members:**

* Hassan Ashraf
* Yousef Elmenshawi
* Ahmed Soliman

---

## 📘 Overview

This project implements the **Quine-McCluskey algorithm**, a tabular method used to minimize Boolean expressions. It is especially useful in digital design, where reducing the complexity of logic circuits leads to more efficient hardware.

The tool:

* Simplifies Boolean expressions.
* Computes prime and essential prime implicants.
* Outputs minimal logic expressions.
* Generates equivalent **Verilog code**.

---

## ✨ Features

* 🧠 **Boolean Expression Input**: Supports minterms, maxterms, and don’t-care conditions.
* 🔗 **Prime Implicant Generation**: Lists all prime implicants.
* ⭐ **Essential Prime Implicants**: Identifies implicants that uniquely cover minterms.
* 🧮 **Minimal Cover Generation**: Uses a greedy approach to select minimal implicants.
* 💻 **Verilog Code Generation**: Exports the minimized expression to Verilog.
* ✅ **Comprehensive Testing**: Includes 10 edge-case-rich test cases.

---

## 🧑‍💻 How to Use

### 🔧 Compile the Program

Use a C++11-compatible compiler:

```bash
g++ -std=c++11 -o qmc main.cpp QuineMcCluskey.cpp Implicant.cpp Term.cpp
```

Alternatively, use an IDE like CLion or Visual Studio to build the project.

### 🚀 Run the Program

After compilation, run the executable:

```bash
./qmc
```

You will be prompted to enter the name of a test case file located in the `testcases/` folder.

### 📤 Output

For each test case, the program will display:

* ✅ All **prime implicants**
* ⭐ **Essential prime implicants**
* 🧾 The **minimized Boolean expression**
* 💻 The corresponding **Verilog code**

### 📂 Input Format

Each input file should follow this structure:

```
Line 1: An integer N (1 ≤ N ≤ 20) — Number of variables

Line 2: A comma-separated list of minterms or maxterms
    - Prefix with `m:` for minterms (e.g., m:0,1,3,5)
    - Prefix with `M:` for maxterms (e.g., M:2,4,6)

Line 3: A comma-separated list of don't-care terms
    - Prefix with `d:` (e.g., d:7,8,9)
```

If any line contains only `m:`, `M:`, or `d:` with no values, it means that there are no minterms, maxterms, or don’t-care terms respectively.

#### 🧾 Example Input

```
4
m:1,3,7,8,9
d:2,5
```

This represents a Boolean function with 4 variables, minterms 1, 3, 7, 8, 9, and don’t-care terms 2 and 5.

### 🧪 Test Cases

The `testcases/` directory includes 10 diverse examples for testing:

| Test Case   | Description                              | Input Snippet           |
| ----------- | ---------------------------------------- | ----------------------- |
| **Test 1**  | Function with multiple minimal solutions | `3\nm:1,3,7`            |
| **Test 2**  | Only don’t-care terms                    | `4\nd:0,1,2,3,4`        |
| **Test 3**  | One variable, one minterm                | `1\nm:1`                |
| **Test 4**  | No essential prime implicants            | `4\nm:1,3,5,7`          |
| **Test 5**  | No minterms or don’t-cares               | `3\nm:\nd:`             |
| **Test 6**  | Defined by maxterms                      | `3\nM:0,2,4,6`          |
| **Test 7**  | Single maxterm                           | `2\nM:3`                |
| **Test 8**  | Overlapping minterms & don’t-cares       | `4\nm:1,2,3,4\nd:3,4,5` |
| **Test 9**  | All minterms (outputs 1)                 | `3\nm:0,1,2,3,4,5,6,7`  |
| **Test 10** | Edge case with 20 variables              | `20\nm:1048575`         |

Each test case is saved in its own file for ease of use and reproducibility.

---

## 📬 Contact & Contributions

If you have any questions or suggestions, feel free to reach out at **[yousefelmenshawi@aucegypt.edu](mailto:yousefelmenshawi@aucegypt.edu)**.

🎉 **Contributions are welcome!** If you'd like to improve or extend the project, feel free to open a pull request.
