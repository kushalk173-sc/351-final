# 351-final

# All Algorithm Information
| **Algorithm** | **Description** | **Worst Case** | **Best Case** | **Average Case** | **Recurrence Relation** | **In-Place** |
|----------------|-----------------|---------------|---------------|----------------|-------------------------|-------------|
| **Bubble Sort** | Iterates through a list of length n, starting at the beginning and swapping elements if the current is bigger. <br> After each step, the rightmost side becomes sorted. | O(n²) | O(n) | O(n²) | - | Yes |
| **Insertion Sort** | Starting with a list A of length n, pick up A[1]. Look left. If anything left is larger, slide it to the right, then insert. Continue to iterate through the list until sorted. | O(n²) | O(n) | O(n²) | - | Yes |
| **Selection Sort** | Look through a list A, find the index of the smallest item. Swap A[that index] with A[0]. Now A[0] is correctly placed. Then look through the rest of the list for the index of the smallest item. Swap with A[i]. | O(n²) | O(n²) | O(n²) | - | Yes |
| **Merge Sort** | Divide list by 2, repeating until the sublists are of size 2. Then, compare & sort the elements in each list. Merge the sublists with ones next to it and compare and sort. Repeat until the list is of size n. | O(n log n) | O(n log n) | O(n log n) | T(n) = 2T(n/2) + Θ(n) | No |
| **Quick Sort** | Pick a key and rearrange so all values left of the key are smaller & all values right of key are larger. Repeat until no more smaller lists. | O(n²) | O(n log n) | O(n log n) | Worst case: T(n) = T(k) + T(n-k) + Θ(n), Best Case: T(n) = 2T (n/2) + Θ(n) | Yes |
| **Heap Sort** | Convert to maxheap and then sort by repeatedly removing the maximum element and rebuilding the heap. | O(n log n) | O(n) | O(n log n) | - | Yes |
| **Radix Sort** | Underlying sort must be stable to work at all. Run the underlying sort on the list based only on the rightmost digit. Repeat this process on the next-rightmost digit until you have sorted the list on the leftmost digit. | Θ(d(n +(b - 1))) | Θ(d(n +(b - 1))) | Θ(d(n +(b - 1))) | - | No |
| **Counting Sort** | Create a list from 0 to the max key, populated with how many keys equal the index. Make a cumulative version of that list. Using this position list, iterate the input list backwards, placing each element in the appropriate position by key and then decrementing the position. | O(n+k) | O(n+k) | O(n+k) | - | No |
| **Bucket Sort** | Distribute elements into buckets, sort each bucket, and then concatenate the sorted buckets. | O(n²) | O(n) | O(n) | - | No |
| **Binary Search** | The input list must be sorted. Check the median of the list. Either it is the target, or search the appropriate half of the list. | O(log n) | O(1) | O(log n) | - | N/A |
| **Karatsuba** | A more efficient way of multiplication. AB = (10^n)A1B1 + (10^(n/2))[(A1 + A0)(B1 + B0) - A0B0 - A1B1] + A0B0 | - | - | - | T(n) = 3T(n/2) + Θ(n) | N/A |
| **BFS** | 1) Add the starting node to a queue. <br> 2) Pop from the queue. <br> 3) Add all the popped element’s new neighbors to the queue. <br> 4) Repeat 2-4 until you’ve found the node you wanted. | O(V²) for adjacency matrix, O(V + E) for adjacency list | - | - | - | N/A |
| **DFS** | 1) Add the starting node to a stack + visited set. <br> 2) Pop from the stack.<br> 3) Add all the popped element’s new neighbors to the stack.<br> 4) Repeat 2-4 until you’ve found the node you wanted. | O(V² + E) for adjacency matrix, O(V + E) for adjacency list | - | - | - | N/A |
| **Dijkstra’s** | Single-source shortest path algorithm. | Θ(V³) for adjacency matrix, Θ(V² + E) for adjacency list, Θ(E log V) for min heap | - | - | - | N/A |
| **Floyd’s** | Finds shortest paths for a weighted (pos or neg) and directed graph using an adjacency matrix. | O(V³) | - | - | - | N/A |
| **Kruskal’s** | Creates a minimum spanning tree. Starts at the edge with the smallest value, and uses the next smallest one until all nodes are reached. | O(E log E) | - | - | - | N/A |
| **Prim’s** | Creates a minimum spanning tree. Starts at the edge with the smallest value and uses the smallest edge connected to a node that it has reached as the next edge to visit. | O(E log V) with min heap, O(V²) with adjacency matrix | - | - | - | N/A |
| **Huffman** | A way to express something (a string) in the minimum number of bits. <br> 1) Create nodes with each value.<br>  2) Combine the two nodes with the lowest frequency and merge them where the parents are the total of the children. <br> 3) Repeat until the top node is the total count of all nodes. | O(n log n) | O(n log n) | O(n log n) | - | N/A |
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
- **Practical Use**: Widely used due to its predictable O(n log n) time complexity and stability. It is the basis for many modern sorting algorithmst.

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

