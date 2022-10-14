# Introduction to scientific Python

* Introduction [slides](https://docs.google.com/presentation/d/1z4lad4-pvLIN9mDlBzrgP8ECNHYgkXbr0ZcQrcx7Uu4/edit?usp=sharing) 
* To follow the tutorial without Python installed: [![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://lorenzocerrone.github.io/intro-to-scientific-python)

## Installing Python using anaconda
For all OS, you can download the anaconda installer from [anaconda](https://www.anaconda.com/products/individual).
But, to reduce the installation size (and avoid bloatware), we suggest using Miniconda.
### Installation on Linux (Mac)
To download Miniconda open a terminal and type
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
Then install by typing:
```bash
bash ./Miniconda3-latest-Linux-x86_64.sh
```
Follow the instructions to complete the anaconda installation. 
The `Miniconda3-latest-Linux-x86_64.sh` file can be safely deleted.

### Installation on Windows
Miniconda can be downloaded from [miniconda](https://docs.conda.io/en/latest/miniconda.html). Download the 
executable `.exe` for your Windows version and follow the installation instructions.

### Check your installation
On Linux (Mac), source your `.bashrc` (or  open and close the terminal), and on Windows, open the `Conda Prompt` from 
the applications. 
Then type:
```bash
which Python
```

### Create a new environment
```bash
conda create -n tutorial-env -c conda-forge python=3.10 numpy scipy matplotlib
```
Where:
- `-n tutorial-env`: is just the name that we want to give to your environment
- `-c conda-forge`: this is the `repository` from where we are going to source our packages
- `python=3.10 nu...`: the list of packages you want to have in your environment

Then activate the environment:
```bash
conda activate tutorial-env
```

### Install additional packages
To install additional packages, execute the following:
```bash
conda intall -c conda-forge notebook
```
#### Some Tips: 
- Avoid (only if you can) installing packages one by one like:
```bash
conda intall -c conda-forge notebook
conda intall -c conda-forge numpy
conda intall -c conda-forge scipy
conda intall -c conda-forge matplotlib
```
but install them in bulk 
```bash
conda intall -c conda-forge numpy scipy matplotlib notebook
```
- If you need to install something with `pip`, do it at the end
```bash
conda intall -c conda-forge numpy scipy matplotlib
pip install notebook
```

- If you try to install something on an environment that has been modified many times, and anaconda struggles to 
install the package. Then recreate the environment from scratch, including all the new packages. 
- If you find conda slow, then install [mamba](https://github.com/mamba-org/mamba) is like conda (same commands and syntax) but much faster. 

## Advanced usage
- `conda deactivate`: Deactivate the current environment and set it back to `base`
- `conda info --envs`: List all existing environments  
- `conda list`: Returns a list of all packages installed in the current environment 
  
For a more in-depth usage guide, check the official [documentation](https://docs.conda.io/projects/conda/en/latest/commands.html).
