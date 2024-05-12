# 351-final

# All Algorithm Information

| **Name**       | **Brief overview** | **Worst Case** | **Best Case** | **Average Case** | **Recurrence Relation** | **Stable?** |
|----------------|---------------------|----------------|---------------|------------------|-------------------------|-------------|
| **Bubble Sort** | Iterates through a list of length n, starting at the beginning and swapping elements if the current is bigger. After each step, the rightmost side becomes sorted. | O(n²) | O(n²) | O(n²) | - | Yes |
| **Insertion Sort** | Starting with a list A of length n, pick up A[1]. Look left. If anything left is larger, slide it to the right, then insert. Continue to iterate through the list until sorted. | O(n²) | O(n) | O(n²) | - | Yes |
| **Selection Sort** | Look through a list A, find the index of the smallest item. Swap A[that index] with A[0]. Now A[0] is correctly placed. Then look through the rest of the list for the index of the smallest item. Swap with A[i]. | O(n²) | O(n²) | O(n²) | - | No |
| **Merge Sort** | Divide list by 2, repeating until the sublists are of size 2. Then, compare & sort the elements in each list. Merge the sublists with ones next to it and compare and sort. Repeat until the list is of size n. | O(n log n) | O(n log n) | O(n log n) | T(n) = 2T(n/2) + Θ(n) | Yes |
| **Quick Sort** | Pick a key and rearrange so all values left of the key are smaller & all values right of key are larger. Repeat until no more smaller lists. | O(n²) | O(n log n) | O(n log n) | Worst case: T(n) = T(k) + T(n-k) + Θ(n), Best Case: T(n) = 2T (n/2) + Θ(n) | No |
| **Heap Sort** | -Maxheapify -convert to maxheap | O(n log n) | O(n) | O(n log n) | - | No |
| **Radix Sort** | Underlying sort must be stable to work at all. Run the underlying sort on the list based only on the rightmost digit. Repeat this process on the next-rightmost digit until you have sorted the list on the leftmost digit. | Θ(d(n +(b - 1))) | Θ(d(n +(b - 1))) | Θ(d(n +(b - 1))) | - | Yes |
| **Counting Sort** | Create a list from 0 to the max key, populated with how many keys equal the index. Make a cumulative version of that list. Using this position list, iterate the input list backwards, placing each element in the appropriate position by key and then decrementing the position. | O(n+k) | O(n+k) | O(n+k) | - | Yes |
| **Bucket Sort** | # buckets = floor(max(A)/n) + 1. Bucket sort will be stable as long as the underlying sort is also stable. | O(n²) | O(n) | O(n) | - | Yes-ish |
| **Binary Search** | The input list must be sorted. Check the median of the list. Either it is the target, or search the appropriate half of the list. | O(log n) | O(1) | O(log n) | - | N/A |
| **Karatsuba** | A more efficient way of multiplication. AB = (10^n)A1B1 + (10^(n/2))[(A1 + A0)(B1 + B0) - A0B0 - A1B1] + A0B0 | - | - | - | T(n) = 3T(n/2) + Θ(n) | N/A |
| **BFS** | 1) Add the starting node to a queue. 2) Pop from the queue. 3) Add all the popped element’s new neighbors to the queue. 4) Repeat 2-4 until you’ve found the node you wanted. | O(V²) for adjacency matrix, O(V + E) for adjacency list | - | - | - | N/A |
| **DFS** | 1) Add the starting node to a stack + visited set. 2) Pop from the stack. 3) Add all the popped element’s new neighbors to the stack. 4) Repeat 2-4 until you’ve found the node you wanted. | O(V² + E) for adjacency matrix, O(V + E) for adjacency list | - | - | - | N/A |
| **Dijkstra’s** | Single-source shortest path algorithm. | Θ(V³) for adjacency matrix, Θ(V² + E) for adjacency list, Θ(E log V) for min heap | - | - | - | N/A |
| **Floyd’s** | Finds shortest paths for a weighted (pos or neg) and directed graph using an adjacency matrix. | O(V³) | - | - | - | N/A |
| **Kruskal’s** | Creates a minimum spanning tree. Starts at the edge with the smallest value, and uses the next smallest one until all nodes are reached. | O(E log E) | - | - | - | N/A |
| **Prim’s** | Creates a minimum spanning tree. Starts at the edge with the smallest value and uses the smallest edge connected to a node that it has reached as the next edge to visit. | O(E log V) with min heap, O(V²) with adjacency matrix | - | - | - | N/A |
| **Huffman** | A way to express something (a string) in the minimum number of bits. 1) Create nodes with each value. 2) Combine the two nodes with the lowest frequency and merge them where the parents are the total of the children. 3) Repeat until the top node is the total count of all nodes. | O(n log n) | O(n log n) | O(n log n) | - | N/A |
| **Minimax** | Algorithm for decision making in game theory. Evaluates the best move by minimizing the possible loss for a worst-case scenario. | - | - | - | - | N/A |


## Detailed info on each algorithm 
### Bubble Sort
- **Detailed Complexity Analysis**: Bubble sort makes O(n) passes through the list. Each pass makes O(n) comparisons and potentially swaps, leading to O(n²) comparisons and swaps in the worst case.
- **Practical Use**: Often used for educational purposes or for very small datasets. It's simple to understand and implement.

### Insertion Sort
- **Detailed Complexity Analysis**: In the worst case, each insertion requires shifting all previously sorted elements, resulting in O(n²) time complexity. In the best case (already sorted list), each insertion requires no shifting, resulting in O(n) time complexity.
- **Practical Use**: Efficient for small or nearly sorted datasets. It's also used in hybrid algorithms like Timsort, which combines insertion sort with merge sort for efficiency.

### Selection Sort
- **Detailed Complexity Analysis**: Selection sort performs O(n²) comparisons and O(n) swaps regardless of the initial order of the list. This makes it less efficient than insertion sort for nearly sorted lists.
- **Practical Use**: Rarely used in practice due to its inefficiency, but it is simple to implement and understand.

### Merge Sort
- **Detailed Complexity Analysis**: Merge sort consistently divides the list in half, resulting in a logarithmic number of levels. Each level requires a linear amount of work to merge, resulting in O(n log n) time complexity.
- **Practical Use**: Widely used due to its predictable O(n log n) time complexity and stability. It is the basis for many modern sorting algorithms, including Timsort.

### Quick Sort
- **Detailed Complexity Analysis**: The efficiency of quick sort heavily depends on the choice of the pivot. Randomized pivot selection or the median-of-three method can help avoid the worst-case scenario.
- **Practical Use**: Commonly used due to its average-case efficiency and in-place sorting. It's often the default sorting algorithm in many programming libraries (e.g., C's qsort, Python's sorted).

### Heap Sort
- **Detailed Complexity Analysis**: Building a max heap from an unsorted list requires O(n) time, and each of the n removals from the heap requires O(log n) time, resulting in O(n log n) overall.
- **Practical Use**: Useful when a stable sort is not required and in-place sorting is needed. It has consistent O(n log n) performance but is often slower than quick sort in practice due to higher constant factors.

### Radix Sort
- **Detailed Complexity Analysis**: Radix sort processes each digit in the numbers. If there are d digits and n numbers, and counting sort (or another stable sort) is used on each digit, the overall complexity is O(d(n + b)).
- **Practical Use**: Efficient for sorting large sets of numbers where the number of digits (d) is not significantly larger than the number of items (n).

### Counting Sort
- **Detailed Complexity Analysis**: Counting sort's time complexity is O(n + k), where n is the number of elements and k is the range of the input. This makes it efficient for small ranges but impractical for large ranges.
- **Practical Use**: Suitable for datasets where the range of input values is not significantly larger than the number of items.

### Bucket Sort
- **Detailed Complexity Analysis**: Bucket sort's performance depends on the distribution of elements. If elements are uniformly distributed, each bucket will have a small number of elements, leading to O(n) time complexity.
- **Practical Use**: Effective for sorting floating-point numbers or uniformly distributed data. The choice of bucket size and underlying sort is crucial for efficiency.

### Binary Search
- **Detailed Complexity Analysis**: Binary search divides the search interval in half with each step, leading to O(log n) time complexity.
- **Practical Use**: Ideal for searching in sorted arrays. It is not a sorting algorithm but a searching algorithm.

### Karatsuba
- **Detailed Complexity Analysis**: Karatsuba's divide-and-conquer approach reduces the multiplication of two n-digit numbers from O(n²) to O(n^log₃ 2) ≈ O(n^1.585).
- **Practical Use**: Used in high-performance computing for multiplying large integers.

### BFS and DFS
- **BFS Detailed Analysis**: BFS explores all nodes at the present depth before moving to the next level, making it useful for finding the shortest path in unweighted graphs.
- **DFS Detailed Analysis**: DFS explores as far as possible along each branch before backtracking, making it useful for pathfinding and topological sorting in directed acyclic graphs (DAGs).

### Dijkstra’s Algorithm
- **Detailed Complexity Analysis**: Dijkstra’s algorithm uses a priority queue to efficiently find the shortest path from the source vertex to all other vertices. The complexity depends on the data structure used for the priority queue.
- **Practical Use**: Widely used in routing and navigation systems.

### Floyd’s Algorithm
- **Detailed Complexity Analysis**: Floyd’s algorithm uses a dynamic programming approach with three nested loops, resulting in O(V³) time complexity.
- **Practical Use**: Suitable for dense graphs where all-pairs shortest path is needed.

### Kruskal’s and Prim’s Algorithms
- **Kruskal’s Detailed Analysis**: Kruskal’s algorithm sorts all edges and uses a union-find data structure to detect cycles, ensuring a minimum spanning tree.
- **Prim’s Detailed Analysis**: Prim’s algorithm builds the minimum spanning tree by adding the smallest edge that connects a vertex in the tree to a vertex outside the tree.

### Huffman Coding
- **Detailed Complexity Analysis**: Huffman coding creates a binary tree based on the frequencies of characters, resulting in O(n log n) complexity for building the tree.
- **Practical Use**: Commonly used in data compression algorithms, such as ZIP and JPEG.

### Minimax Algorithm
- **Detailed Complexity Analysis**: Minimax explores all possible moves in a game tree, leading to exponential complexity based on the depth of the tree.
- **Practical Use**: Used in decision making and AI for games like chess and tic-tac-toe.


# Notes on Max’s Review Doc
---

### Coin Changing Algorithm
- **Greedy**: Find the minimum number of coins to make n cents by using the max-cent coin each time.
- **Dynamic**: Keep track of the minimum number of coins to make every cent value up to n cents.

---

### Big O Notation
- **O**: f(x) = O(g(x)) if ∃x₀,C > 0 such that ∀x ≥ x₀, f(x) ≤ Cg(x).
- **Ω**: f(x) = Ω(g(x)) if ∃x₀,B > 0 such that ∀x ≥ x₀, f(x) ≥ Bg(x).
- **Θ**: f(x) = Θ(g(x)) if ∃x₀,B > 0,C > 0 such that ∀x ≥ x₀, Bg(x) ≤ f(x) ≤ Cg(x).

---

### Greedy Algorithm
Generally grabs the most obvious good-looking solution. Usually not optimal.

---

### Dynamic Programming
A technique where we cache results as we go. Identifying redundant subproblems and eliminating them (e.g., Minimum number of coins or calculating a Fibonacci term mainly uses the results of recursive calls with reduced input, so there is no need to recompute the lower recursive calls over and over).

---

### Divide And Conquer
Divide a list in two and recurse.

---

### Limit Theorems
- **Lim f/g ≠ 0 or ∞** → f = Θ(g)
- **Lim f/g ≠ 0** → f = Ω(g)
- **Lim f/g ≠ ∞** → f = O(g)

---

### Basic Derivatives
- xⁿ → n*xⁿ⁻¹
- nˣ → nˣ * ln(n)
- logₐ x → 1/(x ln(a))
- ln(x) → 1/x

---

### Basic Summations
- ∑n = n(n+1)/2
- ∑n² = n(n+1)(2n+1)/6
- ∑rⁱ = (rⁿ+¹ - 1) / (r - 1)

---

### Maximum Contiguous Subarray (MCS)
- **Brute Force** → O(n²)
  - Go through all possible combinations.
