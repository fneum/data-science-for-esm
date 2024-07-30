Deployment Setup
=================
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
