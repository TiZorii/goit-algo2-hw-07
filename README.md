# Homework on "Cache Management Algorithms"

Welcome 🌞

Ready to apply cache management algorithms? Then let's get to work!

By completing the first task, you will learn to use an LRU cache to optimize
data processing in a program. This task will help you practically compare the
performance of a program with and without caching, assessing how caching can
significantly reduce query execution time in systems with large data volumes.

In the second task, you will implement different optimization methods for
computing Fibonacci numbers: using the `@lru_cache` decorator and using the
Splay Tree data structure. Through this task, you will compare two different
algorithms, evaluate their efficiency, and visually compare the results.

These tasks will help you understand the advantages and limitations of different
caching approaches and their impact on program performance, especially for large
input data.

Good luck! 😎

## Task 1. Optimizing Data Access Using LRU Cache

Implement a program to optimize processing requests to an array of numbers using
an LRU cache.

### Technical Requirements

1. Given an array of size N consisting of positive integers (1 ≤ N ≤ 100,000),
   process Q queries (1 ≤ Q ≤ 50,000) of the following types:

   - `Range(L, R)`: Find the sum of elements in the range from index L to R
     (inclusive).
   - `Update(index, value)`: Replace the value of an element in the array at the
     given index with a new value.

2. Implement four functions to work with the array:

   - `range_sum_no_cache(array, L, R)`: Computes the sum of array elements in
     the range from L to R without caching. Each query must be recalculated from
     scratch.
   - `update_no_cache(array, index, value)`: Updates the value of an array
     element at the specified index without caching.
   - `range_sum_with_cache(array, L, R)`: Computes the sum of elements in the
     range from L to R using an LRU cache. If the sum for this range has been
     computed before, it should be retrieved from the cache; otherwise, it is
     computed and added to the cache.
   - `update_with_cache(array, index, value)`: Updates the value of an array
     element at the specified index and removes all relevant values from the
     cache that have become outdated due to the change in the array.

3. To test the program, create an array of 100,000 elements filled with random
   numbers and generate 50,000 `Range` and `Update` queries in random order.

   Example list of queries:

   ```python
   [('Range', 46943, 91428), ('Range', 5528, 29889), ('Update', 77043, 78), ...]
   ```

4. Use an **LRU cache** of size **K = 1000** to store previously computed
   results for **Range queries**.  
   The cache should **automatically remove the least recently used** elements
   when it reaches its maximum size.

5. Compare the execution time of queries:
   - **Without caching**.
   - **With LRU caching**.
   - **Output the results** in terms of execution time for both approaches.

### **Acceptance Criteria**

📌 These acceptance criteria are mandatory for homework review by a mentor.  
If any criteria are not met, the mentor will return the homework for revision
without evaluation.  
If you need clarification 😉 or get stuck at any stage, contact your mentor on
**Slack**.

1. All functions (`range_sum_no_cache`, `update_no_cache`,
   `range_sum_with_cache`, `update_with_cache`) are **implemented and
   functional**.
2. The program **measures query execution time** with and without caching and
   outputs the results in a clear format.
3. Test results are **presented in an understandable format** to evaluate the
   efficiency of **LRU caching**.
4. The **code runs without errors** and meets the technical requirements.

### **Example Terminal Output**

```bash
Execution time without caching: 3.11 seconds
Execution time with LRU cache: 0.02 seconds

```

# Task 2: Comparing Fibonacci Computation Performance Using LRU Cache and Splay Tree

## Requirements

Implement a program to compute Fibonacci numbers using two approaches:

- **LRU Caching** (`@lru_cache` decorator).
- **Splay Tree** for storing previously computed values.

Conduct a **comparative analysis** of their efficiency by measuring the
**average execution time** for each approach.
