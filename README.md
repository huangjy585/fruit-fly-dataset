# Fruit-Fly Protein Interaction Dataset

## Description

This repository provides a copy of the Fruit-Fly protein interaction dataset used for research experiments.

The original dataset link is no longer available, so this repository is maintained as an accessible copy of the dataset for reproducibility.

The dataset represents a weighted protein-protein interaction network, where nodes correspond to proteins and edges represent interactions between proteins.

## Dataset Statistics

- **Dataset name:** Fruit-Fly
- **Number of nodes:** 3,751
- **Number of edges:** 3,692
- **Graph type:** Weighted graph
- **File:** `Fruit-Fly.txt`

## File Format

The dataset is stored as a weighted edge list in CSV format:

```text
v1,v2,weight
```

Each row contains one weighted edge:

- `v1`: ID of the first node/protein
- `v2`: ID of the second node/protein
- `weight`: edge weight

Example:

```text
1,1618,0.160
1,2941,0.217
2,333,0.224
```

## Usage

### Load with pandas

```python
import pandas as pd

edges = pd.read_csv("Fruit-Fly.txt", header=None)
edges.columns = ["v1", "v2", "weight"]

print(edges.head())
```

### Load with NetworkX

```python
import networkx as nx

G = nx.read_weighted_edgelist(
    "Fruit-Fly.txt",
    delimiter=",",
    nodetype=int
)

print("Number of nodes:", G.number_of_nodes())
print("Number of edges:", G.number_of_edges())
```

## Notes

- Node IDs are represented as integers.
- Edge weights are represented as floating-point values.
- No additional node attributes are included.
- Unless otherwise specified, the dataset can be treated as an undirected weighted graph.

## Citation

This repository is provided only as an accessible copy of the Fruit-Fly dataset because the original dataset link is unavailable.

If you use this dataset, please cite the original data source if you know it. If the original source cannot be found, you may cite or link to this repository only as a dataset access location.

Example:

```text
Fruit-Fly Protein Interaction Dataset. Available at: https://github.com/<your-username>/<repository-name>
```

## License

Please verify the license of the original dataset before redistribution or reuse. If the original license cannot be identified, use this repository with appropriate caution and attribution.
