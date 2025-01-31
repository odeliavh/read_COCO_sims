# read_COCO_sims
This is a beginners guide to reading the snapshot and subhalo files of the COCO simulations. Starting by getting set up on Cosma to perform the project. 


## Introduction

This module provides a step by step process to read the snapshots and subfind catalogs for the COCO simulations. This requires using virgo.formats.gadget_snapshot and virgo.formats.subfind_gadget4 

## Environment set up on COSMA and Installation
Open up terminal on your computer and type in command to open up jupyter notebook on cosma:
ssh -N -L 8443:login8b.cosma.dur.ac.uk:443 USER@login8b.cosma.dur.ac.uk
Then go to https://localhost:8443
Then go to File → New → Terminal

To properly set up the environment, closely Follow the instructions on 
https://cosma.readthedocs.io/en/latest/jupyter.html#adding-a-venv-to-jupyter

when installing packages refer to https://cosma.readthedocs.io/en/latest/python.html

```
pip install pytest-mpi
```

```
pip install virgodc
```

```
module load gnu_comp/14.1.0 openmpi
pip install /cosma/local/python-wheels/3.12.4/openmpi-5.0.3-hdf5-1.12.3/mpi4py-3.1.6-cp312-cp312-linux_x86_64.whl
```

```
pip install /cosma/local/python-wheels/3.12.4/openmpi-5.0.3-hdf5-1.12.3/h5py-3.11.0-cp312-cp312-linux_x86_64.whl
```

## Set up paths
On cosma in your home directory.. Create a folder where you want the put your code. 
To upload the code from home computer to cosma use scp command.

scp /Users/mycomputer/path_to_files/* USER@login8b.cosma.dur.ac.uk:/cosma/home/proj/USER/project_code_directory


## Module setup

readers_COCO.py ~ uses virgo.formats.gadget_snapshot and virgo.formats.subfind_gadget4 to opens all files for a given COCO snapshot.
subflag.py ~ used to identify particles of various subhalos.
read_data.py ~ uses readers_COCO.py to extract specfic parameters desired. This function should be modified to return desired parameters. 
Test_Main.ipynb ~ Notebook which assigns variables to the output parameter of the function in read_data.py

