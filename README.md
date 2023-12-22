# Simple continous delivery design for DbtCloud
This repo is an example of a simple CD model that can be used for many use cases in the Data space.

Analytics Engineering has traits of Software engineering but some of the common patterns in software development tend to add too much rigidity and complexity to a developers flow when dealing with the data domain.

This repo is an example of a design that seems to work really well in data and has introduced some of the safe guards we get in Software Engineering like Git Tags.

## How to contribute to the code base.
Most software applications have a develop branch and release branches.
Although this is sometimes useful for much larger projects and teams in the Data world I have noticed that a 
**simple feature branch from `main`** is more than enough for most use cases.

## Versioning and Tags.
* Versioning is simplified to an incremental build number which is then converted to a tag. e.g. v1,v2,v3
* There is a `latest` tag that always points to the latest version. (This is critical as it allows the DBT environment to always run the latest code without modification).

## Why not just use the `main` branch instead of the `latest` tag?
The reason why we go for tags is think of them as snapshots of the code that cannot be changed accidentally. A normal branch can still be manipulated and we want to protect our production jobs as much as we can.


## Setup your DBT project if one does not exist.
```
python -m venv .venv
pip install -r requirements.txt
dbt-<adaptor> init
```

## Setup your DbtCloud Pre-production Environment.
Go to your DbtCloud projects pre-production environment.
* Select custom branch.
* Set this to `main`. (This is the name of the default branch in your repo.)
![image](https://github.com/tried-and-tested-development/simple-cicd/assets/12293369/c9aa033f-0b83-4ac0-b6a0-5265fbf42f7c)

## Setup your DbtCloud Production Environment.
Go to your DbtCloud projects production environment.
* Select custom branch.
* Set this to `latest`. (This is the name of the tag that will automatically be created.)
![image](https://github.com/tried-and-tested-development/simple-cicd/assets/12293369/c9aa033f-0b83-4ac0-b6a0-5265fbf42f7c)