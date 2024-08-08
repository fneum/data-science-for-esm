GitHub Workflow Deployment
=========================================================
In [Deployment Settings](./05_Deploy.md#deployment-settings) we defined the deployment branch in the `.github/workflows/deploy.yml` [file][deploy], which is used by the workflow, whenever performing `git push`.

You are free to use any branch, other than the `gh-pages`, keeping in mind that only upon the `git push`, the workflow will be triggered.

The workflow deployment itself is tracked by your repository's status indicator, in this case a beige-brown dot &nbsp;<strong><b><font color='peru'>⏺</font></strong></b>
* _Clicking on it will show the running status, and the deployment details_.

As mentioned, the deployment takes minutes to finish, depending on the content files, i.e. the python commands in the Jupyter Notebooks, which will take the most of time required for the deployment.

<center>
<figure>
    <!-- <a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'> -->
    <img src='https://raw.githubusercontent.com/mdzzg/data-science-for-esm/mdzzg/data-science-for-esm/_images/05_deployment_status.png' width='85%'style='vertical-align:middle;border:5px solid paleturquoise;margin:30px 30px' />
    <!-- </a> -->
    <figcaption>Deployment status upon <code>git push</code> to the branch specified in the <mark>deploy.yml</mark> file</figcaption>
</figure>
</center>

Upon the deployment finalization, the status indicator turns to:
* _successful_: a green thick <strong><b><font color='green'>🗸</font></strong></b>
    * you should be able to see the changes taking place, after some moments, at the specified `https://<user>.github.io/data-science-for-esm`[^1]
* _unsuccessful_: a red cross mark <font color="red">🗶</font>
    * indicating an error in the `_toc.yml`, or one of the content files, which need to be revisited.

<center>
<figure>
    <!-- <a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'> -->
    <img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/06_successful_deployment.png' width='85%'style='vertical-align:middle;border:5px solid paleturquoise;margin:30px 30px' />
    <!-- </a> -->
    <figcaption>Successful deployment, after a finalized <code>jupyter-book build</code> run</figcaption>
</figure>
</center>

[^1]: https://github.com/executablebooks/cookiecutter-jupyter-book/tree/main



[deploy]:   https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L4-L7