- **Divide & Conquer** → O(n log n)
  - Break list into sublists.
  - Find MCS within those sublists.
  - Find straddling sum for the input.
  - Return maximum of left MCS, right MCS, and the straddling sum.
- **Kadane’s Algorithm** → O(n)
  - Dynamic programming approach.
  - For list A & an index i, define MCS ending at i that goes up to and includes i. The MCS ending at index i is max(A[i], A[i] + MCS ending at i-1).

---

### Bubble Sort
**Time complexity**: 
Since a single pass iterates over the entire list minus the sorted part, and each pass places one element in the sorted part, the number of comparisons is 1 + 2 + … + (n - 1) = n(n - 1)/2, and the number of swaps is the number of inversions.
- **Advantages**: Simple and efficient for small lists; stable and uses O(1) auxiliary memory.
- **Disadvantages**: Inefficient for large lists due to O(n²) time complexity.

**Post-first pass**: The last element will be in the correct place. After n passes, the last n elements will be in their correct positions.

---

### Insertion Sort
**Time complexity**: 
A single pass iterates up to the entire sorted part’s length. The number of comparisons is 1 + 1 + … 1 (n - 1 times) = n - 1 in the best case, or 1 + 2 + … + (n - 1) = n(n - 1)/2 in the worst case. The numbers of comparisons and of swaps/shifts are the number of inversions, give or take a constant on each pass (which doesn’t affect the asymptotic time complexity).

**Advantages**: Efficient for small and nearly sorted lists; stable.
**Disadvantages**: Inefficient for large lists due to O(n²) time complexity.

---

### Selection Sort
**Post-first pass**: The first element will be in the correct place. After n passes, the first n elements will be in their correct positions.
**Operations comparison with Bubble Sort**: Selection sort uses fewer operations because it performs fewer swaps.
**Advantages**: Simple and uses a minimal number of swaps.
**Disadvantages**: Inefficient for large lists due to O(n²) time complexity; not stable.

---

### Merge Sort
**Recurrence relation**: T(n)= 2T(n/2)+Θ(n).
**Parallelization**: Merge sort splits the list in half repeatedly until you have a single element, and then merges those lists together. Because when merging, both lists are already sorted, so you can compare the first two elements in each sublist when forming a combined list.

---

### Quick Sort
**Partition**: The pivot is the reference point around which elements are partitioned during the sorting process. After partitioning, to the left of the pivot will be elements smaller, to the right, elements greater.
**Worst-case**: T(n)=T(n−1)+c2n+(c1 −c2)=Θ(n²). Occurs when the pivot is the smallest or largest element.
**Best-case**: T(n)=2T(n/2)+c2n+(c1 −c2)=Θ(n log n). Occurs when the pivot is the median element.
**Advantages**: Generally faster for large lists; in-place sorting.
**Disadvantages**: Worst-case performance is O(n²); not stable.

---

### Heap Sort
**Heap**: A complete binary tree where each node is greater/less than all elements in its subtrees (for a max/min heap, respectively).
**Heap operations**: To restore the heap property, use local information to determine which node should go where.
**Advantages**: Good for large lists; in-place sorting.
**Disadvantages**: Not stable.

---

### Radix Sort
**Underlying sort**: Must be stable to ensure the overall sort is stable.
**Base and digits**: As the base and the number of digits increase, the time complexity increases.
**LSD vs. MSD**: Least significant digit (LSD) ensures stability and proper sorting.

---

### Counting Sort
**Counting array**: First pass step where numbers are counted.
**Cumulative array**: Second step, cumulative counts.
**Weaknesses**: Not suitable when k is much higher than n; high space complexity.
**Ideal data set**: Small range of values but high input.

---

### Bucket Sort
**Bucket properties**: Buckets are chosen based on the input distribution; aim for an average of 1 item per bucket.
**Underlying sort**: Should be fast and stable.
**Ideal data set**: Uniformly distributed data.
**Average case**: Same as best case because the underlying sort runs efficiently with small buckets.

---

