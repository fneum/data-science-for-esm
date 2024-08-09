<!-- Content and Structure
================================ -->
<!-- ```{contents}
:local:
:depth: 1
``` -->

<span style="font-size:2.25em;">Anatomy of a Jupyter Book</span>

**Three things** are needed for building a [Jupyter Book][jupyter-book]:
* A configuration file ([_config.yml][fneum_content])
* A table of contents file ([_toc.yml][fneum_toc])
* Your book’s [source files][content]


::::{important}
:tags: ["full-width"]
<!-- :class: attention -->
`jupyter-book build` builds Jupyter Book off of a content source:
* <b><mark style="background-color: peachpuff; color: black">Jupyter Notebook (.ipynb)</mark></b> and
* <b><mark style="background-color: peachpuff; color: black">Markdown (.md)</mark></b> files.
<!-- > <br />
\ -->
:::{admonition} Supported files
:class: tip
For the full list of the available file formats go to the [JupyterBook](https://jupyterbook.org/en/stable/file-types/index.html).
:::

:::{admonition} Jupyter Notebook
:class: tip
Markdown also easily integrates into Jupyter Notebook files . For more refer to the [MyST](https://executablebooks.github.io/cookiecutter-jupyter-book/notebooks.html).
:::
::::

Use the files presented here as the template of your Jupyter Book, as they will reduce your content development time.

* The `.ipynb` and the `.md` content files are to be located in the root, or a subfolder, of the cloned `data-science-for-esm`, and specified accordingly in the `_toc.yml`<b>[^1]</b>.
* Both the `_config.yml`, as well as the `_toc.yml`, are to remain in the root of the `data-science-for-esm` folder.
* The website logo, as well as the other figures, can be placed in the `data-science-for-esm/_images/` [folder][_images_folder].
<br />
<br />

Modify the Content
===================

* **<ins>Modify the `.ipynb` and the `.md` files as seen fit. They are the core-content.</ins>**
* **When changing the images and modifying the content files, the referencing throughout the `.md` and the `.ipynb` files needs changing as well[^2].**

To have the content changes reflected in the website, there is a chain of **git** to-do commands:

<!-- git clone https://github.com/"owner"/data-science-for-esm.git -->
~~~
# make changes to the content
git status
git add .
git commit -m 'new changes applied'
git push origin content_branch
~~~

* The metadata of the website, such as the author, logo, and other relevant GitHub and Google Colab links, are to be defined in the `_config.yml`<b>[^3]</b>:
    * Use the already provided `_toc.yml` and `_config.yml` files as a template, and follow their structure.

* In the `data-science-for-esm/_toc.yml` [file](https://github.com/fneum/data-science-for-esm/blob/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm/_toc.yml), a sequence of files to be included in the Jupyter Book, and the GitHub Page, is defined, and further used by the `jupyter-build book` command.
    * Detailed customization instructions on both the `_toc.yml` and the `_config.yml` are provided in [link][here_1] and [link][here_2]. <strong><font color='red'>⇶ MUST READ!</font></strong>

After a successful run, the TOC will be displayed in the left-side menu of the website.


[^1]: If not being placed in the root folder, or subfolder, the workflow will be unable to find the files specified by the `_toc.yml`, resulting in the unsuccessful deployment, and unaccessible `https://<user>.github.io/data-science-for-esm`.
[^2]: <strong><font color='red'>Otherwise workflow deployment will break!</font></strong>
[^3]: https://jupyterbook.org/en/stable/start/create.html#book-configuration-config-yml



[jupyter-book]:     https://jupyterbook.org/en/stable/start/create.html#
[fneum_content]:    https://github.com/fneum/data-science-for-esm/blob/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm/_config.yml
[fneum_toc]:        https://github.com/fneum/data-science-for-esm/blob/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm/_toc.yml
[content]:          https://jupyterbook.org/en/stable/file-types/index.html
[_images_folder]:   https://github.com/open-energy-transition/data-science-for-esm/tree/ce07272ac531acdbe4b6e18110c5fbc70f3b03c0/data-science-for-esm/_images
[here_1]:           https://jupyterbook.org/en/stable/structure/configure.html
[here_2]:           https://jupyterbook.org/en/stable/structure/toc.html