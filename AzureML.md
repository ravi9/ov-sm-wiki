## Instructions to Run the Notebooks in Azure ML Studio
The steps below assume that you have an Azure account and access to the [Azure ML Studio](https://ml.azure.com/). The entire one-time setup process may take up to 20 minutes.

### Step 0: Add a Compute Instance
In Azure ML Studio, [add a compute instance](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-manage-compute-instance?tabs=python) and pick any CPU-based instance (No GPU required, but we recommend at least 4 CPU cores and 8GB of RAM). <br>
<img width="657" alt="azure1" src="https://user-images.githubusercontent.com/15709723/117559437-17463180-b03a-11eb-9e8d-d4539d1502f2.png">

Once the compute instance is running, open the terminal and then run Steps 1-8 below.
<img width="900" alt="azure2a" src="https://user-images.githubusercontent.com/15709723/117582205-b6f4d580-b0b5-11eb-9b83-eb2004ad9b19.png">


### Step 1: Create a Conda Environment
```bash
conda create --name openvino_env python=3.8 -y
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
pip install -r requirements.txt
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
<img width="558" alt="azure6a" src="https://user-images.githubusercontent.com/15709723/117580973-37640800-b0af-11eb-91ae-7194b9b4e505.png">

Note: Please also make sure you are using the 'openvino_env' environment (not Python 3). That's all :) Happy coding. 
![image](https://user-images.githubusercontent.com/1720147/162268538-f0012ff1-af5b-49ec-96df-9d176f019e0f.png)