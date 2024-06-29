# Personal guide for OTS students

This guide covers what **I** did during my time as a student employee.
This guide doesn't cover everything that a student employee is responsible for.

Made using [MkDocs](https://www.mkdocs.org/)  
Dependencies managed by [Poetry](https://python-poetry.org/)

Development was mostly done using MacOS.
Before you go running the commands below, make sure you have poetry installed by running `pipx install poetry`

## Clone the repo

`$ git clone https://github.com/curlyLasagna/OTS-Student-Documentation.git`

## Setting up

`$ cd OTS_StudentGuide` to go to the 

### Change python environment

`$ poetry shell`

### Installing dependencies

`$ poetry install`
  
#### How dependencies are managed

In `pyproject.toml` file, look for `tool.poetry.dependencies`.  
That is where dependencies are declared.  
To add a dependency run `poetry add <package>`

### Servin' it up at your local port

`$ mkdocs serve`

### Viewing changes

Visit the `localhost` url that `mkdocs serve` prints on the command line.
The default should be `8000`.
Can't remember nor do I care to research, but it has a hot reload feature so whenever you save changes on any one of the files it reads, the browser refreshes and outputs the new changes.  
> Be careful when you have the project saved in OneDrive. For some reason, hot reload will constantly trigger, causing the browser to continuously refresh.

### To update changes to Github Pages

Fortunately, MkDocs comes with a pretty cool command flag that deals with Github Pages

`$ mkdocs gh-deploy`

This creates a `gh-pages` branch and pushes that branch to GitHub, which is then published on GitHub Pages.  
[Click here](https://www.mkdocs.org/user-guide/deploying-your-docs/) if you want to read more information about `gh-deploy`
