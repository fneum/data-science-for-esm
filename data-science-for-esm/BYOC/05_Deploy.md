Deploy Settings
===================
> **Note:** The key point is to set the correct deployment branch in the <code>./github/workflows/deploy.yml</code>.

In the <code>.github/workflows/deploy.yml</code> [file][deploy_1], of the cloned repository, specify the branch, to be used by the workflow:

~~~
on:
  # Trigger the workflow on push to the main branch
  push:
    branches:
    - main
~~~
Upon the `git push` command to the specified branch<b>[^1]</b>, the workflow will be triggered.

> **Note:** The specified `branch` can be any<b>[^2]</b>, other than the <ins>`gh-pages`</ins>.

In the same [`deploy.yml` file][deploy_2] set the following permissions:

~~~
permissions:
  pages: write
  deployments: write
  contents: write
  statuses: write
  actions: write
  checks: read
~~~

This setup uses the `main` branch in the workflow, but it can also be any other newly created side-branch. Upon the `git push`, the [workflow](./08_Workflow.md#github-workflow-deployment) will be triggered.

The deployment itself is the `jupyter-build book data-science-for-esm` [command][command]. This command is in charge generating the HTML code from the data provided in the data-science-for-esm [folder][folder].

Further explanation of this command, i.e. the `jupyter-book build`, as well as the other commands is provided in the [README.md](https://github.com/open-energy-transition/data-science-for-esm/blob/37c3ef84651a12ee947573dfedd6c4b7786731bc/README.md) file. A more detailed explanation is to be found in the following Jupyter Book references:
<!-- 1. [Build your book](https://jupyterbook.org/en/stable/start/build.html) -->
1. [Build from the command line](https://jupyterbook.org/en/stable/basics/build.html)
1. [Structure the Table of Contents](https://jupyterbook.org/en/stable/structure/toc.html)

Although it is perfectly fine to trigger the workflow from the `main` working branch, there are a couple of reasons why you should stay off the `main` branch and use a `feature` branch instead. These are explained in the next [section](./06_Deploy_Advanced.md#content-ie-feature-branch).



[^1]: In this example it is the `main` branch.
[^2]: <span style="font-size:.8em;">The workflow has been successfully tested using the `main` branch, as well as the side-branches, once correctly specifying the branch, and the permissions, in the `deploy.yml` file, as explained above.</span>



<!-- # Internal Doc References -->
[deploy_1]: https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L4-L7
[deploy_2]: https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L9C1-L15C15
[command]:  https://github.com/open-energy-transition/data-science-for-esm/blob/b1ab15c6d99fb325ca3877b0d33578a42669c3b7/.github/workflows/deploy.yml#L37
[folder]:   https://github.com/fneum/data-science-for-esm/tree/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm
