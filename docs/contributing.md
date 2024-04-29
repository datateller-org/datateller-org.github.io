# Contributing

Contributions are welcome, and they are greatly appreciated! Every little bit
helps, and credit will always be given.

You can contribute in many ways:

## Types of Contributions

### Report Bugs

Report bugs at https://github.com/datateller-org.github.io/issues.

If you are reporting a bug, please include:

- Your operating system name and version.
- Any details about your local setup that might be helpful in troubleshooting.
- Detailed steps to reproduce the bug.

### Fix Bugs

Look through the GitHub issues for bugs. Anything tagged with “bug” and “help
wanted” is open to whoever wants to implement it.

### Implement Features

Look through the GitHub issues for features. Anything tagged with “enhancement”
and “help wanted” is open to whoever wants to implement it.

### Write Documentation

Data Teller could always use more documentation, whether as part of the official
Data Teller docs, in docstrings, or even on the web in blog posts, articles, and
such.

### Submit Feedback

The best way to send feedback is to file an issue at
https://github.com/datateller-org.github.io/issues.

If you are proposing a feature:

- Explain in detail how it would work.
- Keep the scope as narrow as possible, to make it easier to implement.
- Remember that this is a volunteer-driven project, and that contributions are
  welcome :)

## Get Started!

Ready to contribute? Here’s how to set up `datateller-org.github.io` for local
development.

1.  Fork the `datateller-org.github.io` repo on GitHub.
2.  Clone your fork locally:

```bash
$ git clone git@github.com:your_name_here/datateller-org.github.io.git
```

3.  Create an environment with `conda` and install the dependencies:

```bash
$ cd datateller-org.github.io/
$ mamba env create --file conda/dev.yaml
$ conda activate datateller-web
```

Install the dependencies:

```bash
$ poetry install --no-root
```

4.  Create a branch for local development:

```bash
git checkout -b name-of-your-bugfix-or-feature
```

Now you can make your changes locally. 5. `datateller-org.github.io` uses a set
of `pre-commit` hooks and the `pre-commit` bot to format, type-check, and
prettify the codebase. The hooks can be installed locally using:

```bash
pre-commit install
```

This would run the checks every time a commit is created locally. The checks
will only run on the files modified by that commit, but the checks can be
triggered for all the files using:

```bash
$ pre-commit run --all-files
```

If you would like to skip the failing checks and push the code for further
discussion, use the `--no-verify` option with `git commit`. 6.
`datateller-org.github.io` is tested with `pytest`. `pytest` is responsible for
testing the code, whose configuration is available in pyproject.toml. 7. Commit
your changes and push your branch to GitHub::

```bash
$ git add .
$ git commit -m “Your detailed description of your changes.”
$ git push origin name-of-your-bugfix-or-feature
```

8.  Submit a pull request through the GitHub website.

## Run jupyter-lab

All the data exploration and analysis is done using jupyter notebooks. In order
to run it, use the following command:

```bash
$ jupyter-lab --notebook-dir docs/notebooks
```

## Launch the web page locally

In order to lauch the web page locally with all the notebooks, run:

```bash
$ makim web.preview
```

## Pull Request Guidelines

Before you submit a pull request, check that it meets these guidelines:

1.  The pull request should include tests.
2.  If the pull request adds functionality, the docs should be updated. Put your
    new functionality into a function with a docstring, and add the feature to
    the list in README.rst.
3.  The pull request should work for Python 3.11.

## Release

This project uses semantic-release in order to cut a new release based on the
commit-message.

### Commit message format

**semantic-release** uses the commit messages to determine the consumer impact
of changes in the codebase. Following formalized conventions for commit
messages, **semantic-release** automatically determines the next
[semantic version](https://semver.org) number, generates a changelog and
publishes the release.

By default, **semantic-release** uses
[Angular Commit Message Conventions](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-format).
The commit message format can be changed with the `preset` or `config` options\_
of the
[@semantic-release/commit-analyzer](https://github.com/semantic-release/commit-analyzer#options)
and
[@semantic-release/release-notes-generator](https://github.com/semantic-release/release-notes-generator#options)
plugins.

Tools such as [commitizen](https://github.com/commitizen/cz-cli) or
[commitlint](https://github.com/conventional-changelog/commitlint) can be used
to help contributors and enforce valid commit messages.

The table below shows which commit message gets you which release type when
`semantic-release` runs (using the default configuration):

| Commit message                                                 | Release type     |
| -------------------------------------------------------------- | ---------------- |
| `fix(pencil): stop graphite breaking when pressure is applied` | Fix Release      |
| `feat(pencil): add 'graphiteWidth' option`                     | Feature Release  |
| `perf(pencil): remove graphiteWidth option`                    | Chore            |
| `fix(pencil)!: The graphiteWidth option has been removed`      | Breaking Release |

source:
<https://github.com/semantic-release/semantic-release/blob/master/README.md#commit-message-format>

As this project uses the `squash and merge` strategy, ensure to apply the commit
message format to the PR's title.
