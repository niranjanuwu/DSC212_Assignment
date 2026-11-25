# Modularity on the Karate Club Graph (DSC212, Graph Theory Module)

Spectral modularity community detection (Newman, 2006) implemented from scratch with
NumPy and NetworkX on Zachary's Karate Club network.

## Contents
| File | Description |
|---|---|
| `KarateClub_Modularity.ipynb` | Main notebook: runs top-to-bottom with no manual edits |
| `assets/` | Figures produced by the notebook (graph, splits per iteration, metric evolution) |
| `requirements.txt` | Python dependencies |

## What the notebook does
1. Builds the adjacency matrix `A` and modularity matrix `B = A - k k^T / 2m`
2. Two-way split from the sign of the leading eigenvector of `B` (Q = 0.371; matches the real split except node 8)
3. Recursive bisection until every community has leading eigenvalue <= 0 (5 communities, Q = 0.409)
4. Plots the graph after each iteration with a fixed layout
5. Computes degree, betweenness, closeness and clustering after each iteration (on each community's induced subgraph)
6. Plots the evolution of each metric and discusses the results

## Run it
```bash
pip install -r requirements.txt
jupyter notebook KarateClub_Modularity.ipynb   # Kernel -> Restart & Run All
```
The notebook creates `assets/` itself if it does not exist.

## Reference
Newman, M. E. J. (2006). Modularity and community structure in networks. *PNAS* 103(23):8577-8582.
Disclaimer: Use of AI to aid, as permitted by the assignment
