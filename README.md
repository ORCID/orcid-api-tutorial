# orcid-api-tutorial
MkDocs version of ORCID API workshop materials

## Pre-requisites
* [Python](https://www.python.org) 2.6 or higher
* [pip](http://pip.readthedocs.io/en/stable/installing/)
* [MkDocs](http://www.mkdocs.org/#installation)

## Start development environment
1. Clone project

        cd ~/git
        git clone git@github.com:ORCID/orcid-api-tutorial.git
  
2. Start local server

        cd orcid-api-tutorial
        mkdocs serve

3. View local site at [http://127.0.0.1:8000](http://127.0.0.1:8000)
4. Add/edit pages per http://www.mkdocs.org/user-guide/writing-your-docs (mkdocs server will reload changes automatically)

## Deploy code to Github pages
Pushes code to gh-pages branch per http://www.mkdocs.org/user-guide/deploying-your-docs/#github-pages

1. cd to local project directory

        cd ~/git/orcid-api-tutorial
  
2. Make sure you're on the master branch

        git checkout master

2. Deploy code to Github pages

        mkdocs gh-deploy

3. View live site at [https://orcid.github.io/orcid-api-tutorial](https://orcid.github.io/orcid-api-tutorial)