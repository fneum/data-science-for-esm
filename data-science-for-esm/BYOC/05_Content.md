Content Modification Setup
=========================================================
Use the provided files as templates. This will assist you in content creating, reducing the time in searching for the answers.

> **Note:** `jupyter-book build` builds content from the *markdown* and jupyter notebook files, hence their content needs modifying.

* The website logo, as well as the other figures can be placed in the `data-science-for-esm/_images/` folder.
* Please keep in mind that, when changing images and modifying files, the referencing throughout `.md` and `.ipynb` files needs changing as well.
* The `.ipynb` and `.md` content files are to be located in the root of the `data-science-for--esm` folder, and specified in the `_toc.yml`.
    * If not being placed in the root, the workflow will be unable to find the files specified in the `_toc.yml`, resulting in the unsuccessful deployment, and unaccessible `github.io`.
* Modify `*.ipynb` and `.md` files as seen fit. They are the core-content.
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

* In the `data-science-for-esm/_toc.yml` [file](https://github.com/open-energy-transition/data-science-for-esm/blob/37c3ef84651a12ee947573dfedd6c4b7786731bc/data-science-for-esm/_toc.yml), a sequence of files to be included in the GitHub Page is defined, and further used by the `jupyter-build book` command.

After a successful run, the TOC displayed will be displayed in the left-side menu.
