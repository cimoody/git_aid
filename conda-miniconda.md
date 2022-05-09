## install mini-conda
* https://github.com/robotology/robotology-superbuild/blob/master/doc/install-miniforge.md & https://docs.conda.io/en/latest/miniconda.html#linux-installers
* First of all, download the installer and install it in its default location:

## Download
* `curl -LO https://repo.anaconda.com/miniconda/Miniconda3-py39_4.11.0-Linux-x86_64.sh`
## Install with default options
* `sh ./Miniconda3-py39_4.11.0-Linux-x86_64.sh -b`
* This will install miniforge in  ~/miniconda3/ .

## To use the conda command, 
* add the `~/miniconda3/condabin` directory to the PATH environment variable. You can do this persistently by modifying the `.bashrc` via the command:
* `~/miniconda3/condabin/conda init`
