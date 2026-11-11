# Library Details

## Molecule Identification
Reaxys was used to curate a list of quinones with commercially available hydroquinone precursors. This curation included a molecular weight cutoff less than 500 au, identifiable on PubChem, and more than one available commercial vendor reported on PubChem.

## Conformational Searching & Conformer Selection

To capture the conformational flexibility of the substrates at a reasonable a computational cost, each quinone was subject to a gas phase molecular mechanics conformational search using CREST GFN2-xTB using GBSA implicit solvation (water).  An ensemble of conformers within 5 kcal/mol of the minimum were collected, which were then clustered to a maximum of 10 conformers per molecule. 

## DFT Computations

All DFT geometry optimizations and frequency calculations  were performed at wB97XD def2SVP (Gaussian 16, rev C.01). The corresponding geometries were used for a series of single-point energy calculations at wB97XD def2TZVP SCRF(IEFPCM,solvent=water). 

From the DFT calculations, global, atomic, and bond-level properties were collected for each conformer using [Get Properties](https://github.com/SigmanGroup/Get_Properties). 
Atomic properties were collected for the quinone oxygens and the carbon they are attached to. These atomic properties were averaged for the two carbonyls on each quinone and are referenced 'C' and 'O' in the descriptor list.

The dynamic range of properties across the conformational ensemble of a single quinone was summarized by using five condensed measures for each of the properties.

| Descriptor              | Definition                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------|
| Boltz                   | Boltzmann-weighted average of a property from all the conformers in an ensemble (T = 298.15 K)  |
| max                     | highest value of a property given by any conformer in an ensemble                               |
| min                     | lowest value of a property given by any conformer in an ensemble                                |
| low_E                   | value of a property from the lowest energy conformer in the ensemble                            |

