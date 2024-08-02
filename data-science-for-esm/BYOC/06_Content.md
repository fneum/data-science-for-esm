Modify the Content
===============
Use these files as the template of your content, as they will reduce your content development time.

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
Jupyter Notebook files can also contain markdown. For more refer to [MyST](https://executablebooks.github.io/cookiecutter-jupyter-book/notebooks.html).
:::

* The website logo, as well as the other figures can be placed in the `data-science-for-esm/_images/` [folder][_images_folder].
* **When changing the images and modifying the content files, the referencing throughout the `.md` and the `.ipynb` files needs changing as well[^1].**
* The `.ipynb` and the `.md` content files are to be located in the root, or a subfolder, of the cloned `data-science-for-esm`, and specified accordingly in the `_toc.yml`[^2].
* **<ins>Modify the `.ipynb` and the `.md` files as seen fit. They are the core-content.</ins>**

To have the content changes be reflected in the website, there is a chain of git to-do commands:

<!-- git clone https://github.com/"owner"/data-science-for-esm.git -->
~~~
# make changes to the content
git status
git add .
git commit -m'new changes applied'
git push origin main
~~~

* Both the `_config.yml`, as well as the `_toc.yml` are to remain in the root of the `data-science-for esm` folder.

* The metadata of the website, such as the author, logo, and other relevant GitHub and Google Collab links, are to be defined in the `_config.yml`[^3]:
    * Use the already provided `_toc.yml` and `_config.yml` files as a template, and follow their structure.

* In the `data-science-for-esm/_toc.yml` [file](https://github.com/fneum/data-science-for-esm/blob/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm/_toc.yml), a sequence of files to be included in the GitHub Page is defined, and further used by the `jupyter-build book` command.
    * Detailed customization instructions on both the `_toc.yml` and the `_config.yml` are provided in [link][here_1] and [link][here_2]. <strong><font color='red'>⇶ MUST READ!</font></strong>

After a successful run, the TOC will be displayed in the left-side menu of the website.


[^1]: <strong><font color='red'>Otherwise it results in a broken workflow deployment!</font></strong>
[^2]: If not being placed in the root folder, or subfolder, the workflow will be unable to find the files specified by the `_toc.yml`, resulting in the unsuccessful deployment, and unaccessible `https://<user>.github.io/data-science-for-esm`.
[^3]: https://jupyterbook.org/en/stable/start/create.html#book-configuration-config-yml



[_images_folder]:   https://github.com/open-energy-transition/data-science-for-esm/tree/ce07272ac531acdbe4b6e18110c5fbc70f3b03c0/data-science-for-esm/_images
[here_1]:           https://jupyterbook.org/en/stable/structure/configure.html
[here_2]:           https://jupyterbook.org/en/stable/structure/toc.html