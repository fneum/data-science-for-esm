# Welcome

Welcome to the website accompanying the course [Data Science for Energy System Modelling](https://moseskonto.tu-berlin.de/moses/modultransfersystem/bolognamodule/beschreibung/anzeigen.html;jsessionid=DQfixqzzpn1XIg5N1GG7S9um4EDykZn99AHmH6Fj.moseskonto?number=31027&version=1&sprache=2). This course is being developed by [Dr. Fabian Neumann](https://neumann.fyi) and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin](https://www.tu.berlin/ensys).

On this website you will find practical introductions to many Python packages that are useful for dealing with energy data and building energy system models. Course materials other than practical introductions to Python packages can be found on [ISIS](https://isis.tu-berlin.de/course/view.php?id=30525).

## Python

:::{note}
This section is adapted from the following resource:
- https://earth-env-data-science.github.io/lectures/environment/python_environments.html
:::

Python and nearly all of the software packages in the scientific python
ecosystem are [open-source](https://opensource.org/). Coordinating the compatibility between these different packages and their
multiple versions used to be a nightmare! Fortunately, the problem is solved by using a Python _distribution_ and/or _package manager_.

One important rule about data science in Python is:

**Do not use your system Python installation, but a dedicated package manager!**

## Easy Installation Method: Use Anaconda Python

The easiest way to set up a full-stack scientific Python deployment is to use a
Python distribution. This is an installation of Python with a set of curated
packages which are guaranteed to work together.

For instance, you can install on your computer the popular
[Anaconda Python Distribution](https://www.anaconda.com/download/).
Follow the link above to obtain a one-click installers for your operating system.

## Accessing the Command Line

For **Linux and MacOS users**, you can access the command line by opening the _terminal_ program.

For **Windows users**, you should first install Anaconda (described above) or Miniconda (described below), which gives you access to the "Anaconda Prompt" desktop application. (Instructions for this are given on the [Anaconda Website](https://docs.anaconda.com/anaconda/user-guide/getting-started/#write-a-python-program-using-anaconda-prompt-or-terminal).)

From the Anaconda Prompt, you should be able to run `conda` and other shell commands.

## Lightweight Alternatives: Micromamba and Miniconda

If you don't want to download a large file like the Anaconda Python Distribution (ca. 800 MB), there are
lightweight alternative installation methods (like `micromamba` and `miniconda`, but they are a bit more complicated.

1. [Micromamba Installation](https://mamba.readthedocs.io/en/latest/installation.html#micromamba)
2. [Miniconda Installation](https://docs.conda.io/en/latest/miniconda.html)

## Managing Environments with `conda`

Python coupled with a package manager provides a way to make isolated,
reproducible *environments* where you have fine-tuned control over all packages
and configuration.

To create a conda environment, you execute the following command:

    $ conda create --name my_environment python=3.10 numpy

To use this environment, simply "activate" it by executing:

    $ conda activate my_environment

You should now see the string `(my_environment)` prepended to your prompt.
Now, if you execute any Python-related tool from the
command line, it will first search in your environment.

To install additional packages into your environment:

    $ conda install <package-name>
    
Some packages are community-maintained (e.g. `conda-forge`) and require you to specify a different "channel":

    $ conda install -c conda-forge <package-name>

You can deactivate your environment by typing:

    $ conda deactivate

To see all the environments on your system:

    $ conda info --envs
    
To get a complete summary of all the packages installed in your environment, run

    $ conda list

If you want to permanently remove an environment and delete all the data
associated with it:

    $ conda env remove --name my_environment --all

A conda environment can also be defined through an `environment.yaml` file. With that file, a new environment with the exact
configuration can be installed by executing

    $ conda env create -f my_environment.yml

Below we will see an example of an environment file.

For extensive documentation on using environments, please see
[the conda documentation](https://conda.io/docs/using/envs.html).

## Speeding things up with Mamba

In order to put together an actual python environment from your package specifications,
conda has to solve a difficult puzzle, to ensure that the combination of packages is mutually compatible.
Each package specified has certain dependencies on other packages.
Moreover, each version of one package requires certain minimum versions of other
packages.
Other packages in your environment may have different or incompatible versions.
The default implementation of `conda` can be very slow.
Fortunately, there is a much faster alternative called [mamba](https://mamba.readthedocs.io/en/latest/index.html).
To install it, just run:

    conda install -n base -c conda-forge mamba

Now you can install environments and packages as before, but using the `mamba` command
instead of `conda`. Everything will be faster.

## Data Science for Energy System Modelling Python Environment

The latest environment specification for this course lives at <https://raw.githubusercontent.com/fneum/data-science-for-esm/main/environment.yaml>.

Copy and paste the following `environment.yml` file somewhere on your local hard drive:

    name: esm
    channels:
    - conda-forge
    dependencies:
    - python==3.10
    - pip

      # main packages
    - numpy
    - scipy
    - pandas
    - geopandas
    - xarray
    - networkx
    - yaml
    - pyomo
    - netcdf4
    - pypsa>=0.22
    - atlite>=0.2.9
    - powerplantmatching>=0.5.5
    - rasterio!=1.2.10

      # interactive python
    - ipython
    - jupyterlab

      # reading excel tables
    - tabula-py
    - xlrd
    - lxml
    - pytables
    - pyxlsb
    - openpyxl

      # geodata utilities
    - fiona
    - shapely<2.0
    - proj
    - geopy
    - pyepsg
    - cartopy
    - descartes

      # plotting
    - matplotlib
    - seaborn
    - plotly
    - hvplot
    - holoviews
    - geoviews
    - graphviz
    - contextily
    - streamlit

      # publishing
    - jupyter-book
    - ghp-import


Create this environment using mamba

    $ mamba env create -f environment.yml

Activate this environment

    $ conda activate esm

This environment should be sufficient for all of your work in this class.

# What the heck is JupyterLab?

[JupyterLab](https://jupyterlab.readthedocs.io) will be our primary method for
interacting with the computer. JupyterLab contains a complete environment for
interactive data science which runs in your web browser.

JupyterLab has excellent documentation. Rather than repeat that documentation
here, we point you to their docs. The following pages are particularly relevant:

- [The JupyterLab Interface](https://jupyterlab.readthedocs.io/en/stable/user/interface.html)
- [Working with Files](https://jupyterlab.readthedocs.io/en/stable/user/files.html)
- [The Text Editor](https://jupyterlab.readthedocs.io/en/stable/user/file_editor.html)
- [Notebooks](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html)
- [Terminals](https://jupyterlab.readthedocs.io/en/stable/user/terminal.html)
- [Managing Kernels and Terminals](https://jupyterlab.readthedocs.io/en/stable/user/running.html)

## Markdown Syntax

Throughout the course, you might want to write rich text documents using Markdown.
This is also very common in Jupyter Notebooks.
Here are some useful references on Markdown syntax.

- [Markdown Guide / Basic Syntax](https://www.markdownguide.org/basic-syntax)
- [Official Markdown Documentation](https://daringfireball.net/projects/markdown/)