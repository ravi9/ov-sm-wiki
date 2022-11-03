# Instructions to Run the OpenVINO Notebooks in Amazon SageMaker Studio
The steps below assume that you have an [AWS account](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin) and access to [Amazon SageMaker Studio](https://aws.amazon.com/sagemaker/studio/). The entire one-time setup process may take up to 15 minutes.

## Pre-requisites: Launch Amazon SageMaker Studio Environment.
- Log into your Amazon SageMaker Studio Environment and Add user
<img width="720" src="https://user-images.githubusercontent.com/4837253/199801883-7bb64ad2-bb7f-4477-ace1-25111d4fd43c.png">

- Choose desired user profile name
<img width="500" src="https://user-images.githubusercontent.com/4837253/199802173-8d65c851-604b-4b92-bafa-cae86b17d1ec.png">

- Choose Jupyter Lab version 3.0
<img width="500" src="https://user-images.githubusercontent.com/4837253/199802353-14c17233-3dae-4649-bbfe-59b8a598450c.png">

- Choose remaining default setting and click Submit to Add user.
- Click "Open Studio" to Launch Amazon SageMake Studio Envirnoment.
<img width="720" src="https://user-images.githubusercontent.com/4837253/199802726-97c85732-ff25-4cdd-ad6e-d491b4ed122b.png">

**_Note:_** The Amazon SageMaker free tier usage per month for the first 2 months is 250 hours of ml.t3.medium instance on Studio notebook. In this example, we are using an ml.t3.medium instance.

- Allow a couple minutes for your environment to spin up. You should see the following loading screen:
<img width="300" src="https://user-images.githubusercontent.com/15709723/199784252-c8581c73-342a-4c70-9207-5543d7b87346.png">

- Then, Choose `Data Science 3.0` in "select a SageMaker image" drop down under **Notebooks and compute resources** 
- Then, Click on **+** on `Image Terminal` to open a terminal session:
<img width="900" src="https://user-images.githubusercontent.com/4837253/199805717-5d102d27-e92e-4426-8d14-0484fd5ba24c.png">


## OpenVINO Notebooks Setup.

- Inside the terminal, follow the steps below.

<img width="720" src="https://user-images.githubusercontent.com/4837253/199807022-3cc5dd9e-f9f0-445d-be5e-d429dc1b752c.png">

### Step 1: Install few system requirements
```sh
apt update
apt install build-essential -y
apt install libpython3.9-dev -y
apt install libgl1-mesa-glx -y
```

### Step 2: Setup OpenVINO conda environment.
```sh
conda create --name openvino_env python=3.9
conda activate openvino_env
conda install ipykernel
set PATH="/anaconda/envs/openvino_env/bin;%PATH%"
```

### Step 3: Setup OpenVINO Notebooks
```sh
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
cd openvino_notebooks
# Install OpenVINO and OpenVINO notebook Requirements
python -m pip install --upgrade pip
pip install -r requirements.txt`
```

### Step 4: Run the Notebooks!
- To run the notebooks, click on the top level ‘openvino_notebooks’ folder and navigate to your example:
<img width="400" src="https://user-images.githubusercontent.com/4837253/199810405-0f6748e1-d5f5-469e-8305-a96724dfffba.png">

- Choose Image - `Data Science 3.0`, Kernel - `Python [conda env:openvino_env]`, Instance type - your desired compute instance.

<img width="400" alt="Choose Image" src="https://user-images.githubusercontent.com/4837253/199812540-c52ea429-9d53-4bdb-aec1-a0b8616c6fcc.png">

<img width="400" alt="Choose Kernel" src="https://user-images.githubusercontent.com/4837253/199812587-20c3e360-3a31-4032-b17a-8b242d6ccc26.png">

<img width="400" alt="Choose Compute" src="https://user-images.githubusercontent.com/4837253/199812713-32074aa7-8190-43c8-815c-231542c7b286.png">


**_Note:_** Please also make sure you are using the `Python [conda env:openvino_env]` environment (not Python 3).

- Next, run the cells of the notebook. Try other notebooks to explore OpenVINO features and examples !!
