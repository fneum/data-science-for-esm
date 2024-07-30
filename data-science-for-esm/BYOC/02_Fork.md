Create a new fork
=================
<!-- > **Note:** The first step is forking the repository, having the below in mind.

Before forking this repository please have the following in mind: -->
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

These will be re-generated, upon a successful workflow execution, every time `git push` is performed, in the prior specified git branch. Branch specification is provided in the [Deployment Setup](./04_deploy.md#deployment-setup).

<!-- of the forked repository, in the `.github/workflows/deploy.yml` ([link][07]) file which will contain the required `HTML`, `css`, `.js`, and other files
is used for generating the required `HTML`, `css`, `.js`, as well as the other files - other than the `gh-pages`

- on preexisting knowledge disseminating the gained expertise by OET, and TU Berlin, to help .   Welcome to the website accompanying the course [Data Science for Energy System Modelling][04]. This course is being developed by [Dr. F. Neumann][05] and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin][06]. -->
