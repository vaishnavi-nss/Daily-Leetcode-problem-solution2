# Daily-Leetcode-problem-solution2
Problem

In this problem, a tree is an undirected graph that is connected and has no cycles.
You are given a graph that started as a tree with n nodes labeled from 1 to n, with one additional edge added. The added edge has two different vertices chosen from 1 to n, and was not an edge that already existed. The graph is represented as an array edges of length n where edges[i] = [ai, bi] indicates that there is an edge between nodes ai and bi in the graph.
Return an edge that can be removed so that the resulting graph is a tree of n nodes. If there are multiple answers, return the answer that occurs last in the input.


Approach

I have a parent array in which every node is pointing to itself.
I used Find with path compression to quickly determine the root of a node.
I used Union by rank to merge sets efficiently.
Iterate through the given edges and try to union them.
If an edge is found that connects two nodes already in the same connected component (i.e., they have the same root), that edge is redundant.
Return the last edge.

Complexity
Time complexity:

Find operation (with path compression):
O(α(n)) (inverse Ackermann function, nearly constant time)
Union operation (by rank):
O(α(n))
Processing all edges:
O(nα(n)) can be simply put as O(n)

Space complexity:

Parent Array: Stores the parent of each node → O(n)
Recursive Stack (Find with Path Compression): In the worst case, the depth of recursion is O(log n) (almost constant due to path compression).
Other Variables: Only a few extra integers for processing edges → O(1)
Overall Space Complexity:
O(n)
since the dominant factor is the parent array.
