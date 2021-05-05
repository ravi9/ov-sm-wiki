### Add a Compute Instance
See instructions to [add an Azure compute instance](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-manage-compute-instance?tabs=python). Pick any CPU instance. 

### Deactivate Conda
For OpenVINO Notebooks, we recommend using virtualenv instead of Anaconda
```
conda deactivate
```

### Install python3-venv
```
sudo apt install python3-venv
```

### Change Directory to the Home Folder
```
cd ~
```

### Create a Virtual Environment
```bash
python3 -m venv openvino_env
```

### Activate the Environment
```bash
source openvino_env/bin/activate
```

### Change Directory to Users Folder
To access notebooks from the web console, they must be in the Users folder
```
cd ~/cloudfiles/code/Users
```

### Clone OpenVINO Notebooks
```bash
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
```

### Change Directory to openvino_notebooks
```
cd openvino_notebooks
```

### Install the Packages
```bash
# Upgrade pip to the latest version.
# Use pip's legacy dependency resolver to avoid dependency conflicts
python -m pip install --upgrade pip
pip install -r requirements.txt --use-deprecated=legacy-resolver
```

### Install the virtualenv Kernel in Jupyter
```bash
python -m ipykernel install --user --name openvino_env
```

### Launch the Notebooks in Azure ML!
See [instructions here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-run-jupyter-notebooks) on how to run Notebooks in Azure ML Studio. 

