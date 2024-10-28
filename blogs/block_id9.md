---

# Heavy-Light Decomposition (HLD)

### Difficulty: Very Hard   
**Topic**: Advanced Tree Data Structures  
**Time Complexity**: \( O(\log^2 N) \) for queries  
**Space Complexity**: \( O(N) \) 

---


Heavy-Light Decomposition (HLD) is an advanced technique used in trees to break down a path into "heavy" and "light" edges. This method is especially powerful in solving **range queries** (e.g., sum, min, max) and **path updates** between nodes in trees. HLD is mainly used in competitive programming and advanced data structure problems.

---

### Algorithm

1. **Tree Traversal**: Calculate the subtree size for each node in a Depth-First Search (DFS).
2. **Heavy Edge Selection**: For each node, select the child with the largest subtree size as the "heavy" child.
3. **Heavy-Light Paths**:
   - Assign each node to either a heavy path or a light path based on its position relative to the "heavy" child.
   - Label paths so that each node is part of a continuous segment in an array.
4. **Segment Tree**: Use a Segment Tree or Fenwick Tree to handle range queries and updates on the flattened tree array.

---

### Input and Output

- **Input**:
  - A tree with nodes and edges.
  - Queries involving range queries (e.g., sum, min) or point updates between nodes.
- **Output**:
  - The result of each query, based on the current tree structure.

---

### Example

#### Input

A tree structured as follows:
    1
   / \
  2   3
 / \   \
4   5   6
- Queries: Find the sum between nodes 4 and 5, or update the value at node 3.

#### Output

Results for the specified queries, such as path sums, min, or max values.

---

### Solution Outline

Here is an outline of the solution using HLD:

```python
class HLD:
    def __init__(self, n):
        self.n = n
        self.tree = [[] for _ in range(n)]
        self.size = [0] * n
        self.parent = [-1] * n
        self.depth = [0] * n
        self.chain_head = [-1] * n
        self.pos_in_base = [-1] * n
        self.curr_pos = 0

    def dfs_size(self, u):
        """Calculate subtree sizes and parents using DFS."""
        self.size[u] = 1
        for v in self.tree[u]:
            if v != self.parent[u]:
                self.parent[v] = u
                self.depth[v] = self.depth[u] + 1
                self.size[u] += self.dfs_size(v)
        return self.size[u]

    def decompose(self, u, head):
        """Decompose tree into heavy-light paths."""
        self.chain_head[u] = head
        self.pos_in_base[u] = self.curr_pos
        self.curr_pos += 1
        heavy_child, max_size = -1, 0
        for v in self.tree[u]:
            if v != self.parent[u] and self.size[v] > max_size:
                heavy_child, max_size = v, self.size[v]
        if heavy_child != -1:
            self.decompose(heavy_child, head)
        for v in self.tree[u]:
            if v != self.parent[u] and v != heavy_child:
                self.decompose(v, v)
## Explanation

- **Tree Size Calculation**: A Depth-First Search (DFS) is used to calculate subtree sizes.
- **Heavy Path Assignment**: Each node’s child with the largest subtree is designated as “heavy.”
- **Path Decomposition**: Nodes are grouped into heavy paths, minimizing the number of paths a query crosses.
- **Flattened Representation**: The tree is mapped into an array where each path segment is continuous, enabling efficient range queries with a Segment Tree.


## Pros and Cons

- **Pros**:
  - Efficient path-based operations in trees.
  - Reduces complex tree queries to simpler range queries on an array.
- **Cons**:
  - Difficult to implement and understand.
  - Limited to trees and paths, less flexible for general graph types.

## Use Cases

- **Path Queries**: Ideal for answering range queries along paths in trees (e.g., sum, min, max).
- **Point Updates**: Useful for updating values at nodes within a tree and quickly reflecting them on paths.
- **Lowest Common Ancestor (LCA)**: Can work alongside HLD for efficient LCA computation in tree structures.

## Additional Challenges

1. **Dynamic Edge Updates**: Adapt HLD to work with dynamic edge weights.
2. **Path XOR Queries**: Modify the algorithm to handle XOR queries along a path.
3. **Advanced Tree Queries**: Solve complex tree-based range queries by combining HLD with other techniques.