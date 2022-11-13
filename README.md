# Folder-Structure-Template
There are three way to create the folder structure for Project templates.

# Steps for Cookiecutter
1. Create virtual env: setup.sh
```
python3 -m pip install virtualenv
echo "creating a virtual envirnment."
virtualenv -p python3 virtualenv
echo "activating virual environment"
. virtualenv/bin/activate
echo "virtrual environment activated"

```
2. Activate vitual environment
```
chmod +x setup.sh
./setup.sh
source virtualenv/bin/activate
```
3. install cookiecutter
```
pip install cookiecutter
```
4. create folder for datascience project
```
cookiecutter https://github.com/drivendata/cookiecutter-data-science
```
5. Setting some parameters
```
project_name [project_name]: cookiecutter_project
repo_name [cookiecutter_project]: cookiecutter_repo
author_name [Your name (or your organization/company/team)]: Md Sanowar Hossain
description [A short description of the project.]: This is a cookiecutter folder structure
Select open_source_license:
1 - MIT
2 - BSD-3-Clause
3 - No license file
Choose from 1, 2, 3 [1]: 1
s3_bucket [[OPTIONAL] your-bucket-for-syncing-data (do not include 's3://')]: 
aws_profile [default]: 
Select python_interpreter:
1 - python3
2 - python
Choose from 1, 2 [1]: 1
```
# Steps for py file
1. create folder like template.py
2. run below command ```python template.py```
```
import os


dirs = [
    os.path.join("data", "raw"),
    os.path.join("data","processed"),
    "notebooks",
    "saved_models",
    "src"
]

for dir_ in dirs:
    os.makedirs(dir_, exist_ok=True)
    with open(os.path.join(dir_, ".gitkeep"), "w") as f:
        pass


files = [
    "dvc.yaml",
    "params.yaml",
    ".gitignore",
    os.path.join("src","__init__.py")
]

for file_ in files:
    with open(file_, "w") as f:
        pass
```
