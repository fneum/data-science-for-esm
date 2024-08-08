Content (i.e. feature) Branch
=================================
In the [previous section](./05_Deploy.md#deployment-settings) we defined the `main` branch as the deployment branch.

This section is intended for advanced users, who would like to:
1. deploy their website from a so-called feature branch,
1. keep the main branch synchronized with the original source, i.e. the upstream.

There is a valid reason why one would want the website deploying from a non-main branch, i.e. commonly termed a feature branch.

The argument for doing so is to keep the `main` branch of your fork `https://github.com/<user>/data-science-for-esm` synchronized/identical to the `main` branch of the upstream `https://github.com/fneum/data-science-for-esm` repository.

In particular, this approach facilitates comparing the fork and the upstream, retrieving updates/patches, and also allows you <ins>resetting</ins> your fork, in case something has gone completely wrong.

A simple workflow of keeping your fork's `main` up-to-date with the upstream `main` is:
~~~
git remote add upstream https://github.com/fneum/data-science-for-esm
git pull upstream main
~~~
To merge the `main` branch updates, obtained by synchronizing your `main` with the upstream `main`, into your Jupyter Book `content_branch`:

~~~
git switch content_branch # alternatively you can also do: git checkout content_branch
git cherry-pick <last main branch commit hash>
~~~

* At this point, if there are conflicts, resolve them manually, while keeping in mind that “incoming” refers to the changes obtained from the upstream using `git pull` and “HEAD” refers current state of the `content_branch`:
```
git cherry-pick --continue
```

In order to save these changes, follow the instructions in [Modify the Content](./06_Content.md#modify-the-content) section.


<!-- [^1]: <strong><font color='red'>This section is intended for </font></strong> <mark style="background-color: red; color: black"><b>advanced use.</b></mark> -->
[^1]: In this material the feature branch is defined as `content_branch`.



<!-- # Internal Doc References -->
[deploy_1]: https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L4-L7
[deploy_2]: https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml#L9C1-L15C15
[command]:  https://github.com/open-energy-transition/data-science-for-esm/blob/b1ab15c6d99fb325ca3877b0d33578a42669c3b7/.github/workflows/deploy.yml#L37
[folder]:   https://github.com/fneum/data-science-for-esm/tree/bc6e35f5c007a33972d23d1df7e26c59f2a875dd/data-science-for-esm
