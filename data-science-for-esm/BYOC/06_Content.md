Modify the Content
===============
Use these files as the template of your content. They will reduce the development time for your subject matter.

:::{note}
:tags: ["full-width"]
`jupyter-book build` builds Jupyter Book off of <mark>Jupyter Notebook</mark> and <mark>markdown</mark> files.
<!-- > <br />
\ -->
:::{admonition} Supported files
:class: tip
For the full list of the available file formats go to [JupyterBook](https://jupyterbook.org/en/stable/file-types/index.html).
:::
:::

:::{note}
:tags: ["raises-exception"]
:tags: ["margin"]
Jupyter Notebook files can contain markdown. For more refer to [MyST](https://executablebooks.github.io/cookiecutter-jupyter-book/notebooks.html).
:::

* The website logo, as well as the other figures can be placed in the `data-science-for-esm/_images/` folder.
* When changing images and modifying content files, the referencing throughout the `.md` and the `.ipynb` files needs changing also[^1].
* The `.ipynb` and `.md` content files are to be located in the root of the cloned `data-science-for-esm`, or a subfolder, and specified accordingly in the `_toc.yml`.
    * If not being placed in the root folder, or subfolder, the workflow will be unable to find the files specified by the `_toc.yml`, resulting in the unsuccessful deployment, and unaccessible `github.io`.
* Modify `.ipynb` and `.md` files as seen fit. They are the core-content.
* For any content change, there is a chain of git to-do commands, for a website update:
~~~
git clone https://github.com/"owner"/data-science-for-esm.git
# make changes to the content
git status
git add .
git commit -m 'new changes applied'
git push origin stanford
~~~

Both `_config.yml`, as well as the `_toc.yml` are to remain in the root of the `data-science-for esm` folder. The details of the website, such as the author, logo, other relevant GitHub and Google Collab links, are defined in the `_config.yml`. Please use the already provided `_toc` and `_config.yml` files as a template, and follow their structure.

* In the `data-science-for-esm/_toc.yml` [file](https://github.com/fneum/data-science-for-esm/blob/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm/_toc.yml), a sequence of files to be included in the GitHub Page is defined, and further used by the `jupyter-build book` command.

After a successful run, the TOC displayed will be displayed in the left-side menu.


[^1]: Otherwise it results in a broken workflow deployment.
[^2]: 