This readme is organized into two parts: 
1. An overview for setting up the system on your computer 
2. A quick tour of the code showing how the verification of Dijkstra's algorithm matches that described in the paper

A word of warning at the offset: building this system can be a lengthy and breaky process, depending on individual computer specifications and resources allocated to the task. If readers are interested in building upon this work in a serious way, we would be happy to provide them with a precompiled Docker file.

## Overview
This repository simply contains VST (commit cb633f) and the latest version of RamifyCoq thrown together as sibling directories. Having these directories as siblings with these names is not essential, but it simplifies things ever so slightly and allows a one-command build.


#### Coq Version
This code has been tested with Coq version 8.9.1


#### Download
Download this repository as a .zip and unpack it.


#### Build (lengthy step)
Change to the RamifyCoq folder (`cd RamifyCoq/`) and then run either  `make vstdijk7`  or  `make vstdijk3`, depending on whether you would like to dedicate 7 or 3 cores to this task. This command just hops to the VST folder, builds a minimal portion of VST that our work depends on, and then comes back and builds verif_dijkstra.vo along with its dependencies. 

You will see two warnings at the very top, but these can be safely ignored. The rest of the script will be a series of  “COQC filename” commands. You will see three ignorable warnings from VST when building the file “veric/mpred.v”.


## Quick Tour
We point out examine some of the items discussed in the paper. The hyperlinks that follow lead back into this GitHub repository.

1. The C code for Dijkstra's algorithm is [here](www.example.com). 
2. We use VST's clightgen tool to convert this into a Coq-readable AST. That .v file is [here](www.example.com). 
3. The spatial representation of the graph comes together [here](www.example.com). 
4. The Coq verification of the algorithm is [here](www.example.com). Note how dijkstra_correct, the correctness condition and while loop invariant, is defined [here](www.example.com). Just above it are the definitions of inv_popped, inv_unpopped, and inv_unseen, as dicussed in the paper.