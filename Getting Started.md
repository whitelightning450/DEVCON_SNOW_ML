
# Getting Started:

If using CIROH Resources, login to the 2i2c hub. Select a server option (Medium or Small) and choose Neural Networks for Snow Modeling from the dropdown list. 
    
    https://ciroh.awi.2i2c.cloud
    
The first step is to identify a folder location where you would like to work in a development environment.
We suggest a location that will be able to easily access streamflow predictions to make for easy evaluation of your model.
Using the command prompt, change your working directory to this folder and fork this repo [DEVCON_SNOW_ML](https://github.com/dliljest/DEVCON_SNOW_ML)

    git fork https://github.com/dliljest/DEVCON_SNOW_ML

Identify a folder location where you would like to work in a development environment.
We suggest a location that will be able to easily access streamflow predictions to make for easy evaluation of your model.
Change your working directory to this folder and git clone your forked repo. 

    git clone <your repo>

## Virtual Environment
It is a best practice to create a virtual environment when starting a new project, as a virtual environment essentially creates an isolated working copy of Python for a particular project. 
I.e., each environment can have its own dependencies or even its own Python versions.
Creating a Python virtual environment is useful if you need different versions of Python or packages for different projects.
Lastly, a virtual environment keeps things tidy, makes sure your main Python installation stays healthy and supports reproducible and open science.

## Creating Stable CONDA Environment
Go to home directory
```
cd ~
```
Create a envs directory
```
mkdir envs
```
Create .condarc file and link it to a text file
```
touch .condarc

ln -s .condarc condarc.txt
```
Add the below lines to the condarc.txt file
```
# .condarc
envs_dirs:
 - ~/envs
```
Restart your server

### Creating your Python Virtual Environment
Since we will be using Jupyter Notebooks for this exercise, we will use the Anaconda command prompt to create a virtual environment from the provided [environment.yml] file. 
In the command line type: 

    conda env create -f environment.yml

For this example, we will be using Python version 3.9.12, specify this version when setting up your new virtual environment.
After Anaconda finishes setting up your environment, activate it using the activate function.

    conda activate notebook 

You should now be working in your new DEVCON_env within the command prompt. 
However, we will want to work in this environment within our Jupyter Notebook and need to create a kernel to connect them.
We begin by installing the **ipykernel** python package:

    pip install --user ipykernel

With the package installed, we can connect the NSM_env to our Python Notebook

    python -m ipykernel install --user --name=notebook 

To double check you have the correct working environment, open up the [Methods](./workbook/NSM_Example/methods.ipynb) file, click the kernel tab on the top toolbar, and select "notebook" from the dropdown. 
The notebook should show up on the top right of the Jupyter Notebook.

![environment](./workbook/NSM_Example/Images/NSM-Kernel.JPG)

### Explore the model through an example

The objective of the project is to optimize a neural network for snow modeling.
To start, the next step is to explore the [NSM Example](./workbook/NSM_Example/methods.ipynb).
