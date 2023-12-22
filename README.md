# Simple-cicd
This repo is an example of a simple CICD model that can be used for many use cases

# Setup your DBT project if one does not exist
```
python -m venv .venv
pip install -r requirements.txt
dbt-<adaptor> init
```

# Setup your DBT Cloud Production Environment.
Go to your DBT Cloud projects production environment.
* Select custom branch.
* Set this to `latest`. (This is the name of the tag that will automatically be created.)
