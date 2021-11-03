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


### Check the Python version on Windows, Linux, or macOS systems :-
To check the version installed, open a terminal window and entering the following:
   
     python --version
![image](https://user-images.githubusercontent.com/20612971/136605964-7aa1de15-1474-4e2f-963b-c3a28c3c6cb1.png)

If installed python version is 3.5 or above then you can continue to install pyqt5 library using pip.
To install python or upgrade older python version follow next step -

### Install Python3

#### Windows
Download setup from https://www.python.org/downloads/ and follow the instruction.
#### linux/Ubuntu
If you are using Ubuntu 16.10 or newer, then you can easily install Python 3 with the following commands:

     sudo apt-get update
     sudo apt-get install python3
If you’re using another version of Ubuntu (e.g. the latest LTS release) or you want to use a more current Python, we recommend using the deadsnakes PPA to install Python 3:

    sudo apt-get install software-properties-common
    sudo add-apt-repository ppa:deadsnakes/ppa
    sudo apt-get update
    sudo apt-get install python3
If you are using other Linux distribution, chances are you already have Python 3 pre-installed as well. If not, use your distribution’s package manager. For example on Fedora, you would use dnf:

    sudo dnf install python3
   
### Download and Install pip:
#### Windows
Download the https://bootstrap.pypa.io/get-pip.py file and store it in the same directory as python is installed.
Run the command given below:
     python get-pip.py
and wait through the installation process.

#### Linux/Ubuntu
To Install PIP3(For Python 3+):

     sudo apt install python3-pip 

### Upgrading Pip version in linux
     pip install --upgrade pip


### Installing pyqt5 using pip
     pip install pyqt5 
     
To run the code use 
     python ./InfileGenerator.py
     
Developed by- Ajay Sagar
