# Welcome

Welcome to the website accompanying the course [Data Science for Energy System Modelling](https://moseskonto.tu-berlin.de/moses/modultransfersystem/bolognamodule/beschreibung/anzeigen.html?nummer=31027&version=2&sprache=2). This course is being developed by [Dr. Fabian Neumann](https://fneum.org) and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin](https://www.tu.berlin/ensys).

On this website you will find practical introductions to many Python packages that are useful for dealing with energy data and building energy system models. Course materials other than practical introductions to Python packages for students at TU Berlin are provided on [ISIS](https://isis.tu-berlin.de/course/view.php?id=44803) (winter semeter 2025/2026).

The course covers tutorials and examples for getting started with Python, `numpy`, `matplotlib`, `pandas`, `geopandas`, `cartopy`, `rasterio`,  `pysheds`, `atlite`, `networkx`, `linopy`, `pypsa`, `plotly`, `hvplot`, and `streamlit`. Topics covered include:

- time series analysis (e.g., demand, wind and solar production)
- tabular data (e.g., power plants, industrial sites, LNG terminals)
- geographical data (e.g., power plants, industrial sites, LNG terminals)
- data visualisation (e.g., static and interactive plots, maps, dashboards)
- converting weather data to renewable generation availability
- land eligibility analysis (e.g., where can we build wind turbines or solar parks)
- optimisation (e.g. linear programming and using solvers)
- electricity market modelling (e.g., how dispatch is determined and prices form)
- power flow modelling (e.g., how electricity can cause grid congestion)
- capacity expansion planning (e.g., where to build new generation, storage, and transmission)
- sector-coupling (e.g., hydrogen, heat pumps, electric vehicles)

## Quickstart with Google Colab

You can begin with the course without a local Python installation using online
services like  [Google Colab (colab.google)](https://colab.google) which provide
an online Python version in a [Jupyter Notebook](jupyter.org/) environment. This
requires a Google account.

Navigate to the other pages. You will find a rocket-shaped button at the top of
each page that says "Open in Colab". Click this button to open the page in
Google Colab.

## Getting the Code

To get the code and material for this course, you can **download** the full GitHub
repository or parts of it.  There are several ways to do this:

### Individual File Download (beginner friendly):

You can download individual files directly from website by clicking on the
download button at the top-right corner of each page.

:::{note}
This method is suitable if you want to start step by step and want to update them selectively once in a while.
:::

### ZIP Option (easy, but static):

Download the ZIP file from GitHub and extract it to your computer in a directory
of your choice.

:::{warning}
This method does not allow you to easily update the course materials later on. You will need to re-download the ZIP file and re-extract it to get the latest
updates.
::::

### Git Option (more advanced):

Git is a version control system that allows you to manage and track changes to
your code. If you don't have Git installed, you can install it from
[git-scm.com](https://git-scm.com/install/). Once installed, you can
**navigate** to a directory where you want to store the course materials and
**clone** the repository using Git. Cloning means you create a local copy of the
repository on your computer. It can be done by running the following commands:

```sh
# navigate to your desired directory
cd path/to/your/directory

# clone the repository
git clone https://github.com/fneum/data-science-for-esm.git

# enter the cloned repository
cd data-science-for-esm

# update the repository to get the latest changes
git pull
```

The `#` symbol indicates comments and should not be typed.


:::{note}
What is **navigation** in the command line and how to do it?

The command line (also known as terminal, shell, or console) is a text-based
interface that allows you to interact with your computer's operating system by
typing commands. To navigate the file system using the command line, you use
commands to change directories and list files. The following are some basic
commands:

- `cd my_directory`: Change directory to `my_directory`
- `cd ..`: Move up one directory
- `ls` (Linux/Mac) or `dir` (Windows): List files and directories in the current directory
- `mkdir my_new_directory`: Create a new directory named `my_new_directory`

Paths (i.e., the directions to where files and directories are stored) can be **absolute** (e.g., `C:\Users\YourName\Documents` on Windows or `/home/yourname/documents` on Linux/Mac) or **relative** to the current directory.

On Windows, you use backslashes `\` to separate directories in paths, while on
Linux and MacOS, you use forward slashes `/`.

For a more detailed introduction to using the command line, see [this tutorial](https://tutorials.codebar.io/command-line/introduction/tutorial.html).
:::


## Recommended Setup with `conda`

### Installing `conda`

Python and nearly all of the software packages in the scientific python
ecosystem are [open-source](https://opensource.org/). Coordinating the
compatibility between these different packages and their multiple versions can
be difficult! Fortunately, the problem is solved by using **package managers**.

The easiest way to set up a full-stack scientific Python deployment without
prior experience is to use a Python distribution, such as
[Anaconda](https://www.anaconda.com). The instructions differ for Windows, MacOS, and Linux. Closely, follow the instructions (and videos) at

https://www.anaconda.com/docs/getting-started/getting-started

Watch the introduction videos and follow the instructions there.

:::{note}
For beginners, the Anaconda Python Distribution is recommended. If you are comfortable with using the command line, you can also use the lightweight `miniconda` installation.
:::

Once Anaconda is installed, you can access `conda` in the command line using the *Anaconda Prompt* application on Windows, or the terminal application on Linux and MacOS.

### Installing `conda` environments

Python coupled with a package manager like `conda` provides a way to make
isolated, reproducible **environments** where you have control over all
installed packages and configurations. To work through the course materials, you
need to install a specific set of packages within such a dedicated `conda`
environment.

#### Downloading specification files

Among several other ways to do this, this can be done by creating a new
environment from a provided `environment.yaml` file. This file lists all
required packages and their versions in the [`YAML`
format](https://en.wikipedia.org/wiki/YAML). These files can list exact package
versions (**pinned** versions) or just version constraints (e.g., minimum
versions).

In this course, we provide pinned versions to ensure everyone has the same
environment, but they depend on the operating system you are using.

- For **Windows**, use the [`win-64.lock.yaml`](https://github.com/fneum/data-science-for-esm/blob/main/envs/win-64.lock.yaml) file.
- For **MacOS (Intel/AMD)**, use the [`osx-64.lock.yaml`](https://github.com/fneum/data-science-for-esm/blob/main/envs/osx-64.lock.yaml) file.
- For **MacOS (Apple Silicon)**, use the [`osx-arm64.lock.yaml`](https://github.com/fneum/data-science-for-esm/blob/main/envs/osx-arm64.lock.yaml) file.
- For **Linux**, use the [`linux-64.lock.yaml`](https://github.com/fneum/data-science-for-esm/blob/main/envs/linux-64.lock.yaml) file.

**There is a download button at the top-right corner.**

:::{note}
If there are problems with the pinned versions, you can also try using the
unpinned
[`environment.yaml`](https://github.com/fneum/data-science-for-esm/blob/main/envs/environment.yaml)
file.
:::


#### Option 1: Anaconda user interface

1. Open the Anaconda Navigator application
2. Go to the "Environments" tab on the left
3. Click "Import" at the bottom
4. In the dialog, provide a name for the new environment (e.g. `esm-ws-25-26`) and select the downloaded `environment.yaml` file
5. Click "Import" to create the environment and install all required packages

:::{note}
This process may take some time, depending on your internet connection and computer speed.
:::

#### Option 2: Command line

First, check that you have access to `conda` in your terminal (or Anaconda Prompt on Windows) by typing:

```sh
conda --version
```

For **Windows**:

```sh
conda env create -f envs/win-64.lock.yaml
```

For **MacOS** (Intel/AMD):

```sh
conda env create -f envs/osx-64.lock.yaml
```

For **MacOS** (Apple Silicon):

```sh
conda env create -f envs/osx-arm64.lock.yaml
```

For **Linux**:

```sh
conda env create -f envs/linux-64.lock.yaml
```

:::{note}
This process may take some time, depending on your internet connection and computer speed. If you encounter issues that the environment could not be solved, try using the
:::


### Using `conda` environments

To use the course environment, it must be **activated** by executing in the terminal (or Anaconda Prompt on Windows):

```sh
conda activate esm-ws-25-26
```

This can be done anywhere; you do not need to be in the course repository folder.

You should now see the string `(esm-ws-25-26)` prepended to your prompt.

Now, any execution of Python will use the packages installed in your
environment `esm-ws-25-26`.

:::{warning}
The activation step has to be repeated whenever you open a new terminal; it is not persistent across terminal sessions.
:::

To install additional packages into your environment, such as `pandas`, you can use:

```sh
conda install pandas
```

Sometimes you may want to install specific versions of packages. For example, to install version `2.1.0` of `pandas`, you can use:

```sh
conda install "pandas=2.1.0"
```

You can deactivate your environment again by running (you will rarely need to do this):

```sh
conda deactivate
```

To see all the environments on your system:

```sh
conda env list
```

To get a complete summary of all the packages installed in your *activated* environment, run

```sh
conda list
```

If you want to permanently remove an environment, run:

```sh
conda env remove -n esm-ws-25-26
```

### Running Jupyter Lab

With the environment activated, you can start [Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/), a web-based interactive development environment, by typing:

```sh
jupyter lab
```

This should open a new tab in your web browser with the Jupyter Lab interface.

## Alternative Setup Options


### Using `pip`

:::{warning}
Some geographical packages used in this course (e.g., `rasterio`, `geopandas`, `cartopy`) may require additional system dependencies that are not handled by `pip`. Unlike with `conda`, you may need to install these dependencies manually, e.g. "GDAL".
**Only use this method if you are experienced with package management!**
:::

For using `pip` as package manager, first ensure you have a working Python installation (version 3.13 is recommended). You can download Python from [python.org](https://www.python.org/downloads/) for your operating system.

Once Python is installed, you can open the command prompt / terminal and verify the installation by typing:

```sh
python --version
python -m pip --version
# or
pip --version
```

Now, you can upgrade `pip` to the latest version by running:

```sh
pip install --upgrade pip
```

Similar to the `conda` environment setup, you can install all required packages using a `requirements.txt` file. This is the same for all operating systems.

For our course, you can find it
[here](https://github.com/fneum/data-science-for-esm/blob/main/requirements.txt).
There is a download button at the top-right corner.

After navigating to the folder where the `requirements.txt` file is stored (i.e. using `cd path/to/your/directory`), you can install the required packages with

```sh
pip install -r requirements.txt
```

You can add more packages later using `pip install package_name`, e.g.

```sh
pip install pandas
```

Once this is done, you can start a new Jupyter Lab session in your browser:

```sh
jupyter lab
```

Unlike with `conda`, `pip` does not provide isolated environments by default.

### Using `uv`

:::{warning}
Some geographical packages used in this course (e.g., `rasterio`, `geopandas`, `cartopy`) may require additional system dependencies that are not handled by `pip`.
Unlike with `conda`, you may need to install these dependencies manually, e.g. "GDAL".
**Only use this method if you are experienced with package management!**
:::

For using `uv` as package manager, first follow the [installation instructions](https://docs.astral.sh/uv/getting-started/installation/). These differ depending on your operating system.

Once `uv` is installed, navigate to your local copy of the course repository and verify that it's working:

```sh
uv --version
```

Now, install all required packages and set up the environment by running:

```sh
uv sync
```

It is important that you run this command in the root folder of the course repository, where the `pyproject.toml` and `uv.lock` files are located.

You can also add more packages later using `uv pip install package_name`, e.g.

```sh
uv pip install pandas
```

Once this is done, you can start a new Jupyter Lab session in your browser with this environment by running:

```sh
uv run jupyter lab
```

### VS Code

An alternative to using **Jupyter Lab** is to use [Visual Studio Code (VS
Code)](https://code.visualstudio.com/) as your development environment. You
still need to manage your Python installation and packages using either `conda`,
`pip`, or `uv` as described above.

To work with Jupyter Notebooks in VS Code, you need to install the [Jupyter
extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter).
You can install it directly from the Extensions view in VS Code by searching for
"Jupyter" and clicking "Install". You also need to install the [Python
extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python).

Now, whenever you open a Jupyter Notebook file (`.ipynb`), VS Code will
automatically provide you with an interactive interface to run and edit your
notebooks. To link the notebook to the correct Python environment, click on the
**kernel** name in the top-right corner of the notebook interface and select the
appropriate environment (i.e., `esm-ws-25-26`).

This setup is a lot more powerful than Jupyter Lab alone, as it provides many
additional features such as code completion and AI-assisted coding.


### Github Codespaces

Github Codespaces provides a cloud-based development environment that can be
configured to run all code examples for this course. It is an alternative to
Google Colab (described above) or local development on your computer. A Github
account is required. To use it, simply click the button below to create your own
copy of the course repository on Github.

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/fneum/data-science-for-esm)

This will create a fork of the repository in your own Github account; the link
will look like this: `https://github.com/YOUR_USERNAME/data-science-for-esm`.

Then, click on the green "Code" button and select "Open with Codespaces" and "New codespace".
This will create a new Codespace for you. It may take a few minutes to set up the environment for the first time. You get an online VS Code environment with all required packages installed.

If you want to sync your forked repository with the original repository
without using the command line, you can use the "Sync fork" button in your
forked repository on Github.

:::{note}
The free runtime for Github Codespaces is limited to 120 hours per month per user. There is a Github Software Student Pack that provides 60 additional free hours for students. See https://education.github.com/pack for more information.
:::

:::{warning}
Github Codespaces sessions will time out after a period of inactivity. Unsaved work may be lost. Make sure to frequently save your work.
:::
