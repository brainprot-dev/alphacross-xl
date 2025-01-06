# AlphaCross-XL

AlphaCross-XL is an interactive Google Colaboratory (Colab) powered IPython Notebook that helps users analyze XL-MS (Cross-Linking Mass Spectrometry) Data. The tool provides seamless mapping of cross-linked peptides onto 3D protein structures with an intuitive interface powered by ipywidgets.

## Features

* **Automated Distance Computation**: 
  - Calculate residue distances between cross-linking residues for Intra-Protein Cross-Links and Loop-links
  - Uses freely available protein structures from the AlphaFold Protein Structure Database
  - Extracts pLDDT Confidence Score for quality assessment

* **PyMOL Visualization**: 
  - Visualize cross-links in AlphaFold structures using PyMOL
  - Automatically generates individual PyMOL session files for each cross-link
  - Creates consolidated sessions showing all cross-links per protein
  - Color-coded visualization (green for non-violated, red for violated cross-links based on threshold)

* **Custom Structure Support**: 
  - Upload and analyze your own structure files (e.g., from PDB)
  - Compare distances between uploaded structures and AlphaFold structures
  - Compare AlphaFold 2 vs AlphaFold 3 structures
  - Visualize cross-links in both custom and AlphaFold structures

## Using AlphaCross-XL

### Web Version (Recommended)

1. Access AlphaCross-XL through Google Colab: [AlphaCross-XL.ipynb](https://colab.research.google.com/drive/1I5YTKvWIqrOOCGNHCOURWSop-rFbzVZ_?usp=sharing)

2. Initial Setup:
   - First-time setup takes approximately 8-10 minutes for dependency installation
   - Dependencies need to be reinstalled if the Colab session expires
   - The official version is authored by 'alphacrossxl@gmail.com'

3. Hiding Code (Optional):
   - Click 'View' in the Menu Bar
   - Select 'Hide/Show Code' to hide the implementation details

### Local Environment
You can also download the IPython Notebook given here and use your local python environment to run it. This allows you finer control over the tool and can also help you if you are modifying the tool for development/exploratory purposes.

1. (Optional, but recommended) Create a local environment
   - Use either conda/miniconda or pip to create a virtual environment
   - Virtual environments are very useful for development/local use of AlphaCross-XL
2. Use requirements.txt/environment.yaml to install AlphaCross-XL's dependencies
3. Setting up PyMOL (Open Source)
   - We use PyMOL Open Source for visualization of protein cross-links.
   - You can use package managers (apt/homebrew/e.t.c.) to install PyMOL and skip the building process which was designed with Google Colab in mind.

### Input Requirements

1. **Cross-linking Data File** (.xlsx or .csv):
   - Peptide-centric Format for Link Sites
   - One cross-link (link-site pair) per row
   - UniProt ID column
   - Peptide A and B columns
   - X-link type column (Intra-Protein and Loop Links only currently supported)
   - Link Site A and B columns in format '{R}{n}' (e.g., 'K5' for Lysine at position 5)
  
#### Note for Protein-centric Format
Currently AlphaCross-XL doesn't support protein-centric formats for link-sites out-of-box and is a WIP feature.
However you can use the FormatXLChange.ipynb notebook in this repository which can convert an input file from protein-centric to peptide-centric format.
This script also supports multiple linksites on single row (separated using a character, for .e.g. ';'
You can find an example input file which uses protein-centric format in the 'examples' subdirectory of this repository

2. **FASTA Database**:
   - Compressed FASTA database (.gz) of reviewed UniProt/SwissProt proteins
   - Must contain all proteins referenced in the data file

3. **Custom Structure Files** (Optional):
   - .zip archive containing only .cif files
   - Files must be named as {UniProtID}.cif
   - No subdirectories allowed in the archive

### Workflow

1. **Initialize and Start**:
   - Click the play button or use Ctrl+Enter (Windows/Linux) / Cmd+Enter (Mac)
   - Wait for dependency installation (first time only)

2. **Data Input**:
   - Upload data file and FASTA database
   - Verify file formats and contents

3. **Configure Analysis**:
   - Map required columns
   - Set distance threshold
   - Choose cross-link type
   - Configure visualization preferences
   - Optionally upload custom structures

4. **Review and Process**:
   - Verify all configurations
   - Start analysis (takes 5-10 minutes typically)

### Output Files

The tool generates a ZIP archive containing:

1. **Structure Files**:
   - `acxl-alphafold-structures.zip`: Downloaded AlphaFold structures
   - `acxl-uploaded_structs-data.zip`: Uploaded custom structures (if applicable)

2. **Visualization Files** (if enabled):
   - `acxl-alphafold-pymol-sessions.zip`: PyMOL sessions for AlphaFold structures
   - PyMOL sessions for uploaded structures in the uploaded structures zip

3. **Analysis Results**:
   - `*_XLMS_Distances_WO_Duplicates.csv`: Unique data entries
   - `*_XLMS_Final_Output.xlsx`: Main analysis results
   - `*_XLMS_Distances_Barplot.jpeg`: Summary bar plot
   - `*_XLMS_Distances_Histplot.jpeg`: Summary histogram

## Important Notes

- Currently supports only Intra-Protein Cross-Links and Loop-Links
- Inter-Protein Cross-Links support coming in future versions
- Session expires after prolonged inactivity
- Files over 5MB may take 10-20 seconds to upload
- Protein-centric Format Conversion is not supported yet but a script for conversion to peptide-centric format is provided

## Support and Contact

- Email: alphacrossxl@gmail.com
- For errors or issues, please contact the Development Team
- Official support only through verified alphacrossxl@gmail.com communications

## Citation

Please cite AlphaCross-XL's latest manuscript [Citation pending]