### Master Theorem: (T(n) = aT(n/b) + f(n))
- **Case 1**: If f(n) = O(n^c) and log_b(a) > c, then T(n) = Θ(n^log_b(a)).
- **Case 2**: If f(n) = Θ(n^c) and log_b(a) = c, then T(n) = Θ(n^log_b(a) * log(n)).
- **Case 2f**: If f(n) = Θ(n^c (log n)^d) and log_b(a) = c, then T(n) = Θ(n^log_b(a) * (log(n))^d+1). -> Side note - Case 2 is actually case 2f with d = 0. 
- **Case 3**: If f(n) = Ω(n^c) and log_b(a) < c, then T(n) = Θ(f(n)).

---

### Karatsuba
**Schoolbook multiplication**: Quadratic in the number of digits. Karatsuba reduces multiplications by decomposing the problem and reusing results.

---

### Graphs
**Terminology**:
- **Path**: A walk with no repeated edges or vertices.
- **Walk**: A sequence from one vertex to another, allowing repeated vertices and edges.
- **Trail**: A walk with no repeated edges.
- **Tour**: A path that visits all vertices, starting and ending on the same node.
- **Degree**: Number of edges that a vertex is an endpoint of.
- **Vertex**: A node.
- **Edge**: A connection between two vertices.
- **Adjacency List**: A list that stores lists of each vertex’s neighbors.
- **Adjacency Matrix**: A 2D array that stores whether or not i and j are connected.

**Breadth First Search (BFS)**:
- **Strengths**: Finds the shortest path in unweighted graphs.
- **Weaknesses**: High memory usage for large graphs.
- **Data structure**: Queue.

**Depth First Search (DFS)**:
- **Strengths**: Low memory usage.
- **Weaknesses**: Not guaranteed to find the shortest path.
- **Data structure**: Stack.

**Dijkstra’s Algorithm**:
- **Single-source shortest path**.
- **Negative weights**: Can lead to incorrect results.

**Floyd’s Algorithm**:
- **All-pairs shortest path**.
- **Negative weights**: Works if no negative weight cycles.

**Kruskal’s Algorithm**:
- **Minimum Spanning Tree (MST)**.
- **Advantage**: Simple and efficient for sparse graphs.
- **Disadvantage**: Harder to implement cycle detection.

**Prim’s Algorithm**:
- **Minimum Spanning Tree (MST)**.
- **Advantage**: Efficient for dense graphs.

---

### Minimax Algorithm
**Heuristic**: A function that assigns a value to each position in the game.
**Probabilistic spaces**: Minimax with expected value can give a false idea of the best move.

---

### Huffman Coding
**Encoding tree**: Used to find the encodings for each letter.
**Variable length**: Reduces the number of bits.
**Fixed-length vs. Huffman**: Fixed-length uses the same length encoding for all characters, while Huffman uses variable length.

---

### P and NP
**P**: Problems solvable in polynomial time.
**NP**: Problems verifiable in polynomial time.
**Reduction**: Showing one problem can be transformed into another.

---
#### Selection Sort
1. **Why is selection sort preferred for small data sets?**
   - Selection sort is simple to understand and implement. For small data sets, the quadratic time complexity does not significantly impact performance.

#### Radix Sort
2. **How would you modify Radix Sort to handle variable-length strings?**
   - Pad the shorter strings with a special character (e.g., '\0') that is smaller than any other character in the set. This ensures that shorter strings are sorted correctly relative to longer strings.

#### Bucket Sort
3. **How does the distribution of input data affect the choice of buckets?**
   - The choice of buckets should reflect the distribution of the input data. If data is uniformly distributed, evenly sized buckets are ideal. If data is skewed, adjusting bucket sizes to handle different densities can improve efficiency.

#### Master Theorem
4. **How would the recurrence relation change for a problem divided into three parts instead of two?**
   - The recurrence relation would change to T(n) = 3T(n/3) + Θ(n). The analysis using the Master Theorem would then follow the same steps, comparing the complexity of the divide step to the combined complexity of the recursive calls.

#### Graph Algorithms
5. **Explain the differences between using adjacency lists and adjacency matrices for graph representation.**
   - **Adjacency List**:
     - Space Complexity: O(V + E).
     - Efficient for sparse graphs.
     - Faster for iterating over neighbors of a vertex.
   - **Adjacency Matrix**:
     - Space Complexity: O(V²).
     - Efficient for dense graphs.
     - Faster for checking the presence of an edge between two vertices.

