---
layout: default
title: GraphEm - Graph Embedding and Influence Maximization
---

# GraphEm: Graph Embedding and Influence Maximization

**Authors**: A. Kolpakov and I. Rivin

## Abstract

Computing classical centrality measures such as betweenness and closeness is computationally expensive on large-scale graphs. In this work, we introduce an efficient force layout algorithm that embeds a graph into a low-dimensional space, where the radial distance from the origin serves as a proxy for various centrality measures. We evaluate our method on multiple graph families and demonstrate strong correlations with degree, PageRank, and paths-based centralities. As an application, it turns out that the proposed embedding allows to find high-influence nodes in a network, and provides a fast and scalable alternative to the standard greedy algorithm.

## Overview

GraphEm is a Python library for graph embedding and node influence maximization, featuring advanced algorithms with JAX backend for GPU/TPU acceleration. The library provides efficient solutions for computing centrality measures and finding influential nodes in large-scale networks.

## Key Features

- **Graph embedding** with Laplacian-based layout
- **JAX backend** for GPU/TPU acceleration  
- **Influence maximization** algorithm
- **Graph generators** and visualization tools
- **Benchmarking** capabilities

## Installation

```bash
pip install graphem-jax
```

## Quick Usage Examples

### 1. Graph Embedding

```python
import graphem as ge

# Generate a graph
edges = ge.erdos_renyi_graph(n=500, p=0.01)

# Create embedder
embedder = ge.GraphEmbedder(edges=edges, n_vertices=500, dimension=3)

# Run layout algorithm
embedder.run_layout(num_iterations=50)

# Display results
embedder.display_layout()
```

### 2. Influence Maximization

```python
# Select influential seeds
seeds = ge.graphem_seed_selection(embedder, k=10)

# Estimate influence
influence, _ = ge.ndlib_estimated_influence(G, seeds, p=0.1)
```

## Key Components

- **`GraphEmbedder` class** - Core embedding functionality
- **Multiple graph embedding algorithms** - Various layout and generation methods
- **Network datasets access** - Built-in dataset support
- **Visualization tools** - Display and analyze results

## 🔍 Paper
Read the paper: [PDF](paper.pdf) • [arXiv](https://arxiv.org/abs/2506.07435)

## 🧠 Code
Check the code on [GitHub](https://github.com/igorrivin/graphem.git)

## 💻 Resources
- [Full Documentation](https://github.com/igorrivin/graphem)
- [Examples and Tutorials](https://github.com/igorrivin/graphem/tree/main/examples)

## 📄 License
MIT License

## 📫 Contact
Questions? Reach out at [rivin@temple.edu](mailto:rivin@temple.edu)