# alphacross-xl
AlphaCross-XL is an interactive IPython Notebook that performs fast, seamless mapping of cross-linked peptides onto 3D protein structures. The interactivity is brought about by ipywidgets.

## Features
* Automatically compute residue distance between cross-linking residues for Intra-Protein Cross-Links and Loop-links using the freely available protein structures from the AlphaFold Protein Structure Database. Cross-linking residue's pLDDT Confidence Score is also obtained for inference.
* Option to visualize the cross-links in AlphaFold Protein Structure Database Structures using PyMOL by automatically generating PyMOL Session Files for each individual cross-link, as well as a consolidated session showcasing all cross-links in particular. Users can understand which cross-links are violated based on a user-defined threshold.
* Option to upload custom protein structures (from PDB, etc.) and compare cross-link distances between uploaded structures and AlphaFold Structures. Our tool also visualizes the cross-links for these uploaded structures! **Note**: You can also compare AlphaFold 2 v/s AlphaFold 3 Structures by uploading AlphaFold 3 Structures in this section.

## Citing
Please cite AlphaCross-XL's latest manuscript present here:

## Dependencies 
* Pyfastx - FASTA Database Processing
* ProDy - Cross-linking Residue Distance Computation, pLDDT Extraction
* PyMOL (Open Source)
* Pandas - Data Manipulation
* Matplotlib - Plot Generation
* Seaborn - Plot Generation

## Using AlphaCross-XL
### Web Version (through Google Colab) **(Recommended)**
For ease of use, AlphaCross-XL is available as a web version, thanks to Google Colaboratory (or Colab). This version can be found here: [tinyurl.com/alphacross-xl-v1](https://tinyurl.com/alphacross-xl-v1). Do note that Google Colab's usage policy applies to this version:
* AlphaCross-XL will need to be **re-installed**, every time the Google Colab's Remote Instance Expires.
### Local Versions
Alternatively, you can run AlphaCross-XL on your computer by using it as a Jupyter Notebook or a stand-alone script. The Jupyter Notebook version is already available. Stand-alone Script will be soon available.

## Contributing to AlphaCross-XL
We are open to contributions. If you are willing to contribute, we request you to send us an e-mail at alphacrossxl@gmail.com
