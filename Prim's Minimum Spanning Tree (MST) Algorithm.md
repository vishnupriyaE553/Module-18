# Ex. No: 12A - Prim's Minimum Spanning Tree (MST) Algorithm

## AIM:
To write a Python program for **Prim's Minimum Spanning Tree (MST)** algorithm.

## ALGORITHM:

**Step 1**: Initialize the `key[]` array to infinity, set the first vertex's key to `0`, and create `mstSet[]` and `parent[]` arrays.

**Step 2**: Select the vertex with the smallest key value not yet included in `mstSet`.

**Step 3**: Add the selected vertex to `mstSet`.

**Step 4**: For all adjacent vertices:
- If the edge weight is smaller than their current key value, and the vertex is not in `mstSet`, then:
  - Update their key value
  - Update their parent to the current vertex

**Step 5**: Repeat Steps 2–4 until all vertices are included in the MST.

**Step 6**: Print the resulting Minimum Spanning Tree using the `parent[]` array.

## PYTHON PROGRAM

```
ADD YOUR CODE HERE
```

## OUTPUT

```
```


## RESULT


