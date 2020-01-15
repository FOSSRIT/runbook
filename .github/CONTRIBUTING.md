How to ontribute to the FOSSRIT Runbook
=======================================

This guide is a short introduction on how to contribute to the Runbook.
Follow these steps to make new contributions.


## Style guide

### Markdown

All documents are written in **Markdown**.
Markdown is a markup language.
See GitHub's [Mastering Markdown](https://guides.github.com/features/mastering-markdown/ "How to write Markdown") page to get started.

### One sentence per line

**Write each sentence in a document on a new line**.
This is awkward to write, but it will appear as paragraphs when published.
Most importantly, it makes changes (i.e. _diffs_) easier to read.
Make a new paragraph by leaving an empty line between sections.
Doing this makes pull requests easier to review and will make it easier for a maintainer to review your change.

Advanced writing tip: writing this way also makes you conscious of how long your sentences are.
See if you can keep your sentences shorter to reduce complexity.


## Test changes

**Use pipenv to set up a development environment and generate the Runbook on your computer.**

### Set up environment

The Runbook uses [**pipenv**](https://pipenv.readthedocs.io/en/latest/) to manage Python virtual environments (a.k.a. virtualenvs).
`pipenv` is a tool to make Python dependency management easier.
It also makes using virtual environments easier.
See the [pipenv installation guide](https://pipenv.readthedocs.io/en/latest/install/) to get started.

Once installed, run these commands inside the Runbook directory to initialize your project:

```bash
pipenv shell
pipenv sync
```
### Build your changes

Once your environment is set up, test your changes and check the appearance in the browser.

`pipenv shell` sets up a new virtualenv for the project.
It pre-loads both the documentation toolchain and the same theme we use for [runbook.fossrit.community](https://runbook.fossrit.community/).
When these dependencies are loaded, testing on your computer will emulate the same tests run in pull requests.

Run the following script on Linux/macOS:

```bash
docs/build_docs.sh
```

On Windows:

```bash
docs/make.bat
```

Either script generates HTML from our docs.
Rendered HTML is placed into `docs/_build`.
All HTML files are found in `docs/_build/html/`.
If you are using a Linux machine with Firefox installed, run this command in the terminal for a handy shortcut:

```bash
firefox docs/_build/html/index.html
```

Review your changes.
Make sure links work and formatting is not broken.
If it looks good, make a pull request!


## How to get your pull request (PR) merged

Follow these steps to get your PR merged:

1. Follow the style guide (explained above)
2. Test your changes and make sure it appears correctly (explained above)
3. Make a PR to FOSSRIT/runbook.
4. [_recommended_] Add a screenshot of the rendered documentation in your PR
5. All changes require one review from someone on the [FOSS@MAGIC GitHub Team](https://github.com/orgs/FOSSRIT/teams/foss-magic/members)
    * This keeps everyone on the same page about additions and removals to the Runbook

