# ACEFA Website

Repository for the website for ACEFA - the Australian Consortium for Epidemic Forecasting & Analytics.

## Instructions for contributing to this repository

### A note on branches

This github pages website is built with quarto. It is configured so that it publishes the website via the `gh-pages` branch (see [publishing quarto websites](https://quarto.org/docs/publishing/github-pages.html#publish-command) for more detail).

**This branch should never be modified manually.**

### Setting up

1.  Fork this repo into personal GitHub account > you must untick the option to "Copy main branch only" as you need both branches. 
 <img width="755" alt="Screenshot 2024-02-16 at 2 21 25 pm" src="https://github.com/acefa-hubs/acefa-hubs.github.io/assets/11023506/7c9e2890-4200-4a24-9e27-24bbfda7d3d1">

3.  Navigate to your fork `github.com/[YOURUSERNAME]/acefa-hubs.github.io` and clone a local version to your machine
4.  Open new project from version control in local RStudio
5.  Configure your remote repository:

-   list remotes

```         
git remote -v
> origin  git@github.com:[YOURUSERNAME]/acefa-hubs.github.io.git (fetch)
> origin  git@github.com:[YOURUSERNAME]/acefa-hubs.github.io.git (push)
```

-   add upstream

```         
git remote add upstream git@github.com:acefa-hubs/acefa-hubs.github.io.git
```

-   verify upstream has been added by checking remotes again

```         
git remote -v
 > origin  git@github.com:[YOURUSERNAME]/acefa-hubs.github.io.git (fetch)
 > origin  git@github.com:[YOURUSERNAME]/acefa-hubs.github.io.git (push)
 > upstream        git@github.com:acefa-hubs/acefa-hubs.github.io.git (fetch)
 > upstream        git@github.com:acefa-hubs/acefa-hubs.github.io.git (push)
```

### Making changes

1.  Before beginning new work, make sure your fork is up to date with the remote:

    ```         
    # fetch from upstream repo
    git fetch upstream main

    # then merge
    git merge upstream/main
    ```

2.  Make your changes. The key files to modify for content will all be `.qmd` (quarto) files:

-   `index.qmd` is the file for the main landing page
-   `about.qmd` is the file for the "Team" tab
-   `pillars/` folder contains `decision-support.qmd`, `methods-and-tools.qmd`, `data.qmd`, and `engagement.qmd`, the main roles of the consortium.
-   `_quarto.yml` contains higher level organisation for the website
-   `.css` and `.scss` files contain style code
-   `images/` folder stores all images used as thumbnails or as figures

**Remember** to preview your changes with the 'Render' button, or with `quarto render` in the terminal.

3.  When you're happy with the changes, commit and push to origin all changes.

4.  Create pull request on GitHub. Once a pull request is merged, the website will be republished automatically using a Github Action that has been configured in the main repository.
