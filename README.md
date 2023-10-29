# ⚫ Dynamic Programming in Tech Interviews 2024: 8 Must-Know Questions & Answers

**Dynamic Programming**, a method for solving **complex problems** by breaking them down into simpler overlapping **subproblems**. It is a frequent topic in advanced coding interviews.

Check out our carefully selected list of **basic** and **advanced** Dynamic Programming questions and answers to be well-prepared for your tech interviews in 2024.

![Dynamic Programming Decorative Image](https://storage.googleapis.com/dev-stack-app.appspot.com/blogImg/dynamicProgramming.png?GoogleAccessId=firebase-adminsdk-bgeaf%40dev-stack-app.iam.gserviceaccount.com&Expires=1698598947&Signature=QJa%2Fw4ZvwRlF8Hh1h9NGKoQIcd8puQeCMBtpm3IPx%2FfN5gQPGPUrgSanph2DCLuhfi%2FHlAvKvqot3BH68DexVaNIdRFpfIAwN4x5MSv9mDImjrcYVPtKclzAI1hBT%2FntSKymK3UX%2FrbZdpzmVTLO88OpBNagEGfmDVmBb4fJUEKnK7hnaMLS6m%2FfBgy6v22JG9vmJ4BlqxcxSA%2FHkVo86HcLuJkXFd1horeqNmDpBOq%2FoD7XR3cvq018YAk4OYRqvu0OkFlOAmsEdryDT7poMUACa2Qho1PtJHZ3FAR0XsQulyAkYCap9RfeYckG%2BOFS%2BtTlkIcTmAf9PqdnCeqbwA%3D%3D)

👉🏼 You can also find all answers here: [Devinterview.io - Dynamic Programming](https://devinterview.io/data/dynamicProgramming-interview-questions)

---

## 🔹 1. What is _Dynamic Programming_?

### Answer

**Dynamic Programming** (DP) optimizes algorithms by solving **recursive** problems more efficiently. It divides a complex problem into overlapping **subproblems** and caches their solutions to avoid redundancy.

### Benefits of Dynamic Programming

- **Efficiency**: DP can drastically reduce time complexity.
- **Memoization**: By storing solutions, computation is expedited.
- **Versatility**: It's applicable in various scenarios like resource allocation and sequence alignment.


### Fundamental Concepts

- **Subproblems**:
   - Description: DP breaks problems into manageable tasks.
   - Example: To compute $Fib(5)$, one requires $Fib(4)$ and $Fib(3)$, which can be further decomposed.

- **Overlapping Subproblems**:
   - Description: Some tasks are computed multiple times.
   - Example: Both $Fib(4)$ and $Fib(3)$ utilize the result of $Fib(3)$.

- **Optimal Substructure**:
   - Description: The optimal solution of a problem is constructed from the optimal solutions of its subproblems.
   - Example: The longest common subsequence between two strings derives from the subsequence of their prefixes.


### Dynamic Programming Approaches

- **Top-Down (Memoization)**: Tackle the main problem and break it down as required. Use a memoization table to check before solving subproblems.

- **Bottom-Up (Tabulation)**: Begin with the smallest subproblems and build up solutions.

### Complexity Analysis

- **Time Complexity**: Generally $O(n)$ for problems having $n$ subproblems with each being $O(1)$.
- **Space Complexity**: Both methods tend to require $O(n)$ space.

### Code Example: Top-Down & Bottom-Up Approaches

Here is the Python code:

```python
# Top-Down (Memoization)
def fibonacci_top_down(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fibonacci_top_down(n-1, memo) + fibonacci_top_down(n-2, memo)
    return memo[n]

# Bottom-Up (Tabulation)
def fibonacci_bottom_up(n):
    if n <= 1:
        return n
    fib = [0] * (n+1)
    fib[1] = 1
    for i in range(2, n+1):
        fib[i] = fib[i-1] + fib[i-2]
    return fib[n]
```

---

## 🔹 2. How to choose between _Top-Down_ vs _Bottom-Up_ approaches?

### Answer

When it comes to Dynamic Programming, choosing between the **Top-Down** (Memoization) and **Bottom-Up** (Tabulation) approaches can significantly impact both the performance and complexity of your algorithm.

### Key Considerations

1. **Efficiency**: Both methods usually offer similar time complexities, but the bottom-up approach can be faster in practice due to the lack of recursive function call overhead.
  
2. **Memory Use**: The bottom-up method often requires less memory because it eliminates the need for recursive stack space.

3. **Calculations**: Top-down is advantageous when not all sub-problems need to be solved, as it caches solutions for repeated sub-problems. Bottom-up computes all sub-problems, which may result in extra work.
  
4. **Ease of Coding**: Top-down algorithms are often more straightforward to implement and understand, as they closely mirror the problem description. Bottom-up algorithms can be trickier, especially when sub-problem dependencies are complex.

5. **Order of Computation**: Bottom-up is beneficial when there's a clear, natural order in which to solve sub-problems.

### Real-world Examples

#### 0-1 Knapsack Problem

- **Top-Down**: Efficient when few items fit in the knapsack; solves only necessary sub-problems.
- **Bottom-Up**: Generates a full $O(nW)$ table, potentially wasting time on irrelevant sub-problems.

#### Longest Increasing Path in a Matrix

- **Top-Down**: Starts at any point and only explores increasing paths, using memoization to avoid redundancy.
- **Bottom-Up**: Requires $O(nm \log(nm))$ sorting time before DP steps, potentially adding unnecessary complexity.

### Code Example: Top-Down & Bottom-Up Approaches

Here is the Python code:

```python
# Top-Down (Memoization)
def fibonacci_top_down(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fibonacci_top_down(n-1, memo) + fibonacci_top_down(n-2, memo)
    return memo[n]

# Bottom-Up (Tabulation)
def fibonacci_bottom_up(n):
    if n <= 1:
        return n
    fib = [0] * (n+1)
    fib[1] = 1
    for i in range(2, n+1):
        fib[i] = fib[i-1] + fib[i-2]
    return fib[n]
```

---

## 🔹 3. How _Dynamic Programming_ is different from _Recursion_ and _Memoization_?

### Answer

**Dynamic Programming** (DP), **Recursion**, and **Memoization** are techniques for solving problems that can be divided into smaller, overlapping sub-problems. While they share this commonality, they each offer unique advantages and limitations. 

### Key Distinctions

1. **Efficiency**: DP typically leads to polynomial-time algorithms, whereas Recursion and Memoization can result in higher time complexities.
  
2. **Problem-Solving Direction**: DP builds solutions from the ground up, focusing on smaller sub-problems first. In contrast, Recursion and Memoization usually adopt a top-down approach.

3. **Implementation Style**: DP and Memoization can be implemented either iteratively or recursively, while Recursion is, by definition, a recursive technique.

4. **Sub-Problem Coverage**: DP aims to solve all relevant sub-problems, whereas Memoization and Recursion solve sub-problems on an as-needed basis.

5. **Memory Use**: DP often requires less memory than Memoization, as it doesn't store every state reached through recursive calls.

---

## 🔹 4. What is the difference between _Divide and Conquer_ and _Dynamic Programming_ algorithms?

### Answer

Both **Divide and Conquer** and **Dynamic Programming** are algorithmic paradigms that break problems down into smaller, more manageable sub-problems.

While they share similarities such as the use of **recursion** and the need for an **optimal substructure**, they also differ in key ways.

### Common Features

- **Recursion**: Both paradigms employ recursive techniques.
- **Optimal Substructure**: Solutions to the overall problem are constructed from optimal solutions of its sub-problems.
- **Complexity**: Time and space complexities help evaluate algorithmic efficiency.

### Key Distinctions

- **Sub-Problems Dependency**: 
   - Divide and Conquer: Sub-problems are independent.
   - Dynamic Programming: Sub-problems often overlap and are dependent.

- **Intermediate Results**: 
   - Divide and Conquer: No storage of intermediate outcomes.
   - Dynamic Programming: Uses memoization or tabulation to store intermediate results, reducing redundant calculations.

### Code Example: Fibonacci Sequence

Here is the Python code:

```python
# Divide and Conquer for Fibonacci
def fibonacci_divide_conquer(n):
    if n <= 1:
        return n
    return fibonacci_divide_conquer(n-1) + fibonacci_divide_conquer(n-2)

# Dynamic Programming for Fibonacci with memoization
def fibonacci_memoization(n, memo={}):
    if n <= 1:
        return n
    if n not in memo:
        memo[n] = fibonacci_memoization(n-1, memo) + fibonacci_memoization(n-2, memo)
    return memo[n]
```

In this example, `fibonacci_divide_conquer` uses Divide and Conquer without any storage mechanism. `fibonacci_memoization` leverages Dynamic Programming and memoizes results to avoid redundant calculations.

---

---

## 🔹 5. Compare _Greedy_ vs _Divide & Conquer_ vs _Dynamic Programming_ algorithms.

### Answer

👉🏼 Check out all 8 answers here: [Devinterview.io - Dynamic Programming](https://devinterview.io/data/dynamicProgramming-interview-questions)

---

## 🔹 6. Is _Dijkstra's_ algorithm a _Greedy_ or _Dynamic Programming_ algorithm?

### Answer

👉🏼 Check out all 8 answers here: [Devinterview.io - Dynamic Programming](https://devinterview.io/data/dynamicProgramming-interview-questions)

---

## 🔹 7. Calculate the N-th value of the _Fibonacci Number_ recursively.

### Answer

👉🏼 Check out all 8 answers here: [Devinterview.io - Dynamic Programming](https://devinterview.io/data/dynamicProgramming-interview-questions)

---

## 🔹 8. Find length of the _Longest Increasing Subsequence_ (LIS) in the array, using _DP_.

### Answer

👉🏼 Check out all 8 answers here: [Devinterview.io - Dynamic Programming](https://devinterview.io/data/dynamicProgramming-interview-questions)
