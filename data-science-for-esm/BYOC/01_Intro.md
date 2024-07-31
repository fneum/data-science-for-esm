Introduction
=========================================================
<!-- ###### List of Abbreviation[^bignote] -->

<!-- ```{contents}
:local:
``` -->

This section helps academics, and alike, in building their own content, by modifying this repository. This repository is used as ane example in the figures below.

> **Goal:** *To create a course page for your own knowledge dissemination, like this one, follow this guide.*

* Its primary purpose is to guide you on how to generate a GitHub page, to be used for learning material, i.e. lectures, or similar.
* It can also be purpose for anything else, for that matter.
* This setup uses the [cookiecutter-jupyter-book](https://github.com/executablebooks/cookiecutter-jupyter-book/tree/main)[^1][^2] workflow.

> **Note:** *This serves only as a reference, as the the full explanation is below.*

By following these instructions, one is able to create his own website, alike this one, with a tailor-made content, quickly and with ease. Albeit, there are two or three things to keep in mind when doing so, specified below.


Requirements
-------------
For a successful workflow run, the [correct python environment][venv], with all the [python package dependencies][dependencies] satisfied, is required. Our suggestion is the package manager `conda` or `mamba`, for which further details, and installation instructions, are provided in the [documentation of PyPSA-Earth creators][PyPSA-Earth].

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

Python and Jupyter Notebooks (`.ipynb`) are optimally used in an [IDE][VSCode]. Our recommendation is VSCode, used by the [PyPSA developers][PyPSA-Earth], due to its ease of use, and being open-source.

[^1]: [More details also here](https://executablebooks.github.io/cookiecutter-jupyter-book/intro.html)[^2]
[^2]: These serves only as a reference, as the the full explanation is below
<!-- # Internal Doc References -->
[gh_actions]:           https://github.com/peaceiris/actions-gh-pages
[gh_actions_python]:    https://github.com/peaceiris/actions-gh-pages?tab=readme-ov-file#%EF%B8%8F-static-site-generators-with-python
[venv]:                 https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/environment.yaml
[dependencies]:         https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/requirements.txt
[PyPSA-Earth]:          https://pypsa-earth.readthedocs.io/en/latest/installation.html
[VSCode]:               https://github.com/microsoft/vscode