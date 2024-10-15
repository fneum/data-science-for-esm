# Welcome

Welcome to the website accompanying the course [Data Science for Energy System Modelling](https://moseskonto.tu-berlin.de/moses/modultransfersystem/bolognamodule/beschreibung/anzeigen.html?nummer=31027&version=2&sprache=2). This course is being developed by [Dr. Fabian Neumann](https://fneum.org) and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin](https://www.tu.berlin/ensys).

On this website you will find practical introductions to many Python packages that are useful for dealing with energy data and building energy system models. Course materials other than practical introductions to Python packages for students at TU Berlin are provided on [ISIS](https://isis.tu-berlin.de/course/view.php?id=40132) (winter semeter 2024/2025).

The course covers tutorials and examples for getting started with Python, `numpy`, `matplotlib`, `pandas`, `geopandas`, `cartopy`, `rasterio`,  `pysheds`, `atlite`, `networkx`, `linopy`, `pypsa`, `plotly`, `hvplot`, and `streamlit`. Topics covered include:

- time series analysis (e.g. wind and solar production)
- tabular data (e.g. LNG terminals, power plants, industrial sites)
- geographical data (e.g. location of power plants)
- data visualisation
- converting weather data to renewable generation
- land eligibility analysis (e.g. where can we build wind turbines)
- optimisation
- electricity market modelling
- power flow modelling (linearised)
- capacity expansion planning
- sector-coupling
- interactive visualisation and dashboarding

## Installing the package manager `conda`

Python and nearly all of the software packages in the scientific python
ecosystem are [open-source](https://opensource.org/). Coordinating the
compatibility between these different packages and their multiple versions can be difficult! Fortunately, the problem is solved by using a Python
_distribution_ and/or _package manager_. You should use a package manager!

### Anaconda

The easiest way to set up a full-stack scientific Python deployment is to use a
Python distribution. This is an installation of Python with a set of curated
packages which are known to work together.

For instance, you can install on your computer the popular
[Anaconda Python Distribution](https://www.anaconda.com/download/).
Follow the link above to obtain a one-click installers for your operating system.

For **Linux and MacOS users**, you can access the command line by opening the _terminal_ program.

For **Windows users**, you should first install Anaconda (described above) or `miniconda` (described below), which gives you access to the "Anaconda Prompt" desktop application. (Instructions for this are given on the [Anaconda Website](https://docs.anaconda.com/anaconda/user-guide/getting-started/#write-a-python-program-using-anaconda-prompt-or-terminal).)

From the Anaconda Prompt, you should be able to run `conda` and other shell commands.

### Lightweight `miniconda`

If you don't want to download a large file like the Anaconda Python Distribution (ca. 800 MB), there is a
lightweight alternative installation called `miniconda`.
Follow the link to the [Miniconda Installation](https://docs.conda.io/en/latest/miniconda.html) page and use, for example, the [quick command line install](https://docs.anaconda.com/miniconda/#quick-command-line-install).

### Google Colab

You can even start the course without a local Python installation using online services like  [Google Colab (colab.google)](https://colab.google) which provide an online Python version
in a [Jupyter Notebook](jupyter.org/) environment. This requires a Google account.

## Managing environments with `conda`

Python coupled with a package manager provides a way to make isolated,
reproducible _environments_ where you have control over all installed packages
and configurations.

First, check that you have access to `conda` in your _terminal_ or _Anaconda Prompt_ application by typing:

    conda --version

Then, make sure that your conda installation is up to date:

    conda update -n base -c conda-forge conda

To create a conda environment, you execute the following command:

    conda create --name my_environment python=3.11 numpy

To use this environment, simply _activate_ it by executing:

    conda activate my_environment

You should now see the string `(my_environment)` prepended to your prompt.
Now, any execution of Python will use the packages installed in your _environment_ "my_environment".

To install additional packages into your environment:

    conda install <package-name>

Some packages are community-maintained (e.g. `conda-forge`) and require you to specify a different "channel", i.e. a different source:

    conda install -c conda-forge <package-name>

You can deactivate your environment by typing:

    conda deactivate

To see all the environments on your system:

    conda env list

To get a complete summary of all the packages installed in your environment, run

    conda list

If you want to permanently remove an environment and delete all the data
associated with it:

    conda env remove --name my_environment --all

A conda environment can also be defined through an `environment.yaml` file. With that file, a new environment with the exact
configuration can be installed by executing

    conda env create -f my_environment.yml

For extensive documentation on using environments, please see
[the conda documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/environments.html).

## Environment for this course: `esm-ws-24-25`

### ... with `conda` (recommended)

The latest environment specification for this course can be downloaded under the following link as a [`YAML`-file](https://en.wikipedia.org/wiki/YAML):

https://github.com/fneum/data-science-for-esm/blob/main/environment.yaml

There is a download button at the top-right corner.

After navigating to the folder where the `environment.yaml` file is stored ([here](https://tutorials.codebar.io/command-line/introduction/tutorial.html)'s a tutorial how to navigate with the command line),
you can reate this environment using `conda`

    conda env create -f environment.yaml

Activate this environment

    conda activate esm-ws-24-25

This environment should be sufficient for all of your work in this course.

The environment has to be activated whenever you open a new terminal,
*before* starting a new Jupyter window with

    jupyter lab

### ... with `pip`

If you want to use `pip` for managing your environment, download

https://github.com/fneum/data-science-for-esm/blob/main/requirements.txt

There is a download button at the top-right corner.

After navigating to the folder where the `requirements.txt` file is stored,
you can install the required packages with

    pip install -r requirements.txt

This should allow you to start a new Jupyter window:

    jupyter lab

## JupyterLab

[JupyterLab](https://jupyterlab.readthedocs.io) will be our primary method for
interacting with Python code. It runs in your web browser.
The following documentation pages might be worth a visit:

- [The JupyterLab Interface](https://jupyterlab.readthedocs.io/en/stable/user/interface.html)
- [Working with Files](https://jupyterlab.readthedocs.io/en/stable/user/files.html)
- [The Text Editor](https://jupyterlab.readthedocs.io/en/stable/user/file_editor.html)
- [Notebooks](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html)
- [Terminals](https://jupyterlab.readthedocs.io/en/stable/user/terminal.html)
- [Managing Kernels and Terminals](https://jupyterlab.readthedocs.io/en/stable/user/running.html)

## Markdown

Throughout the course, you might want to write rich text documents using Markdown.
This is also very common in Jupyter:

- [Markdown Guide / Basic Syntax](https://www.markdownguide.org/basic-syntax)
- [Official Markdown Documentation](https://daringfireball.net/projects/markdown/)
