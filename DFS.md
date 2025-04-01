Depth First Search Algorithm

For Adjacency Matrix
```python
        def dfs(node):

            nonlocal visited

            visited[node] = True

            for i in range(n):
                if graph[node][i] and not visited[i]:
                    dfs(i)
```

For Node List
```python
        def dfs(node, graph):

            nonlocal visited

            visited[node] = True

            for neighbour in graph[node]:
                if not visited[neighbour]:
                    dfs(neighbour)
```
