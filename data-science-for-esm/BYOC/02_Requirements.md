Requirements
=============
For a successful workflow run, the [correct python environment][venv], with all of the [python package dependencies][dependencies] included, is required[^1].

Our suggestion is adopt the package manager `mamba` (or `conda`), which for installation instructions are provided in the [Miniforge GitHub repository][mamba_install], as well as in the [PyPSA-Earth documentation][PyPSA-Earth].

* There is no need for the BAU:

~~~
mamba create -n 'new_venv'
mamba activate new_venv
pip install -r requirements.txt
~~~

when installing the package dependencies, since the

~~~
mamba env create -f envs/environment.yaml
~~~

takes care of both the correct `venv` creation, and the packages installation. The only package requiring `pip` is the `highspy` solver. We highly recommend using `highspy`, and for that `pip` is needed:
~~~
sudo apt install python3-pip -y
pip install highspy
~~~

Python and Jupyter Notebooks (`.ipynb`) are optimally used in an IDE.

Our recommendation is [VSCode][VSCode][^2], together with the `Jupyter` [extension][Jupyter].


[^1]: Your Python `venv` can very, depending on the Jupyter Notebooks' content.
[^2]:   <b><font color='red'>Also used by the [PyPSA developers][PyPSA-Earth], due to its simplicity, and being open-source.</font></b>



<!-- # Internal Doc References -->
[venv]:         https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/environment.yaml
[dependencies]: https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/requirements.txt
[mamba_install]: https://github.com/conda-forge/miniforge?tab=readme-ov-file
[PyPSA-Earth]:  https://pypsa-earth.readthedocs.io/en/latest/installation.html
[VSCode]:       https://github.com/microsoft/vscode
[Jupyter]:      https://medium.com/@claudia.nikel/how-to-setup-a-jupyter-notebook-in-vs-code-w-virtual-env-kernels-install-packages-884cf643375e