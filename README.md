#  Operating Systems — Multithreading Tasks

<p align="center">

**Implementation of Classic OS Problems using Python Multithreading**

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge\&logo=python)
![Operating Systems](https://img.shields.io/badge/Subject-Operating%20Systems-purple?style=for-the-badge)
![Multithreading](https://img.shields.io/badge/Concept-Multithreading-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

</p>

---

## About

This project implements two **Operating Systems multithreading problems** using Python.

The project demonstrates **concurrent execution, shared resources, synchronization, locks, and condition variables**.

### Tasks

1. 🏭 **Producer–Consumer Problem**
2. 🧮 **100 × 100 Matrix Multiplication using Multithreading**

The matrix multiplication task also includes an **interactive HTML cloud animation** to visualize how threads perform individual multiplication operations.

---

##  Table of Contents

* [Producer–Consumer Problem](#-1-producerconsumer-problem)
* [Matrix Multiplication](#-2-matrix-multiplication)
* [Concepts Demonstrated](#-concepts-demonstrated)
* [Technologies Used](#️-technologies-used)
* [Project Structure](#-project-structure)
* [How to Run](#️-how-to-run)
* [Screenshots](#-screenshots)
* [Conclusion](#-conclusion)

---

#  1. Producer–Consumer Problem

## Problem Statement

Implement the Producer–Consumer problem using threads in Python with a **shared bounded buffer**.

The program contains:

* **2 Producer threads**
* **2 Consumer threads**
* A shared buffer with capacity **4**
* Synchronization using a **Condition Variable**

### How It Works

```text
Producer
   │
   ▼
┌───────────────┐
│ Shared Buffer │
│ Capacity = 4  │
└───────┬───────┘
        │
        ▼
    Consumer
```

* Producers generate random numbers and insert them into the buffer.
* Consumers remove and process the numbers.
* If the buffer is **full**, producers wait.
* If the buffer is **empty**, consumers wait.
* `notify_all()` wakes waiting threads when the buffer state changes.
* A `STOP` value is used to terminate consumers after production is complete.

### Synchronization Used

```python
threading.Condition()
```

This prevents unsafe access to the shared buffer and coordinates producer and consumer threads.

---

#  2. Matrix Multiplication

## Problem Statement

Multiply two **100 × 100 matrices** using multithreading, where each individual multiplication operation is performed by a separate thread.

For each result element:

```text
C[i][j] = Σ A[i][k] × B[k][j]
```

### Thread Approach

Each thread calculates one partial product:

```text
A[i][k] × B[k][j]
        │
        ▼
     C[i][j]
```

For a 100 × 100 matrix:

```text
100 × 100 × 100
= 1,000,000 threads
```

### Synchronization

Locks are used while updating the shared result matrix:

```python
with row_guard[r]:
    answer[r][c] += part
```

This helps prevent incorrect updates caused by concurrent access.

### Result Verification

The final matrix is verified using a normal single-threaded matrix multiplication method.

```text
Multithreaded Result
        │
        ▼
    Compare
        │
        ▼
Standard Result
        │
        ▼
     Correct ✓
```

---

# ☁️ HTML Cloud Animation

The project includes an interactive HTML animation for the matrix multiplication concept.

The animation uses a **4 × 4 matrix** for visualization.

Each cloud represents a simulated thread:

```text
☁️  A[i][k] × B[k][j]
          │
          ▼
       C[i][j]
```

It demonstrates:

* Thread creation
* Parallel execution
* Waiting for locked cells
* Updating result cells
* Completion of threads

### Controls

**Start · Pause · Resume · Reset · Speed**

---

#  Concepts Demonstrated

| Concept              | Application                     |
| -------------------- | ------------------------------- |
| Multithreading       | Multiple concurrent threads     |
| Synchronization      | Safe access to shared resources |
| Condition Variables  | Producer–Consumer               |
| Locks                | Matrix result updates           |
| Shared Resources     | Buffer and result matrix        |
| Race Conditions      | Prevented using synchronization |
| `start()` / `join()` | Thread management               |

---

# 🛠️ Technologies Used

* 🐍 Python
* 🧵 Python `threading`
* 🌐 HTML
* 🎨 CSS
* ⚡ JavaScript

---

#  How to Run

### Producer–Consumer

```bash
python producer_consumer.py
```

### Matrix Multiplication

```bash
python matrix_multiplication.py
```

### Animation

Open:

```text
matrix_animation.html
```

in a web browser and click **Start**.

---

# Screenshots

### Producer–Consumer Output

![Producer Consumer](<img width="931" height="847" alt="Screenshot 2026-09-11 224924" src="https://github.com/user-attachments/assets/7a5f7bcb-87cb-40ff-86ec-50477c5837cd" />
)

### Matrix Multiplication Output

![Matrix Output](<img width="1293" height="938" alt="Screenshot 2026-09-11 230147" src="https://github.com/user-attachments/assets/981ebadb-dcbf-402b-8756-475b7cc8e67c" />
)

### HTML Cloud Animation

![Matrix Animation](<img width="1276" height="896" alt="Screenshot 2026-09-11 230204" src="https://github.com/user-attachments/assets/73617d5f-9118-4b4f-ae24-68e3e1e4c070" />)

---

#  Learning Outcomes

Through this project, the following concepts were practically demonstrated:

* Understanding threads and concurrency
* Managing shared resources
* Applying synchronization techniques
* Using condition variables and locks
* Handling race conditions
* Understanding thread creation and joining
* Visualizing multithreaded execution

---

#  Conclusion

This project provides a practical implementation of two classic Operating Systems problems.

The **Producer–Consumer problem** demonstrates synchronization using a bounded buffer and condition variables, while **Matrix Multiplication** demonstrates multithreading and locks for safely updating shared results.

The HTML animation further provides a visual understanding of how individual threads participate in matrix multiplication.

---

<p align="center">

### 🧵 Operating Systems • Multithreading • Synchronization

**Academic Practical Project**

</p>