#### Big O
Essentially Big O represents an upper bound, or a function which is >= our function f(x) at every point. This helps us because it acts as a better represented upper bound for our function <br>
Big O will be better represented by the fact that f(x)/g(x) <= C. Example solve 
![Screenshot (166)](https://github.com/kushalk173-sc/351-final/assets/71304688/065ea6af-c011-47aa-91f2-22fee3dc68db)
![image](https://github.com/kushalk173-sc/351-final/assets/71304688/96921661-4a30-459c-9038-53aec2f2031d)

#### Big Theta
Big Theta acts as a tight bound for our function, where it tries to represent our exact function in a better way, where all we care about is the average runtime, and is the most commonly used runtime, and not some arbitrary constant. here is an example solution 
![image](https://github.com/kushalk173-sc/351-final/assets/71304688/ae7d2194-8725-4a7d-bc4c-ea4a32f123d3)

#### Big Omega
Big Omega acts as a lower bound for our function. Solves similar to Big O, with the sign flipped. 
f(x)/g(x) => C

### Limit theorems for Big O
![image](https://github.com/kushalk173-sc/351-final/assets/71304688/c199e859-e97b-4693-b5ad-fcb45481b020)

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
**Each Bucket is stored with a specific 

---

### Master Theorem: (T(n) = aT(n/b) + f(n))
Better way to remember it <br>
T(n) = a T(n/b) + f(n) where Θ(x) = f(n) <br>
T(n) = Θ(x * n^log_b(a)) <br>
4 cases = <br>
x > n^log_b(a) -> ignore n^log_b(a) hence T(n) = Θ(x) [root is worst to process] <br>
x < n^log_b(a) -> ignore x hence T(n) = Θ(n^log_b(a)) [Leaves are worst to process<br>
x = n^log_b(a) -> Cannot ignore anything so T(n) = Θ(n^log_b(a) * log(n)) [All are equally bad to process] [We removed x here cuz technically processing root has been included in the first term]  <br>
Another catch - What x = n^c * (log n) ^ d , and c = log_b(a) Then ? We cannot ignore x's log factor anymore. So our Case changes into Θ(n^log_b(a) * (log(n))^d+1)<br>

- **Case 1**: If f(n) = O(n^c) and log_b(a) > c, then T(n) = Θ(n^log_b(a)).
- **Case 2**: If f(n) = Θ(n^c) and log_b(a) = c, then T(n) = Θ(n^log_b(a) * log(n)).
- **Case 2f**: If f(n) = Θ(n^c (log n)^d) and log_b(a) = c, then T(n) = Θ(n^log_b(a) * (log(n))^d+1). -> Side note - Case 2 is actually case 2f with d = 0. 
- **Case 3**: If f(n) = Ω(n^c) and log_b(a) < c, then T(n) = Θ(f(n)).

---

### Karatsuba
**Schoolbook multiplication**: Quadratic in the number of digits. Karatsuba reduces multiplications by decomposing the problem and reusing results.

### Overview
The Karatsuba algorithm is a divide-and-conquer algorithm for multiplying two large numbers more efficiently than the traditional grade-school method. It reduces the number of single-digit multiplications required to multiply two n-digit numbers.

### Traditional Multiplication
In the traditional method, multiplying two n-digit numbers involves performing \( n^2 \) single-digit multiplications. For example, to multiply 1234 by 5678, we perform \( 4 \times 4 = 16 \) single-digit multiplications.

### Karatsuba's Insight
The Karatsuba algorithm reduces the number of multiplications by splitting each number into two halves. Suppose we have two n-digit numbers \( A \) and \( B \), and we split them as follows:
- \( A = a1 \times 10^{n/2} + a0 \)
- \( B = b1 \times 10^{n/2} + b0 \)

Then the product \( AB \) can be written as:
\[ AB = (a1 \times 10^{n/2} + a0)(b1 \times 10^{n/2} + b0) \]
\[ = a1b1 \times 10^n + (a1b0 + a0b1) \times 10^{n/2} + a0b0 \]

Instead of performing four multiplications \( (a1b1, a1b0, a0b1, a0b0) \), Karatsuba's method calculates it using three multiplications:
1. \( z0 = a0 \times b0 \)
2. \( z1 = (a0 + a1) \times (b0 + b1) \)
3. \( z2 = a1 \times b1 \)

The product is then:
\[ AB = z2 \times 10^n + ((z1 - z2 - z0) \times 10^{n/2}) + z0 \]

### Complexity
The time complexity \( T(n) \) of the Karatsuba algorithm is:
\[ T(n) = 3T(n/2) + O(n) \]
Using the Master Theorem, we get:
\[ T(n) = O(n^{\log_2 3}) \approx O(n^{1.585}) \]

This is significantly faster than the traditional \( O(n^2) \) method, especially for large \( n \).

### Detailed Steps
1. **Base Case**: If the numbers are small enough (single-digit), multiply them directly.
2. **Recursive Case**:
   - Split the input numbers.
   - Recursively compute the three products.
   - Combine the results as per the formula.

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


## Minimax Algorithm

### Overview
It is an algorithm for representing game states.

### Use Cases 
The game needs to fulfil certain criteria for minimax to be used. 
- It must be an adversarial game
- They must be representable as a tree -> They must have discrete states,
- The game must be zero sum -> No action can benefit more than one player. Hence one players gain = Other players loss -> making sum of all heursitic functions of all players involved = 0
- Games must be deterministic, or can they be stochastic even? 

### Game Representation
In a game with two players, Max and Min:
- Max aims to maximize the score.
- Min aims to minimize the score.

The game can be represented as a tree where:
- Nodes represent game states.
- Edges represent moves by players.
- Leaf nodes represent terminal states of the game with their heuristic values.

### Algorithm Steps
1. **Initialization**: Start at the root node (current game state).
2. **Recursive Evaluation**:
   - If the node is a terminal node, return its heuristic value.
   - If it's Max's turn, calculate the maximum value of the child nodes.
   - If it's Min's turn, calculate the minimum value of the child nodes.
3. **Backpropagation**: Propagate these values back up the tree, alternating between Max and Min layers, and placing the optimal value for both states in each of the parent root nodes. 

### Complexity
- **Time Complexity**: \( O(b^d) \), where \( b \) is the branching factor and \( d \) is the depth of the tree.
- **Space Complexity**: \( O(b \cdot d) \) due to the space required to store the tree and recursive call stack.

### Practical Considerations
In real-world scenarios, the game tree can be extremely large, making it impractical to search completely. Techniques like **alpha-beta pruning** can reduce the effective branching factor, making the search more feasible.

### Alpha-Beta Pruning
This optimization reduces the number of nodes evaluated by the minimax algorithm. It maintains two values, alpha and beta:
- **Alpha**: The best value that the maximizer currently can guarantee.
- **Beta**: The best value that the minimizer currently can guarantee.

If a move proves to be worse than the previously examined moves, it is pruned (i.e., not evaluated further).

The entire point of running alpha-beta pruning is to make sure that we are not focusing on dead values. In a game tree, when we find a node which will not be executed, as it is a worse choice than its sibling, then we remove it and the subtree for which it is a parent

**TODO: GET MORE INFO FROM OH** 

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

### Overview

P vs. NP is one of the most critical open problems in computer science and mathematics. It relates to the ability to solve problems versus the ability to verify solutions.

### Definitions

1. **P (Polynomial Time)**: 
   - Class of decision problems that can be solved by a deterministic Turing machine in polynomial time.
   - Example: Checking if a list is sorted.

2. **NP (Nondeterministic Polynomial Time)**:
   - Class of decision problems for which a given solution can be verified by a deterministic Turing machine in polynomial time.
   - Example: Given a solution to Sudoku, verifying it is correct.

### Relationship between P and NP
- **P ⊆ NP**: If a problem can be solved in polynomial time, it can certainly be verified in polynomial time.
- **NP-Complete**: The hardest problems in NP. If any NP-complete problem can be solved in polynomial time, then P = NP.

### Examples of Problems

- **In P**:
  - Sorting a list
  - Finding the greatest common divisor
  - Solving linear equations

- **In NP (but not known to be in P)**:
  - The Traveling Salesman Problem (decision version): Is there a tour of length ≤ k?
  - The Hamiltonian Cycle Problem: Does a given graph have a Hamiltonian cycle?

### Importance
The question of whether \( P = NP \) remains unsolved. Proving \( P = NP \) would imply that every problem whose solution can be verified quickly can also be solved quickly. This would have profound implications across various fields, from cryptography to algorithm design.

### Problem Reduction and NP-Completeness
- **Polynomial-Time Reduction**: A problem \( A \) can be reduced to problem \( B \) in polynomial time if any instance of \( A \) can be transformed into an instance of \( B \) in polynomial time.
- **NP-Complete Problems**: If a polynomial-time algorithm is found for one NP-complete problem, all NP problems can be solved in polynomial time, proving \( P = NP \).

### Example: SAT Problem
- **SAT (Satisfiability Problem)**: Given a Boolean formula, determine if there is an assignment of truth values to variables that makes the formula true.
- **NP-Completeness**: SAT was the first problem proven to be NP-complete (Cook-Levin theorem).

**TODO: Talk about NP reductions in OH**

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

---

# Other Good to know information - Not super important for me 

### Greedy Algorithm
Generally grabs the most obvious good-looking solution. Usually not optimal.

---

### Dynamic Programming
A technique where we cache results as we go. Identifying redundant subproblems and eliminating them (e.g., Minimum number of coins or calculating a Fibonacci term mainly uses the results of recursive calls with reduced input, so there is no need to recompute the lower recursive calls over and over).

---

### Divide And Conquer
Divide a list in two and recurse.

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
