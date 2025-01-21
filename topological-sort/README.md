# Topological Sort Problems : O(V+E)

Topological sort of a directed graph is a linear ordering of its vertices such that for every directed edge (u,v) from vertex u to vertex v, u comes before v in the ordering.

When topological sort is implemented using **Kahn's Algorithm (BFS with a queue)**, the time complexity and space complexity are as follows:

### Time Complexity : O(V+E)
##### Explanation:
1. Counting in-degrees takes 𝑂(𝐸) time because we iterate over each edge once.
2. Enqueueing and dequeueing each vertex takes 𝑂(𝑉) time.
3. Processing each neighbor of each vertex (decreasing in-degrees and enqueuing zero in-degree nodes) takes 𝑂(𝐸) time as each edge is visited once.

### Space Complexity : : O(V+E)
##### Explanation:
The space complexity is also 𝑂(𝑉+𝐸) because:
1. We need space to store the graph (using an adjacency list) with 𝑉 vertices and 𝐸 edges, which takes 𝑂(𝑉+𝐸).
2. We maintain an in-degree array of size 𝑉, taking 𝑂(𝑉).
3. The queue holds vertices with zero in-degrees, and in the worst case, all vertices could be added to the queue, so it also takes 𝑂(𝑉) space.


## Problems :
1. https://leetcode.com/problems/course-schedule
2. https://leetcode.com/problems/course-schedule-ii
3. https://leetcode.com/problems/parallel-courses
4. https://leetcode.com/problems/find-all-possible-recipes-from-given-supplies
5. https://leetcode.com/problems/alien-dictionary
