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

### Notes on Max’s Review Doc

**Reasons for time complexity (incomplete)**:
- **Counting sort**: Finding the maximum and the cumulative list takes n time, and finding the sorted list takes k time. Note that k and n are independent variables.
- **Radix sort**: You do the underlying sort d times, where d is the number of digits.
- **Bucket Sort**:
  - **Best case**: every bucket has exactly 1 item (uniformly distributed).
  - **Average case**: The average amount of items per bucket is close to 1.
  - **Worst case**: Most of the items are in one bucket, so the runtime is essentially the same as doing the underlying sort.

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

### Additional Questions:
1. **Selection Sort**: Why is selection sort preferred for small data sets?
2. **Radix Sort**: How would you modify Radix Sort to handle variable-length strings?
3. **Bucket Sort**: How does the distribution of input data affect the choice of buckets?
4. **Master Theorem**: How would the recurrence relation change for a problem divided into three parts instead of two?
5. **Graph Algorithms**: Explain the differences between using adjacency lists and adjacency matrices for graph representation.
