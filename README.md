# Graph-convolutional DNN for predicting ESP surfaces

This repository contains the code to generate [PQR files] (https://apbs-pdb2pqr.readthedocs.io/en/latest/formats/pqr.html)
for ligands and proteins that can be used to generate high quality ESP surfaces.
The PQR files records partial charge and radii in the PDB occupancy and b-factor
columns. PQR files generated by our models conatains charges on atoms as well as
off-centered charges on atomic features (e.g., lone pairs, sigma holes, p
orbitals).
For generating ligand PQR files, a graph convolutional deep neural network (DNN)
model, trained on ESP surfaces derived using high quality QM calculations, is 
used. For proteins, parametized charges for all amino acids are used, which are
fully compatible with the ligand ESP surfaces generated using the DNN model.


# How to install
To run our ESP model, you need to:
* setup Python and third-party dependencies listed below.
* Clone (and optionally install) this package.
* Install [PLI code] (https://bitbucket.org/AstexUK/pli/src/pli-snapshot/)

### Installing Python and third-party requirements:
Our package works on Python 2.7 and require following third-party packages:
* rdkit==2018.09.3
* keras==2.2.4
* tensorflow==1.10.0
* numpy==1.16.2

We recommend using [Anaconda Python distribution]
(https://www.anaconda.com/distribution/) for installing Python and the above
dependencies. Clone this repository and run the following commands:

```
conda env create -f environment.yml
source activate esp_ai
python setup.py install
```
