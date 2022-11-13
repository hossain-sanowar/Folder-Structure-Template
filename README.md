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
# Steps for bash file: Basic information for command line
1. bash file_name.sh
2. echo: showing message
3. -p or --prefix: location at current directory
4. mkdir: create folder
5. touch: creating a file

```
echo "create conda environment."
conda create -p venv python==3.7 -y 
echo "conda environment created successfully"

echo "Activate conda environment."
conda activate ./venv
echo "Environment Activated"

echo "creating project structure"
mkdir app_config app_exception app_logger app_pipeline app_src aa_util config app_entity
echo "project structure created"

echo "start creating python script for each module."
touch app_entity/__init__.py app_entity/config_entity.py
echo "app configuration file created successfully"

echo "start creating app exception scripts"
touch app_exception/__init__.py app_exception/exception.py
echo "App exception script created"

echo "start creating app logger script"
touch app_logger/__init__.py app_logger/logger.py

echo "strat creating app pipeline script"
touch app_pipeline/__init__.py app_pipeline/training_pipeline.py app_pipeline/prediction_pipeline.py
echo "App pipeline script created"

echo "start creating app_src scripts."
touch app_src/__init__.py app_src/stage_00_data_ingestion.py app_src/stage_01_data_validation.py
touch app_src/stage_02_data_transformation.py app_src/stage_03_model_trainer.py app_src/ stage_04_model_evalution.py
touch app_src/stage_05_model_pusher.py
echo "App src scripts created successfully"

echo "started creating app_util scripts"
touch app_util/__init__.py app_util/util.py
echo "app util file created successfully"

echo "started creating requirements.txt file"
touch requirements.txt

echo "started created setup.py file"
touch setup.py

echo "all required python scripts created successfully"

echo "configuration file creating"

mkdir config
touch config/config.yaml

echo "configuration file created successfully"

```
