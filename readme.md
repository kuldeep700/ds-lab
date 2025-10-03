# Data Structures & Algorithms — Lab

Welcome to the ds-lab repository: a compact collection of classic data structures and sorting/search algorithms implemented for learning, practice, and small experiments. This repo collects clear, easy-to-follow implementations intended for students and developers who want to study algorithm logic in plain code.

Contents in this repository
- `binary search/` — Binary Search implementation and small test harness.
- `linear search/` — Linear (sequential) search examples.
- `insertion sort/` — Insertion Sort implementation and walkthrough.
- `merge sort/` — Merge Sort implementation with notes and examples.
- `quick sort/` — Quick Sort implementation and pivot strategies.
- `heap sort/` — Heap Sort implementation and heap helpers.
- `circular queue/` — Circular queue (ring buffer) implementation with enqueue/dequeue.
- `bst create in traversing order/` — Binary Search Tree creation and traversal utilities.
- `readme.md` — This file.

Why this repo exists
--------------------

This collection is a study and teaching aid. The implementations emphasize readability over micro-optimizations, include helpful comments, and are small enough to fit inside a single file per algorithm for easy reading. Use it to:

- Learn algorithm mechanics and invariants.
- Compare algorithmic complexity and behavior on sample inputs.
- Modify code to experiment with variations (different pivots for Quick Sort, iterative vs recursive traversals, etc.).

Quick start — how to run
------------------------

This repository contains simple programs (one per folder). To run a particular implementation, open PowerShell, navigate to the repository root (`e:\ds-lab`) and run the appropriate file for the language used inside each folder (most are plain scripts). Example PowerShell commands to run common kinds of files:

```
# Change to repo root
cd e:\ds-lab

# If a folder contains a Python script (example):
python .\"merge sort"\merge_sort.py

# If a folder contains a C/C++ file, build then run (example):
gcc .\"quick sort"\quick_sort.c -o quick_sort.exe; .\quick_sort.exe

# If a folder contains Java, compile and run (example):
javac .\"binary search"\BinarySearch.java; java -cp . binarysearch.BinarySearch

# If files are plain pseudo-code or text, open them in your editor.
```

Note: this README assumes you have the typical language toolchains installed (Python, GCC/Clang, Java JDK) and available on your PATH. If you want, I can add small runner scripts or a Makefile to standardize running across platforms.

Algorithms included (summary)
-----------------------------

Below are short descriptions and complexity analyses for each algorithm in the repo. Use these as a study guide.

1) Linear Search (`linear search/`)
- Description: Scan each element from left to right until the target is found.
- Use when: data is unsorted or very small.
- Time: Best O(1), Average O(n/2) -> O(n), Worst O(n)
- Space: O(1)

2) Binary Search (`binary search/`)
- Description: Search a sorted array by repeatedly dividing the search interval in half.
- Use when: array is sorted and random access is available.
- Time: Best O(1), Average/Worst O(log n)
- Space: O(1) (iterative), O(log n) (recursive stack)

3) Insertion Sort (`insertion sort/`)
- Description: Build the sorted array one element at a time by inserting each new element into its correct position.
- Use when: nearly-sorted arrays or small arrays.
- Time: Best O(n), Average/Worst O(n^2)
- Space: O(1)

4) Merge Sort (`merge sort/`)
- Description: Divide array into halves, sort halves recursively, merge sorted halves.
- Use when: stable sort and guaranteed O(n log n) performance is needed.
- Time: O(n log n) for all cases
- Space: O(n) extra for merging (can be O(1) with complex in-place variants)

5) Quick Sort (`quick sort/`)
- Description: Partition array around a pivot, recursively sort partitions.
- Use when: average-case fast in-place sort; tune pivot selection to avoid worst-case.
- Time: Average O(n log n), Worst O(n^2) (bad pivot)
- Space: O(log n) average recursion stack (O(n) worst)

6) Heap Sort (`heap sort/`)
- Description: Build a binary heap from the array and repeatedly extract max (or min) to produce sorted order.
- Use when: guaranteed O(n log n) in-place sort without recursion is desired.
- Time: O(n log n) all cases
- Space: O(1) (in-place)

7) Circular Queue (`circular queue/`)
- Description: Fixed-size ring buffer providing FIFO operations with wrap-around.
- Use when: implementing queues with bounded capacity (e.g., producer/consumer fixed buffer).
- Operations: enqueue, dequeue, peek, isEmpty, isFull
- Space: O(capacity)

8) Binary Search Tree utilities (`bst create in traversing order/`)
- Description: Helpers to create a BST and traverse it (preorder/inorder/postorder, level order).
- Use when: studying tree construction and traversal algorithms.

File / naming conventions
-----------------------

- Each folder contains a single file or a few small files. Filenames aim to be descriptive (e.g., `merge_sort.py`, `quick_sort.c`).
- Where helpful, small test input or example files are included alongside the implementation.

Example: run and compare sorts (manual)
--------------------------------------

1. Choose array sizes and generate test arrays (small, medium, large). You can write a short script to generate random integers. Example Python quick test:

```python
import random

def gen(n, seed=1):
	random.seed(seed)
	return [random.randint(0, 1000000) for _ in range(n)]

arr = gen(1000)
print(arr[:20])
```

2. Run the same array through `insertion sort`, `merge sort`, `quick sort`, `heap sort` implementations and compare time. Measure with time.time() or time.perf_counter() in Python, or use high-resolution timers in C/Java.

Best practices while exploring
-----------------------------

- Start with small arrays and use prints or assertions to validate correctness.
- Add unit tests for each operation (enqueue/dequeue pairs for the queue, BST insert/traverse invariants).
- When experimenting with Quick Sort pivot choices, measure the worst-case patterns (sorted input) and add randomized pivot selection.
- For large inputs, ensure your environment has enough stack or convert deep-recursive implementations to iterative variants.

Contribution guidelines
-----------------------

Contributions are welcome. A few simple rules to keep the repo useful for learners:

1. Keep implementations clear and documented. Small helper comments that explain invariants are very helpful.
2. Add a small README inside any new folder you create explaining how to run that implementation.
3. Include tests or example inputs demonstrating correctness.
4. Use meaningful commit messages and open a PR against the `readme` branch (or the default branch you prefer).

Suggested development workflow

1. Fork or branch from `readme`.
2. Implement or update code in a new folder or existing folder.
3. Add test input and a brief explanation file if behavior is non-obvious.
4. Run your tests and verify they pass locally.
5. Open a PR with the change and a short description of what you added or fixed.

License
-------

This repository contains example educational code. If you want to add an explicit license, create a `LICENSE` file (MIT is often a good choice for learning code). If you prefer, I can add an MIT license file for you.

References & further reading
---------------------------

- Cormen, Leiserson, Rivest, and Stein — Introduction to Algorithms (CLRS)
- Sedgewick & Wayne — Algorithms
- Wikipedia pages for each algorithm for variants and proofs
- Online judge problems (e.g., LeetCode, HackerRank) to practice patterns covered here

Acknowledgements
----------------

This repo is a study collection assembled incrementally. If you use or adapt these files, a short attribution in your project readme is appreciated.

Contact / questions
-------------------

If you'd like, tell me which language(s) you prefer and I can:

- Add runnable scripts that execute all algorithms and compare performance.
- Add unit tests for each implementation in a chosen test framework (pytest/unit tests/JUnit etc.).
- Add a `LICENSE` file and small CI workflow to run tests automatically.

Enjoy exploring algorithms!

---


