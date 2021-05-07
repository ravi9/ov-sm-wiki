### Step 0: Add a Compute Instance
See instructions to [add an Azure compute instance](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-manage-compute-instance?tabs=python), then pick any CPU-based instance (No GPU required). <br>
<img width="145" alt="create" src="https://user-images.githubusercontent.com/15709723/117380053-c1348b00-ae8d-11eb-9e71-990712d04a61.png">

Once the instance is running, open the terminal and run the steps below.<br>
<img width="392" alt="terminal" src="https://user-images.githubusercontent.com/15709723/117379014-69952000-ae8b-11eb-87ca-0c6d8cd66754.png">

### Step 1: Deactivate Conda
For OpenVINO Notebooks, we recommend using virtualenv instead of Anaconda
```
conda deactivate
```

### Step 2: Install python3-venv
```
sudo apt install python3-venv
```

### Step 3: Change Directory to the Home Folder
```
cd ~
```

### Step 4: Create a Virtual Environment
```bash
python3 -m venv openvino_env
```

### Step 6: Activate the Environment
```bash
source openvino_env/bin/activate
```

### Step 7: Change Directory to Users Folder
To access notebooks from the web console, they must be in the Users folder
```
cd ~/cloudfiles/code/Users
```

### Step 8: Clone OpenVINO Notebooks
```bash
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
```

### Step 9: Change Directory to openvino_notebooks
```
cd openvino_notebooks
```

### Step 10: Install the Packages
```bash
# Upgrade pip to the latest version.
# Use pip's legacy dependency resolver to avoid dependency conflicts
python -m pip install --upgrade pip
pip install -r requirements.txt --use-deprecated=legacy-resolver
```

### Step 11: Install the virtualenv Kernel in Jupyter
```bash
python -m ipykernel install --user --name openvino_env
```

### Step 12: Run the Notebooks!
To run the notebooks, click on Notebooks and refresh your Files: <br>
<img width="130" alt="refresh" src="https://user-images.githubusercontent.com/15709723/117379072-8893b200-ae8b-11eb-8413-6a32638a3026.png">

Select a notebook: <br>
<img width="266" alt="hello-world" src="https://user-images.githubusercontent.com/15709723/117379590-9e55a700-ae8c-11eb-9b3e-178543b82893.png">

Then run all cells: <br>
<img width="258" alt="run" src="https://user-images.githubusercontent.com/15709723/117379639-ba594880-ae8c-11eb-8913-088721ac1a79.png">