# PageRank Algorithm Code
This repository contains multiple implementations of the PageRank algorithm, a link analysis algorithm used to determine the importance of nodes in a graph. The project showcases three different methods to compute PageRank using Python and demonstrates how to use the built-in PageRank function from the NetworkX library.

# Introduction
The PageRank algorithm evaluates the relative importance of nodes in a graph by simulating the behavior of a random web surfer. Originally developed by Google to rank web pages, it assigns importance to each node based on the number and quality of incoming links.

This project provides:
<ul>
    <li>Multiple ways to input graphs: using an adjacency matrix, XML files, or manually defined edges.</li>
    <li>A comparison with NetworkX’s built-in PageRank functionality.</li>
</ul>

# Project Structure
<ul>
    <li>Method 1: Uses an adjacency matrix as input.</li>
    <li>Method 2: Defines graph edges manually.</li>
    <li>Method 3: Parses an XML graph structure.</li>
    <li>Includes built-in NetworkX PageRank for comparison.</li>
</ul>

# Methods
## Method 1: PageRank from Adjacency Matrix
In this method, the graph is represented as an adjacency matrix, where each row indicates the outgoing links from a node.
```python
import numpy as np

# Define the adjacency matrix
adj_matrix = np.array([
    [0, 0, 0, 0, 0],  # Node A
    [0, 0, 1, 0, 0],  # Node B -> C
    [1, 1, 0, 0, 0],  # Node C -> A, B
])

# Compute PageRank
PageRank_Matrix(adj_matrix, node_ids)
```
## Method 2: PageRank from Graph Edges List
Here, define the graph by listing the edges directly in the code.
```python
import networkx as nx
edges = [('A', 'B'), ('B', 'C'), ('C', 'A')]
# Créer le graphe dirigé
G = nx.DiGraph()
G.add_edges_from(edges)

# Exécuter l'algorithme PageRank
page_rank_score(G)
```
## Method 3: PageRank from XML Graph
This method parses a graph from an XML file containing the nodes and edges, allowing for more complex graph structures.
```python
import xml.etree.ElementTree as ET
# Exemple d'utilisation avec le fichier XML
xml_file = 'edges.xml'
page_rank_score_from_xml(xml_file)
```
Example XML structure:
```xml
<graph>
  <node id="A">
    <edge target="B" />
  </node>
  <node id="B">
    <edge target="C" />
  </node>
</graph>
```
## Built-in NetworkX Method
NetworkX provides a built-in function to compute PageRank. This method demonstrates how to use it.
```python
def calculer_pagerank(G):
    # Créer un graphe orienté à partir des arêtes données
    G = nx.DiGraph(edges)
    
    # Calculer le PageRank
    pagerank = nx.pagerank(G, tol=1e-6, alpha=0.85)
    
    for node, rank in pagerank.items():
        print(f"PageRank du nœud {node}: {rank:.6f}")

# Appeler la fonction avec les arêtes données
calculer_pagerank(edges)
```
