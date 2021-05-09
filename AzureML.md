## Instructions to Run the Notebooks in Azure ML Studio
The steps below assume that you have an Azure account and access to the [Azure ML Studio](https://ml.azure.com/). 

### Step 0: Add a Compute Instance
In Azure ML Studio, [add a compute instance](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-manage-compute-instance?tabs=python) and pick any CPU-based instance (No GPU required). <br>
<img width="657" alt="azure1" src="https://user-images.githubusercontent.com/15709723/117559437-17463180-b03a-11eb-9e8d-d4539d1502f2.png">

Once the instance is running, open the terminal and run the steps below.<br>
<img width="804" alt="azure2" src="https://user-images.githubusercontent.com/15709723/117559439-1ca37c00-b03a-11eb-8fc3-3f9b6434275d.png">

### Step 1: Create a Conda Environment
```bash
conda create --name openvino_env python=3.6 -y
```

### Step 2: Activate the Environment
```bash
conda activate openvino_env
```

### Step 3: Clone OpenVINO Notebooks
```bash
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
```

### Step 4: Change Directory to openvino_notebooks
```bash
cd openvino_notebooks
```

### Step 5: Upgrade pip and Install Requirements
```bash
python -m pip install --upgrade pip
pip install -r requirements.txt --use-deprecated=legacy-resolver
```

### Step 6: Add openvino_env to PATH
```bash
set PATH="/anaconda/envs/openvino_env/bin;%PATH%"
```

### Step 7: Install the virtualenv Kernel in Jupyter
```bash
python -m ipykernel install --user --name openvino_env
```

### Step 8: Run the Notebooks!
To run the notebooks, click on Notebooks and refresh your Files: <br>
<img width="546" alt="azure3a" src="https://user-images.githubusercontent.com/15709723/117580814-a725c300-b0ae-11eb-93bf-007779c26075.png">

Select a notebook: <br>
<img width="266" alt="azure4" src="https://user-images.githubusercontent.com/15709723/117559447-2af19800-b03a-11eb-8bd6-8813b7a8814f.png">

Then run all cells: <br>
<img width="258" alt="azure5" src="https://user-images.githubusercontent.com/15709723/117559450-304ee280-b03a-11eb-9b79-3eedd3942474.png">