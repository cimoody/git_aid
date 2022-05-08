## install mini-forge
* https://github.com/robotology/robotology-superbuild/blob/master/doc/install-miniforge.md
* First of all, download the installer and install it in its default location:

## Download
* `curl -LO https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh`
## Install with default options
* `sh ./Miniforge3-Linux-x86_64.sh -b`
* This will install miniforge in ~/miniforge3 .

## To use the conda command, 
* add the `~/miniforge3/condabin` directory to the PATH environment variable. You can do this persistently by modifying the `.bashrc` via the command:
* `~/miniforge3/condabin/conda init`
