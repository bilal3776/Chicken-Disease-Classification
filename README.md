# Chicken-Disease-Classification

#project template ---

import os
from pathlib import Path
import logging  

logging.basicConfig(level=logging.INFO, format='[%(active)s]:%(message)s:')
#that is basically used for generating the logs as active will be used to measure time 
# message will be used to store the messages on the logs

project_name = 'cnn_classifier'
list_of_files = [
    '.github/workflows/.gitkeep',
    f'src/{project_name}/__init__.py',
    f'src/{project_name}/components/__init__.py',
    f'src/{project_name}/utils/__init__.py',
    f'src/{project_name}/config/__init__.py' ,
    f'src/{project_name}/config/configuration.py',
    f'src/{project_name}/pipeline/__init__.py',
    f'src/{project_name}/entity/__init__.py',
    f'src/{project_name}/constants/__init__.py',
    'config/config.yaml',
    'dvc.yaml',
    'params.yaml',
    'requirements.txt',
    'setup.py',
    'research/trials.ipynb' 
]

for filepath in list_of_files:
    filepath = Path(filepath)
    filedir, filename= os.path.split(filepath)
    #folder and filename we will receive

    if filedir != "":
        os.makedirs(filedir, exist_ok=True)
        logging.info(f'Creating directory:{filedir} for the file {filename}')

    if (not os.path.exists(filepath)) or (os.path.getsize(filename)==0):
        #here I will check whether this file exists or have some size if false then only 
        #will create a new file
        with open(filepath, 'w') as f:
            pass
        #above code is for creation of a file
            logging.info(f"Creating a new file : {filepath}")
    else:
        logging.info(f'{filename} already exists')

#now will run this in terminal