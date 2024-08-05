Requirements
=============
For a successful workflow run, the [correct python environment][venv], with all of the [python package dependencies][dependencies] included, is a requirement.

Our suggestion is the package manager `conda` or `mamba`, which for installation instructions are provided in the [documentation of PyPSA-Earth creators][PyPSA-Earth].

* There is no need for the BAU:

~~~
pip install -r requirements.txt
~~~

since the

~~~
mamba env create -f envs/environment.yaml
~~~

takes care of both the correct `venv` creation, and the packages installation. The only package requiring `pip` is the `highspy` solver. We highly recommend using `highspy`, and for that `pip` is needed:
~~~
sudo apt install python3-pip -y
pip install highspy
~~~

Python and Jupyter Notebooks (`.ipynb`) are optimally used in an IDE.

Our recommendation is [VSCode][VSCode], together with the `Jupyter` extension[^1].


[^1]:   <b><font color='red'>Also used by the [PyPSA developers][PyPSA-Earth], due to its simplicity, and being open-source.</font></b>



<!-- # Internal Doc References -->
[venv]:                 https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/environment.yaml
[dependencies]:         https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/requirements.txt
[PyPSA-Earth]:          https://pypsa-earth.readthedocs.io/en/latest/installation.html
[VSCode]:               https://github.com/microsoft/vscode