<!-- # Table of Contents

1. [BYOC](#build-your-own-content)
1. [New Fork](#creating-a-new-fork)
1. [GH Pages](#gh-pages-setup)
1. [GH Workflows Deployment](#gh-workflows-deployment) -->


<font color="red">Build Your Own Content</font>
===============================================
<!-- ###### List of Abbreviation[^bignote] -->


This section assists academics, and alike, in build their content, by modifying this repository, or the original [Dr. F. Neumann's repository][fneum]. Dr. Neumann's repository is used as ane example in the figures below.

> **Goal:** *To create a course page for your own knowledge dissemination, like OET has done, follow this guide.*

* Its primary purpose is guidance on how to generate a GitHub page, to be used for learning material, i.e. lectures, or similar.
* It can also be purpose for anything else, for that matter.
* This setup draws from the [peaceiris actions-gh-pages][gh_actions], in specific using the [Static Site Generator with Python][17].
    * *This serves only as a reference, as the the full explanation is below.*

By following these instructions, one is able to create his own website, alike this one, with a tailor-made content, quickly and with ease. However, there are two or three things to keep in mind when doing so. Please read on.


Requirements
------------
Please keep in mind that that for a successful workflow run, the [correct python environment][12], with all the [python package dependencies][13] satisfied, is required. Our suggestion is the package manager `conda` or `mamba`, for which further details, and installation instructions, are provided in the [documentation of PyPSA-Earth creators][15].

* Please also keep in mind that there is no need for the usual:

~~~
pip install -r requirements.txt
~~~

since the

~~~
mamba env create -f envs/environment.yaml
~~~

takes care of both the correct `venv` creation, and packages installation. The only package requiring `pip` is the `highspy` solver. We highly recommend using `highspy`, and for that `pip` is needed:
~~~
sudo apt install python3-pip -y
pip install highspy
~~~

Python and `*.ipynb` are optimally used in an [IDE](https://github.com/microsoft/vscode). Our recommendation is VSCode, used by the [PyPSA developers][15], due to its ease of use, and being open-source.

---

Creating a new fork of this repository
=====================================================================
> **Note:** The first step is forking the repository, having the below in mind.

Before forking this repository please have the following in mind:
* In the <strong><b><mark>Create a new fork</mark></b></strong> pop-up menu, shown in the figure below, <ins>>deselect</ins> the default **Copy the `main` branch only** option. 
    
By doing so, you will reduce further branch creation, required by the workflow.

:::{note}
<center>
<figure>
    <a href='https://github.com/fneum/data-science-for-esm/fork'>
    <img src='https://github.com/open-energy-transition/data-science-for-esm/raw/stanford/data-science-for-esm/_images/03_fork_option.png' alt='' width='95%' style='vertical-align:middle;border:5px solid goldenrod;margin:20px 0px' />
    </a>
    <figcaption>Clicking on the image above will lead directly to the <strong><b><mark>Create a new fork</mark></b></strong> menu</figcaption>
</figure>
</center>
:::

> **Note:** The key point is to have/keep the `stanford` branch in your fork. This is fully tested using the `stanford` branch

In this workflow:
* Your source code is in the `stanford` branch
* Your published website is in the `gh-pages` branch

* Alternatively, the `stanford` branch can be created locally: 
~~~
git switch -c stanford
git push origin stanford
~~~

* However, this is to be skipped if adhering to the **Note** above.
* `gh-pages` branch will be automatically generated, as defined by the workflow, hence its creation is not required.
* It is also **not** required to have the `gh-pages` locally, once generated, as it hosts only the static site build files, which are taken care of by the workflow.

> **Note:** The remote `gh-pages`, itself, hosts the required `HTML`, `css`, `.js`, and the other files, used for generating the `github.io` website. Hence, there is no requirement for having the branch locally.

These will be re-generated, upon a successful workflow execution, every time `git push` is performed, in the prior specified git branch. Branch specification is provided [below](#deployment-setup).

<!-- of the forked repository, in the `.github/workflows/deploy.yml` ([link][07]) file which will contain the required `HTML`, `css`, `.js`, and other files
is used for generating the required `HTML`, `css`, `.js`, as well as the other files - other than the `gh-pages`

- on preexisting knowledge disseminating the gained expertise by OET, and TU Berlin, to help .   Welcome to the website accompanying the course [Data Science for Energy System Modelling][04]. This course is being developed by [Dr. F. Neumann][05] and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin][06]. -->

---

GitHub Pages Setup
=================================================
* In the your own forked repository `"owner"/data-science-for-energy-system-modelling`, please go to the GitHub **Settings** -> **Pages**.

* In the **GitHub Pages**, go to the **Branch** section, and change the selection from `None` to `gh-pages` `/root`.

Once the branch has been selected, a URL will be provided (<ins>please give it a moment</ins>), at the top: **Your site is live at [https://"owner".github.io/data-science-for-esm](https://open-energy-transition.github.io/data-science-for-esm/)**

<center>
<figure>
    <a href='https://github.com/mdzzg/data-science-for-esm/settings/pages'>
    <img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/04_gh_pages-options.png' width='97%'style='vertical-align:middle;border:5px solid darkgreen;margin:30px 30px' />
    </a>
    <figcaption>Clicking on the image above will lead directly to the our <strong><b><mark>GitHub Pages</mark></b></strong> settings menu</figcaption>
</figure>
</center>

<!-- This GitHub is the go to location for disseminating any material, be it Jupyter Notebooks, slides, videos, markdown text explanations, or links to your other resources.  -->


---

Deployment Setup
===============================================
> **Note:** The key point is to set the correct deployment branch in the <code>./github/workflows/deploy.yml</code>.

In the <code>.github/workflows/deploy.yml</code> [file][deploy] please specify the branch, later to be used by the workflow. Upon the `git push` command to the specified branch, the workflow will be triggered:

~~~
    push:
      branches:
      - stanford
~~~

The specified `branch` can be any[^1], other than the <ins>`gh-pages`</ins>.

This setup uses the `stanford` branch for our workflow, but it can also be the `main`, or any other newly created branch. Upon the `git push`, the [workflow](#github-workflow-deployment) will be triggered.

The deployment itself is the `jupyter-build book data-science-for-esm/` [command](https://github.com/open-energy-transition/data-science-for-esm/blob/b1ab15c6d99fb325ca3877b0d33578a42669c3b7/.github/workflows/deploy.yml#L37). This command is generating the HTML code from the data provided in the data-science-for-esm [folder][16].

Further explanation of this command, i.e. `jupyter-book build`, as well as the other commands is provided in the [README.md](https://github.com/open-energy-transition/data-science-for-esm/blob/37c3ef84651a12ee947573dfedd6c4b7786731bc/README.md) file. A more detailed explanation is to be found at the following **References:**
1. [Build your book](https://jupyterbook.org/en/stable/start/build.html)
1. [Build from the command line](https://jupyterbook.org/en/stable/basics/build.html)
1. [Structure the Table of Contents](https://jupyterbook.org/en/stable/structure/toc.html)

---

Content Modification Setup
=========================================================
Please use the provided files as templates, as this will assist you in content creating, reducing the time in searching for the answers.

> **Note:** `jupyter-book build` builds content from the *markdown* and jupyter notebook files, hence their content needs modifying.

* The website logo, as well as the other figures can be placed in the `data-science-for-esm/_images/` folder.
* Please keep in mind that, when changing images and modifying files, the referencing throughout `.md` and `.ipynb` files needs changing as well.
* The `.ipynb` and `.md` content files are to be located in the root of the `data-science-for--esm` folder, and specified in the `_toc.yml`.
    * If not being placed in the root, the workflow will be unable to find the files specified in the `_toc.yml`, resulting in the unsuccessful deployment, and unaccessible `github.io`.
* Please modify `*.ipynb` and `.md` files as seen fit. They are the core-content.
* Upon each content update, there is a chain of git to-do commands, resulting in the website update:
~~~
git status
git add .
git commit -m 'new changes applied'
git push origin stanford
~~~

Both `_config.yml`, as well as the `_toc.yml` are to remain in the root of the `data-science-for esm` folder. The details of the website, such as the author, logo, other relevant GitHub and Google Collab links, are defined in the `_config.yml`. Please use the already provided `_toc` and `_config.yml` files as a template, and follow their structure.

* In the `data-science-for-esm/_toc.yml` [file](https://github.com/open-energy-transition/data-science-for-esm/blob/37c3ef84651a12ee947573dfedd6c4b7786731bc/data-science-for-esm/_toc.yml), a sequence of files to be included in the GitHub Page is defined, and further used by the `jupyter-build book` command.

After a successful run, the TOC displayed in the menu, located on the left side of the page.

---

GitHub Workflow Deployment
=========================================================
In [Deployment Setup](#deployment-setup) we defined the deployment branch in the `.github/workflows/deploy.yml` [file][deploy], which is used then used for the deployment, whenever performing `git push`. You are free to use any branch, other than the `gh-pages`, keeping in mind that only upon the `git push`, the workflow will be triggered.

The workflow deployment itself is tracked by the status indicator in the repository, in this case a beige-brown dot <strong><b><font color='peru'>⏺</font></strong></b>, which if clicked on, will show the running status, and the deployment details. As mentioned, the deployment takes approx. 2 minutes to finish.

<center>
<figure>
    <!-- <a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'> -->
    <img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/05_deployment_status.png' width='85%'style='vertical-align:middle;border:5px solid paleturquoise;margin:30px 30px' />
    <!-- </a> -->
    <figcaption>Deployment status upon <code>git push</code> to the branch specified in the <em>deploy.yml</em> file</figcaption>
</figure>
</center>

Upon a successful deployment, indicated by the deploy status:
* successful: a green thick <strong><b><font color='green'>🗸</font></strong></b>
* unsuccessful: a red cross mark <font color="red">🗶</font>,
you should be able to see the changes taking place in the specified `github.io` URL.

<center>
<figure>
    <!-- <a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'> -->
    <img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/06_successful_deployment.png' width='85%'style='vertical-align:middle;border:5px solid paleturquoise;margin:30px 30px' />
    <!-- </a> -->
    <figcaption>Successful deployment, after a finalized <code>jupyter book build</code> run</figcaption>
</figure>
</center>


Relevant References for further reading
---------------------------------------

1. Jupyter-book
    * https://jupyterbook.org/en/stable/start/build.html
    * https://jupyterbook.org/en/stable/structure/toc.html
1. PyPSA-Earth:
    * https://pypsa-eur.readthedocs.io/en/latest/introduction.html
1. Open Energy Transition
    * https://openenergytransition.org/about-us.html#theory-of-change
    * https://open-energy-transition.github.io/handbook/
1. Data Science for Energy System Modelling
    * https://www.tu.berlin/ensys
    * https://fneum.github.io/data-science-for-esm/09-workshop-pypsa.html
    * https://moseskonto.tu-berlin.de/moses/modultransfersystem/bolognamodule/beschreibung/anzeigen.html;jsessionid=DQfixqzzpn1XIg5N1GG7S9um4EDykZn99AHmH6Fj.moseskonto?number=31027&version=1&sprache=2
1. Dr. Fabian Neumann
    * https://www.neumann.fyi/

<!-- <mark style="background-color: peachpuff; color: black"> -->
*Kindly [reference][11] us, in case using our materials, e.g. the workflow presented here.
This way, your success is our success also.*

<!-- # Internal Doc References -->
[fneum]:                https://github.com/fneum/data-science-for-esm
[gh_actions]:           https://github.com/peaceiris/actions-gh-pages
[gh_actions_python]:    https://github.com/peaceiris/actions-gh-pages?tab=readme-ov-file#%EF%B8%8F-static-site-generators-with-python
[deploy]:               https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L4-L7
[09]: https://github.com/open-energy-transition/data-science-for-esm/fork
[10]: https://github.com/open-energy-transition/data-science-for-esm/settings/pages
[11]: https://open-energy-transition.github.io/data-science-for-esm/00_intro.html
[12]: https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/environment.yaml
[13]: https://github.com/open-energy-transition/data-science-for-esm/blob/e52f7980165928a7cd90826ee0bf8cd3fb407892/requirements.txt
[15]: https://pypsa-earth.readthedocs.io/en/latest/installation.html
[16]: https://github.com/open-energy-transition/data-science-for-esm/tree/ef394898e3100e2bd2d074a8b2da89235355cd4e/data-science-for-esm

<!-- <center><mark>Table of Abbreviations</mark></center> -->
<!-- ###### Table of Abbreviations -->

[^1]: The workflow has been successfully tested using the `stanford` branch, while, when using the `main` branch, we experienced some issues, which are currently being investigated. 

[^bignote]: | Acronym     | Description |
    |:-----------:|:-----------:|
    | **GH**      | GitHub      |
    | **repo**    | repository  |