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
