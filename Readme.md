# Vector-Matrix DSL Compiler

A statically-typed Domain Specific Language (DSL) compiler and interpreter optimized for linear algebra operations. This project implements a full 4-stage compiler pipeline - from lexical analysis to runtime evaluation - capable of handling vector/matrix math, complex control flow, and user-defined functions.

## 🚀 Technical Highlights
* **Recursive Descent Parser:** Implements an **LL(k)** parser generated from a custom **BNF Grammar** to resolve operator precedence and "dangling else" ambiguity.
* **AST Optimization:** Utilizes **JJTree** and the **Visitor Pattern** to construct an Abstract Syntax Tree (AST), discarding syntactic sugar to optimize runtime performance.
* **Custom Type System:** Engineered to natively support and evaluate complex data types (Vectors `[]`, Matrices) alongside standard Integers and Booleans.
* **Automated CI/CD:** Features a custom Bash-based regression testing suite that validates tokenization and logic against expected outputs.

## 🛠 Tech Stack
* **Core Language:** Java
* **Compiler-Compiler:** JavaCC
* **Tree Builder:** JJTree
* **Scripting:** Bash (Test Automation)

## 🧩 Compiler Architecture

The system follows a modular pipeline design:

### 1. Lexical Analysis (Scanner)
* **Process:** Tokenizes raw source code using Regex-based rules.
* **Features:** Handles keyword recognition (`IF`, `WHILE`, `VAR`), literal parsing, and comment filtering.

### 2. Syntax Analysis (Parser)
* **Process:** Validates token streams against strict grammar rules.
* **Key Logic:** Enforces mathematical operator precedence and manages symbol tables for variable declarations.

### 3. Semantic Analysis (AST)
* **Process:** Constructs a hierarchical tree representation of the code.
* **Tech:** Uses **JJTree** to generate optimized node classes for efficient traversal.

### 4. Runtime Evaluation (Interpreter)
* **Process:** Traverses the AST using the **Visitor Pattern**.
* **Capabilities:** Executes logic, manages memory state, and performs arithmetic operations on vectors and scalars.

## 🧪 Testing & Validation
The project includes a comprehensive test suite driven by the `runtests` shell script.

* **Unit Tests:** Verify individual grammar productions (e.g., boolean logic, arithmetic).
* **Integration Tests:** Execute complex algorithms (e.g., recursive factorials, matrix multiplication).

## 💻 Usage

**Build the Compiler**
```bash
make
```
**Build the Compiler**
```bash
./runtests
