# Generate Stochastic Kronecker Graphs
Code for generating SKGs using SNAP and calculate graph properties, in Python 2.7.11.


## Stochastic Kronecker Graph (SKGs)
SKGs are stochastic graphs generated by taking successive Kronecker powers of an initial stochastic adjacency matrix. Efficient methods exist to both 1) fit the SKG model to existing graphs, and 2) to generate new SKGs. The SKG model was introduced in [this paper](http://www.jmlr.org/papers/v11/leskovec10a.html), which demonstrated that even the simplest form of this model can produce graphs with realistic properties.


## Installation Instructions ##
This codebase generates and analyzes SKGs using the [Stanford Network Analysis Project library](https://github.com/snap-stanford/snap) (SNAP) and the [SNAP python interface](http://snap.stanford.edu/snappy/doc/). Both the SNAP library and its python interface need to be installed for these functions to work.

1. Install SNAP ([link](https://github.com/snap-stanford/snap)).  Clone that repository, then run `make all` in the root directory of wherever you cloned the repository.  
2. Install other Python dependencies by running `pip install -r requirements.txt`.  This will install NumPy, Matplotlib.
3. Install the [SNAP Python API](https://snap.stanford.edu/snappy/).  The CentOS-labeled Linux installer on that site seems to work for Ubuntu installs, too.  It seems like this install may not set `PYTHONPATH` correctly, so a quick work-around to `ImportError: No module named 'snap'` is to copy `snap.py` and `_snap.so` into the root directory of this repository.
4. Some functions take the SNAP installation directory as a parameter.  Open `config.py` and change line 15 to point to wherever you installed SNAP.


## Files
**skg_functions.py**
This file contains functions for generating and analyzing SKGs.

**example.py**
This script generates 10 SKGs, calculates some graph properties using skg_functions.py, and plots the in-degree distributions.

**convert_SKG_to_glasgow.py**
Command line utility onverts the SKG graph files to a format readable by James Trimble's [kidney_solver
](https://github.com/jamestrimble/kidney_solver) codebase. 