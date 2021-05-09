## Instructions to Run the Notebooks in Azure ML Studio
The steps below assume you have an Azure account and access to the [Azure ML Studio](https://ml.azure.com/). 

### Step 0: Add a Compute Instance
In Azure ML Studio, [add a compute instance](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-manage-compute-instance?tabs=python) and pick any CPU-based instance (No GPU required). <br>
<img width="657" alt="createnew" src="https://user-images.githubusercontent.com/15709723/117381499-12924980-ae91-11eb-9fab-5d396316d85f.png">

Once the instance is running, open the terminal and run the steps below.<br>
<img width="804" alt="final" src="https://user-images.githubusercontent.com/15709723/117381662-6f8dff80-ae91-11eb-95ad-0674375d2e10.png">

### Step 1: Create a Conda Environment
```bash
conda create --name openvino_env python=3.6 -y
```

### Step 2: Activate the Environment
```bash
conda activate openvino_env
```

### Step 3: Install pip and ipykernel
```bash
conda install pip ipykernel -y
```

### Step 4: Clone OpenVINO Notebooks
```bash
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
```

### Step 5: Change Directory to openvino_notebooks
```bash
cd openvino_notebooks
```

### Step 6: Upgrade pip and Install Requirements
```bash
python -m pip install --upgrade pip
pip install -r requirements.txt --use-deprecated=legacy-resolver
```

### Step 7: Add openvino_notebooks to PATH
```bash
set PATH="/anaconda/envs/openvino_env/bin;%PATH%"
```

### Step 8: Install the virtualenv Kernel in Jupyter
```bash
python -m ipykernel install --user --name openvino_env
```

### Step 9: Run the Notebooks!
To run the notebooks, click on Notebooks and refresh your Files: <br>
<img width="130" alt="refresh" src="https://user-images.githubusercontent.com/15709723/117379072-8893b200-ae8b-11eb-8413-6a32638a3026.png">

Select a notebook: <br>
<img width="266" alt="hello-world" src="https://user-images.githubusercontent.com/15709723/117379590-9e55a700-ae8c-11eb-9b3e-178543b82893.png">

Then run all cells: <br>
<img width="258" alt="run" src="https://user-images.githubusercontent.com/15709723/117379639-ba594880-ae8c-11eb-8913-088721ac1a79.png">