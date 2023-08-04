# PL-REX

**Data set of protein-ligand complexes with reliable experimental structures and affinities.**

The data set has been introduced in the following paper, please refer to it for more details and don't forget to cite it:   
[A. Pecina, J. Fanfrlík, M. Lepšík and J. Řezáč; *ChemRxiv preprint*, **2023**.](https://doi.org/10.26434/chemrxiv-2023-zh03k)

The data set is also archived at Zenodo: [![DOI](https://zenodo.org/badge/660057665.svg)](https://zenodo.org/badge/latestdoi/660057665)

## Data Set Description

The data set consists of 10 target proteins, each with a series of ligands (164 in total). Crystal structures of the P-L complex are available for the majority of the ligands (147). The PL-REX set uses a single crystal structure of the protein, carefully selected so that it can accommodate all the ligands, into which the ligand poses have been superimposed. In the resulting structures, the ligand and surrounding protein residues have been optimized, yielding the final geometry presented in the data set.

| Code       | Target                           | Ligands | Crystals | pKi range | Protein |
|------------|----------------------------------|:-------:|:--------:|:---------:|:-------:|
| 001-CA2    | Human carbonic anhydrase II      | 10      | 10       | 2.2       | 5NXG    |
| 002-HIV-PR | HIV-1 protease                   | 22      | 12       | 5.1       | 2AQU    |
| 003-CK2    | Zea mays casein kinase 2         | 16      | 16       | 1.9       | 3KXN    |
| 004-AR     | Human aldose reductase           | 14      | 14       | 2.8       | 4XZH    |
| 005-Cath-D | Human cathepsin D                | 10      | 3        | 3.5       | 6QCB    |
| 006-BACE1  | Human beta-secretase 1           | 16      | 16       | 3.6       | 5QCZ    |
| 007-JAK1   | Human Janus kinase 1             | 12      | 12       | 3.4       | 4IVD    |
| 008-Trp    | Bovine trypsin                   | 15      | 15       | 4.4       | 1K1I    |
| 009-CDK2   | Human cyclin-dependent kinase 2  | 31      | 31       | 3.6       | 3R9H    |
| 010-MMP12  | Human matrix metallopeptidase 12 | 18      | 18       | 3.9       | 3EHY    |

## Data Set Organization

The top-level numbered directories contain data for the ten protein targets.
Individual P-L complexes are identified by their PDB code (majority of the systems) or labeled as a model
(some ligands in 002-HIV-PR and 005-Cath-D that were modeled from similar structures). 

## PL-REX Structures

The structures of the optimized P-L complexes are stored in the subdirectory `structures_pl-rex` of each protein target. Each P-L complex has its own subdirectory containing:

- `ligand.sdf` - The geometry of the ligand in the optimized complex.
- `receptor.pdb` - Model of the active site used in the complex.

**These files represent the refined "PL-REX" geometry of the complexes on which the SQM2.20 score was calculated**. Additionally, the optimized active site has been ported back into the structure of the whole protein and is provided as `protein.pdb`.

## Structures from AMBER calculations

Some of the calculations reported in the paper were carried out on structures of the complexes optimized with AMBER/GAFF2 forcefield. These are available in the AMBER subdirectory of each P-L complex. There are two variants, with ligand optimized in frozen protein (`complex_lig_opt.pdb`) and with relaxed flexible region around the ligands (analogously to the PL-REX geometries, `complex_flex_opt.pdb`). In addition to the complex (the active site model with the ligand) in the PDB format, the ligand is also provided as a SDF file (`ligand_lig_opt.sdf` and `ligand_flex_opt.sdf`, respectively).

## Small Model Structures

The smaller model (to which the DFT was applied) is available in the `structures_small_model` directories. Note that the small model has been optimized independently and therefore the geometries of the P-L complexes differ from those in the larger model.

## Crystal structures

The crystal structure of the protein from which all the P-L complexes were derived, protonated and prepared for calculations, is provided as the PDB file `structures_crystal/protein_crystal_geo.pdb`. In the same directory, the initial geometries of the ligands (obtained by overalapping the crystal structures oftheir complexes, protonated, but not optimized) are provided as SDF files.

## Experimental Affinities and Scores

The experimental affinities have been converted to binding free energies and are available in the `experimental_dG.txt` files.

The SQM2.20 score computed on the PL-REX geometries is available as `score_SQM2.20.txt` for each target. The same score, and the DFT score, compute on the small model are available in the `structures_small_model` subdirectory.

Scores obtained with standard scoring functions on the PL-REX geometries are available in the `scores` subdirectory.




