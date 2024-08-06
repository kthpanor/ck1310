# Software installation

Conda is an open-source package and environment management system that runs on Windows, MacOS, and Linux. The conda repository contains a large number of open-source certified packages enabling scientific work. It is recommended that you install the minimal installer for conda named miniconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib and a few others.

## Download and install miniconda

Retrieve miniconda from the following website

> <https://docs.conda.io/en/latest/miniconda.html>

Install the version for 64 bit computers.

## Create conda environment and install packages

### Step-by-step

Start a conda terminal, or Anaconda Powershell as it is referred to on a Windows system. Conda supports multiple *environments* and you start in the one named `base` as is typically indicated by the prompt. To create a new and additional environment named `myenv`, enter the following command line statement

```
conda create -n myenv
```

You can list your conda environments

```
conda env list
```

The activated environment will be marked with an asterisk (the `base` environment to begin with) and you can activate your new environment with the command

```
conda activate myenv
```

as should be indicated by getting a modified prompt.

Install packages into this environment

```
conda install numpy scipy matplotlib jupyterlab mesa -c conda-forge
```

### All in one step

Get all packages needed for course in one step with use of a YML file

```
conda env create -f cb1020.yml
```

where the file `cb1020.yml` should contain

```
name: cb1020
channels:
  - conda-forge
dependencies:
  - python
  - jupyterlab
  - jupyterlab-spellchecker
  - jupyterlab_code_formatter
  - black
  - isort
  - numpy
  - scipy
  - matplotlib
  - mesa
  - pandas
  - openpyxl
```

Some additional features are then made available in your notebooks such as a spell checker and a Python code formatter.

## Try it out

You should now be ready to start a Jupyter notebook with the command

```
jupyter-lab
```

which should open in your default web browser. A notebook allows for interactive execution of Python code written into cells.
