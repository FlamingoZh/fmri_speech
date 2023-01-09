# Speech Model Tutorial

In this tutorial you will step through a voxel-wise modeling analysis. You will use computational models to extract semantic features from a natural speech stimulus. Then these features will be used to build linear models of fMRI data, and model weights and prediction performance will be visualized.

# Getting Started

## Downloading Git repo to your local computer

The very first thing to start with is to download this Git repository to your local computer. The easiest way is to click the green `Code` button at the top right of the repo, select `Download ZIP`, and unzip it. Alternatively, you can use
```bash
git clone git@github.com:FlamingoZh/fmri_speech.git
```
to download the repo if you have git installed on your computer, but that is an advanced skill and we don't require you to do that.

## Downloading fMRI data

You also need to download the fMRI data from [this link](https://utexas.box.com/shared/static/4n3lemyec0wlj5rcr80991nxwflsbks9.zip), unzip it, and put the unzipped `data/` folder under the git repo you just downloaded. The fMRI data is around 1.2GB so please make sure you have enough disk space.

### Acknowledgements

The fMRI data used in this tutorial was collected by Alex Huth and Wendy de Heer at the University of California, Berkeley.

## Using Conda to manage Python packages

Conda is an open source package and environment management system that allows you to create multiple standalone Python envrionments on your computer and automatically resolves package dependencies. We recommend installing Miniconda, a mini version of Anaconda that includes only conda, Python, and a small number of essential packages. If you already have Anaconda installed on your computer, there is no need to install Miniconda.

You can find Miniconda installers from [this page](https://docs.conda.io/en/latest/miniconda.html#installing). If you use Windows, just double-click the downloaded `.exe` file and use default settings. For installation on MacOS or Linux, you can refer to instructions for [MacOS](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html) and [Linux](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html). Feel free to drop an email to Yuchen Zhou (zhouyuchen@cmu.edu) if you have any questions.

For Windows, you'll find `Anaconda Prompt` in your Start menu to lanch conda (be careful, it's different from powershell or WSL). For MacOS and Linux, type ``conda info`` in your terminal to verify your installation. You should also see something like `(base) username ~ %` in your Anaconda prompt or terminal, which means now you are in the base envionment.

Then let's create a new environment and install some packages (in case you are interested, you can find some frequently used commands in this [conda cheat sheet](https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf)):

```bash
conda create -n fmri_speech python=3.8   # create a new environment named fmri_speech
conda activate fmri_speech   # activate the environment
conda install numpy scipy matplotlib jupyterlab pytables   # install some Python packages
pip install pycortex   # install pycortex using pip (because it is not available in conda)
```
Again, feel free to drop an email to Yuchen Zhou (zhouyuchen@cmu.edu) if you encounter any problems.

## Launching Jupyter Lab to start exploring the code

Now everything is set. Make sure you have activated the conda environment (you should see something like `(fmri_speech) username ~ %` in your Anaconda prompt or terminal, if not, enter ``conda activate fmri_speech``), then use ``cd`` command to navigate to the downloaded git repo, and run 

```bash
jupyter lab
```

This command should direct you to a new window in the browser, where you can open `SpeechModelTutorial.ipynb` from the Jupyter file browser on the left.