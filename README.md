# JuliaPhylo website source

This directory contains the Quarto source for the JuliaPhylo website. 

## notes for developers

The website is created using quarto + gihub pages. See the quarto documentation
on this
[here](https://quarto.org/docs/publishing/github-pages.html#publish-command).

To render the website locally, first install [quarto](https://quarto.org).
There are 3 steps to publish a new version of the website:
update the `task-view.qmd`, commit/push it,
then publish the website. Here is how.

1. Update the task view page: this requires updating `task-view.qmd`
  with any updates made previously on some package data in any of the
  `packagedata/*.yaml` files.
  To perform this step, run `fixit` script, which takes as input
   - the skeleton `_task-view-template.qmd`,
     which does not contain any package data
   - the content of `packagedata/*.yaml`.

   The script's output is to overwrite `task-view.qmd` with
   updated package information, listed under their appropriate tasks & subtasks.

   Run the script like this (from the root directory of this repo):
   ```sh
   fixit
   ```

2. Render the site localy to check that it's how you want it to be.
   For this, run

   ```sh
   quarto render
   ```

   This will create (or update) a `_site/` folder
   (which should *not* be committed on the main branch).
   Check it out by opening `_site/index.html` in a browser.

   Commit the `task-view.qmd` created in step 1 once you are happy
   (on the main branch).

3. When ready to publish a new version of the website, make
   sure you are on the main branch then run:
   ```sh
   quarto publish gh-pages
   ```
