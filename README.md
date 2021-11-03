# MicroSim LAB


## Grand-Potential Model 


## Cahn–Hilliard Model
 * C code for precipitate evolution. 
 * It solves Allen-Cahn and Cahn–Hilliard equations using FFTW3.  
 * Compile the code using "make". Compilation creates "FFT_2D_ppt.out" file. 
 * Execute "./FFT_2D_ppt Input.in Filling.in output" 

 * Authors: Dasari Mohan and M P Gururajan

 * This is alpha version of the code and check for updates in future release. 

 * Copyright (c) 2021 Materials and Process Modelling Laboratory,
 * Department of Metallurgical Engineering and Materials Science, 
 * Indian Institute of Technology Bombay, Mumbai 400076 INDIA

## KKS GPU CUDA Model
This code solves the problem of precipitate growth using a multiphase field solver on the GPU.
The code is tested on Tesla P100 and Tesla V100.
For Tesla K80, one needs to comment "CudaMemPrefetchAsync" in solverloop/evolve.h

To run the code use 
1. "make" to create executable kks.out
2. Execute "./kks.out Input.in Filling.in Output"

The code uses CUDA version 11, CUFFT and CUDA-CUB libraries. 
nvcc version 11.2 is used for compilation of the codes.
Input.in contains all numerical and physical parameters used in the simulations. 
Makefile creates a  DATA folder where the datafiles (in the form of VTK files) are stored.
VTK files can be viewed using Paraview.

This is the alpha version of code. We will continue to add more features in future release.


- GPU Phase-Field Developer Team @ IITH
(Pankaj, Saurav Shenoy, Saswata Bhattacharya)

The following contributers are acknowledged
1. Tushar Jogi
2. Hemanth Kumar Sandireddy

## KKS GPU OPENCL Model

* OpenCL code for solidification microstructure evolution 

* Compile the code using "make". Compilation creates "kim_soldfn.out" file. 
* GEdata_writer.py is used for generation of Gibbs energy and its derivatives
* To generate Gibbs energies and execute the program
* run "./kimsldfn.sh  Input.in Filling.in Output"
* It is always safe to run above command for execution of the code.

* If Gibbs energies are generated already then generating 
* Gibbs energies can be skipped and directly execute following command.
* Execute "./kim_soldfn.out Input.in Filling.in Output" 

* Authors: Dasari Mohan and G Phanikumar
* Acknowledgement to P. Gerald Tennyson for contributions towards code development at IITM

* This is alpha version of the code and check for updates in future release. 

## MultiPhysics Solver
This repository is a fork of Phase-Field-DynamicMeshing. The addition primarily is the documentations. The description of each directories are given below:

### codeGuide

It contains the Doxygen configuration file, generated HTML and LaTeX documentation files from the source codes. To access HTML documentation, open html/index.html. To access LaTeX generated PDF documentation, open pdflatex/refman.pdf.

### phaseFieldSolverDynamic

It contains the source files of the solver.

### userGuide

It contains the R Markdown files for creating the HTML (userGuide.html) and PDF (userGuide.pdf) documentations of the OpenFOAM cases.

### freeGrowth

It contains the OpenFOAM case files required to run the free growth problem.

### directionalSolidification

It contains the OpenFOAM case files required to run the directional solidification problem.


## Infile Generator
Python GUI application for generating Infile and Filling files.

### System Requirements :-
   1) Python v3.5 and later 
   2) pyqt5 Library


### check the Python version on Windows, Linux, or macOS systems :-
To check the version installed, open a terminal window and entering the following:
   
     python --version
![image](https://user-images.githubusercontent.com/20612971/136605964-7aa1de15-1474-4e2f-963b-c3a28c3c6cb1.png)

If installed python version is 3.5 or above then you can continue to install pyqt5 library using pip 
