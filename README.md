#  Molecular graph positional encoding from SMILES

Unlike texts in natural language processing (NLP), nodes in a graph do not have any canonical positional information. It has been shown that Laplacian eigenvectors can be used as node positional encoding [1]. This example demonstrates how to use [RDKit](https://www.rdkit.org/) from [MATLAB](https://matlab.mathworks.com/)® to process a [SMILES](https://en.wikipedia.org/wiki/Simplified_molecular-input_line-entry_system) database and generates positional encodings (PE) as part of graph-based transformer neural networks [2]. RDKit is licensed under [BSD 3-Clause License](https://github.com/rdkit/rdkit/blob/master/license.txt).  

### Usage
Run this MATLAB Live Script: 
> MATLAB_Python_Molecular_Graph_Analysis.mlx 

### RDKit Installation
RDKit [3] can be installed easily by following the instructions from this [source](https://www.rdkit.org/docs/Install.html). Linux, Windows, and macOS RDKit platform wheels are available at the rdkit PyPi repository for all major Python versions. You can install RDKit using pip. 

>  $ pip install rdkit

Make sure to check versions of Python compatible with MATLAB products by release. This allows to build proper [MATLAB Interface to Python](https://www.mathworks.com/support/requirements/python-compatibility.html) 

The Python path is setup at the beginning of the MATLAB live script.
> pyenv("Version","C:\Users\...\python.exe");


### How it works
The code takes in the provided `SMILES` string, extracts the adjacency and node matrices are store the generated molecular graph in "graph_data.mat". The code then computes the [eigenvalues and eigenvectors](https://www.mathworks.com/help/matlab/ref/eig.html) of the `Laplacian` of the graph. The Laplacian PE for each node is the `k` smallest non-trivial eigenvectors [4]. 

### References
[1] Mikhail Belkin and Partha Niyogi. Laplacian eigenmaps for dimensionality reduction and data representation. [Neural computation, 15(6):1373–1396, 2003](https://direct.mit.edu/neco/article-abstract/15/6/1373/6730/Laplacian-Eigenmaps-for-Dimensionality-Reduction?redirectedFrom=fulltext).

[2] Chengxuan Ying, et. al., Do Transformers Really Perform Bad for Graph Representation?, [2106.05234.pdf (arxiv.org)](https://arxiv.org/pdf/2106.05234.pdf).

[3] RDKit: Open-source cheminformatics; http://www.rdkit.org

[4] Grégoire Mialon, et.al., GraphiT: Encoding Graph Structure in Transformers, [2106.05667.pdf (arxiv.org)](https://arxiv.org/pdf/2106.05667.pdf).












