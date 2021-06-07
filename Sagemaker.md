# Instructions to Run Notebooks in AWS Sagemaker  
The steps below assume that you have an AWS account and access to [Sagemaker](https://aws.amazon.com/sagemaker/). 

## Step 1: Create a Notebook Instance
### From AWS Sagemaker web portal, select the following:<br>
<img width="200" alt="Open Notebook Instances" src="https://user-images.githubusercontent.com/15709723/120951377-87a9a680-c6fd-11eb-8d63-81eadbd440cb.png"><br>

### Select the button **Create Notebook Instance**:<br>
<img width="600" alt="Create Notebook Instance" src="https://user-images.githubusercontent.com/15709723/120951380-88423d00-c6fd-11eb-8e43-e5256d2397dc.png"><br>

### Give it a name like "openvino-notebooks":<br>
> **NOTE:** The default `ml.t2.medium` instance has only 4GB of RAM. If you plan to run multiple notebooks concurrently, please select an instance with more memory. If you select the default, you may need to restart kernel when switching notebooks to free up memory.<br>

<img width="460" alt="Add name openvino-notebooks" src="https://user-images.githubusercontent.com/15709723/120951383-89736a00-c6fd-11eb-90ef-0d1041d458be.png"><br>

### The default is 5GB of storage, but 10GB or more is recommended: <br>
<img width="360" alt="Additional Options: 10GB storage" src="https://user-images.githubusercontent.com/15709723/120951385-8a0c0080-c6fd-11eb-9861-855d994abaf8.png"><br>

### If you do not have one already, add an IAM role for the notebooks:<br>
<img width="400" alt="If you do not have one yet, add an IAM role for notebooks" src="https://user-images.githubusercontent.com/15709723/120951386-8aa49700-c6fd-11eb-8e88-0ecfab4f05e1.png"><br>

### Root access is enabled by default, but it is not required for running the notebooks. Default is recommended: <br>
<img width="320" alt="Leave root access to default (optional)" src="https://user-images.githubusercontent.com/15709723/120951387-8b3d2d80-c6fd-11eb-8505-4420d5123a10.png"><br>

### To clone the OpenVINO Notebooks, provide the GitHub URL after selecting **Clone a public Git repository**: <br>
<img width="400" alt="Add OpenVINO Notebooks GitHub repo URL" src="https://user-images.githubusercontent.com/15709723/120951389-8b3d2d80-c6fd-11eb-8a2b-7be669350ca7.png"><br>

### Select **Create Notebook Instance**:<br>
<img width="200" alt="Select Create Notebook Instance" src="https://user-images.githubusercontent.com/15709723/120951390-8b3d2d80-c6fd-11eb-819f-6a115ee9d86f.png"><br>

### Click the **Open JupyterLab** Link:<br>
<img width="580" alt="Open in JupyterLab" src="https://user-images.githubusercontent.com/15709723/120951391-8bd5c400-c6fd-11eb-8be3-798e98552bca.png"><br>

### From JupyterLab, Launch a Terminal:<br>
<img width="300" alt="Launch a terminal" src="https://user-images.githubusercontent.com/15709723/120951392-8bd5c400-c6fd-11eb-9290-a512e1cf764e.png"><br>

## Step 2: Install OpenVINO Notebooks
### Copy the commands below, paste them into the terminal in JupyterLab: 
```bash
conda create --name openvino_env python=3.6 -y
source ~/anaconda3/etc/profile.d/conda.sh 
conda activate openvino_env
cd SageMaker/openvino_notebooks
python -m pip install --upgrade pip
pip install -r requirements.txt --use-deprecated=legacy-resolver
set PATH="/home/ec2-user/anaconda3/envs/openvino_env/bin;%PATH%"
python -m ipykernel install --user --name openvino_env
exit
```

## Step 3: Launch the Notebooks
Before you launch the notebooks, please refresh your browser tab where JupyterLab is running. This will make the new `openvino_env` kernel visible in JupyterLab. 

### Now, open a notebook: 


<img width="180" alt="Select openvino_env kernel" src="https://user-images.githubusercontent.com/15709723/120951395-8c6e5a80-c6fd-11eb-8e0d-6c6f54947afb.png">