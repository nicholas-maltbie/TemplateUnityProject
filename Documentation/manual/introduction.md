# Template Unity Project Introduction

Introduction to Nick Maltbie's Template Unity Project.

## Usage

This project is intended to be used as a base for creating
a unity project with git and GitHub.

* Basic unity project configuration for git.
* Basic github actions for uploading the project to a github pages site.
* Automated testing validation in PlayMode and EditMode.

### Rename Script

There is a script file at `Assets\Editor\RenameAssets.cs` that
has steps to rename all the files in the project associated
with the template project (like the project name, website, company
name, etc...) as well as regenerate the project asset GUIDs
for unity to avoid asset collisions in multiple uses of
the template.

See the [Rename Script](rename_script.md) page for further details.

### Automated GitHub actions

There are many automated github actions in
the project stored at `.github/actions`

| Workflow | Description |
|----------|-------------|
| `build-verification.yml` | Verify that project can properly. |
| `deploy.yml` | Builds and deploys project to the github pages environment. |
| `format.yml` | Linting with `markdownlint`, `dotnet format`, and `docfx`. |
| `tests-validation.yml` | Runs test validation on the project. |

Please look at the workflow files for further details and
documentation on the github repo.

There are some global configuration variables all fo the workflows
in the file `.github/variables/projectconfig.env`.

And there are a few shared workflow scripts under `.github/actions` folder
including:

* `git-lfs-cache` -
    Loads files from `git-lfs` using a cache from the list of lfs files.
* `setvars` -
    Loads variables from the `projectconfig.env` file.
* `unity-library-cache` -
    Caches the unity library folders as part of github build.

See the [GitHub Actions](github_actions.md) page for further details.

### Documentation Template Website

In addition, this project includes a documentation website template
that you can customize for your project. This website is part
of the documentation template using docfx. This includes scripts
to create the documentation website with docfx tool that includes
API documentation. See the
[Documentation Website](documentation_website.md) page for further details.
