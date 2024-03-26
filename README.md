# Halide-Perovskites
Assessment of Empirical and Semi-Empirical van der Waals Methods for Halide Perovskites into Density Functional Theory Approach.

In this workflow, the SimStack framework is used to analyze the electronic and structural properties of metal halide perovskites (MHPs) with chemical formula CH~3~AH~3~PbI~3~(A = N, P, As, and Sb) For this, five different **WaNos** were combined: Mult-It, UnpackMol, DFT-VASP, DFT-half and DB-Generator. A table containing the total energies and structural parameters is the expected output of this protocol.

To create the workflow depicted in **Figure 1**, you must use the drag-and-drop standard procedure of Simstack in four steps. In the first, Mult-It **Wano** was used to create a tar file of all structures investigated. In the second step, we add the Unpackmol **Wano** inside AdvancedFor loop control to generate the POSCAR files corresponding to the unit cells. In the third step, we insert the DFT-VASP **Wano** to receive the POSCAR files from the preceding step and execute the DFT calculations. In this step, we need to choose the corresponding van der Waals method to be used, such as D2, D3, D3BJ, TS, TSSCS, MBD, and dDsC. At the end of the protocol, DB-Generator **WaNo** extracts in a yml file the respective total energy from the OUTCAR file associated with each composition investigated.

 ### This workflow allows us to:
```
1. From several initial structures, calculate in an automated way several of their properties, such as stability, gap energy, among others.
2. Compress all structures in the tar file above with Mult-It and uncompress them with UnpackMol.
2. Run the DFT calculations using VASP code (DFT-VASP).
4. Arrange all the total energy values gap energies for a given number of atomic substitutions in a yml file at the end of the protocol (DB-Generator). 
```

 ## Alloys workflow with **_AdvancedFor_** loop control

<img src="./Workflow.png" alt="DFT-Surface WaNo logo" width="100%"/>

**Figure 1** _This workflow aims to perform several DFT calculations of metal halide perovskites with vdW corrections. It is made from Mult-It, UnpackMol, DFT-VASP, and DB-Generator **WaNos** connected by the AdvancedFor loop control. In step 1, we generate the configurations containing different cations within the cboctahedral voids of MHP structure, represented in red. These were ; Steps 2, and 3 define the group of configurations and set the DFT calculation methods employed in the simulation. In the last step, DB-Generator **Wano** extracts the required variables of the output files from the previous steps._

## 1. Python Setup
To get this workflow up and running on your available computational resources, install the below libraries on Python 3.6 or newer.

```
1. Atomic Simulation Environment (ASE).
2. Python Materials Genomics (Pymatgen).
3. Numpy, os, sys, re, yaml, subprocess.
4. json, csv, shutil, tarfile. 
```

