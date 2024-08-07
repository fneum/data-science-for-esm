Deployment Settings
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
Upon the `git push` command to the specified branch[^1], the workflow will be triggered.

> **Note:** The specified `branch` can be any[^2], other than the <ins>`gh-pages`</ins>.

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

This setup uses the `main` branch in the workflow, but it can also be any other newly created side-branch. Upon the `git push`, the [workflow](./07_Workflow.md#github-workflow-deployment) will be triggered.

The deployment itself is the `jupyter-build book data-science-for-esm` [command][command]. This command is in charge generating the HTML code from the data provided in the data-science-for-esm [folder][folder].

Further explanation of this command, i.e. the `jupyter-book build`, as well as the other commands is provided in the [README.md](https://github.com/open-energy-transition/data-science-for-esm/blob/37c3ef84651a12ee947573dfedd6c4b7786731bc/README.md) file. A more detailed explanation is to be found at the following Jupyter Book references:
<!-- 1. [Build your book](https://jupyterbook.org/en/stable/start/build.html) -->
1. [Build from the command line](https://jupyterbook.org/en/stable/basics/build.html)
1. [Structure the Table of Contents](https://jupyterbook.org/en/stable/structure/toc.html)

___

Content (i.e. feature) branch[^3]
------------------------------
There is a very valid reason for deploying your website from a non-main branch though, i.e. commonly termed feature branch[^4].

The argument for doing so is to keep the `main` branch of your forked repository `https://github.com/<user>/data-science-for-esm` synchronized/identical to `main` branch of the upstream `https://github.com/fneum/data-science-for-esm` repository.

In particular, this approach facilitates comparing the fork and the upstream, retrieving updates/patches, and also allows you to "reset" your fork, if/when something has gone completely wrong with the content development.

A simple workflow of keeping your fork's `main` up-to-date with the upstream `main` is:
~~~
git remote add upstream https://github.com/fneum/data-science-for-esm
git pull upstream main
~~~
Furthermore, you might want to merge the `main` branch updates, obtained by synchronizing with the upstream, to your Jupyter Book `content_branch`:

~~~
git switch content_branch # alternatively you can also do: git checkout content_branch
git cherry-pick <last main branch commit hash>
~~~

* At this point, if there are conflicts, resolve them manually, while keeping in mind that “incoming” refers to the changes obtained from the upstream using `git pull` and “HEAD” refers current state of the `content_branch`:
```
git cherry-pick --continue
```

In order to save these changes, follow the instructions in [Modify the Content](./06_Content.md#modify-the-content) section.

[^1]: In this example it is the `main` branch.
[^2]: <span style="font-size:.8em;">The workflow has been successfully tested using the `main` branch, as well as the side-branches, once correctly specifying the branch, and the permissions, in the `deploy.yml` file, as explained above.</span>
[^3]: <strong><font color='red'>This section is intended for </font></strong> <mark style="background-color: red; color: black"><b>advanced use.</b></mark>
[^4]: In this material the feature branch is defined as `content_branch`.

<!-- # Internal Doc References -->
[deploy_1]: https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L4-L7
[deploy_2]: https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L9C1-L15C15
[command]:  https://github.com/open-energy-transition/data-science-for-esm/blob/b1ab15c6d99fb325ca3877b0d33578a42669c3b7/.github/workflows/deploy.yml#L37
[folder]:   https://github.com/fneum/data-science-for-esm/tree/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm
