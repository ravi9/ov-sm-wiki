# Instructions to Run the Notebooks in Amazon SageMaker Studio
The steps below assume that you have an [AWS account](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin) and access to [Amazon SageMaker Studio](https://aws.amazon.com/sagemaker/studio/). The entire one-time setup process may take up to 15 minutes.

## Pre-requisite: Log into your Amazon SageMaker Studio Environment
![image](https://user-images.githubusercontent.com/15709723/199784049-c99abb6d-e015-4329-a459-3f5e5fe7e87e.png)
_Note: The Amazon SageMaker free tier usage per month for the first 2 months is 250 hours of ml.t3.medium instance on Studio notebook. In this example, we are using an ml.t3.medium instance.

Allow a couple minutes for your environment to spin up. You should see the following loading screen:
![image](https://user-images.githubusercontent.com/15709723/199784252-c8581c73-342a-4c70-9207-5543d7b87346.png)

Then, open a Terminal Session:
![image](https://user-images.githubusercontent.com/15709723/199784327-b0dec437-09ce-49f9-b4bf-1645353657ea.png)

## Step 1:
`conda create --name openvino_env python=3.9`

## Step 2: Activate the Environment
`conda activate openvino_env`

## Step 2b: Ensure packages are installed in the environment
`conda install ipykernel`

## Step 3: Clone OpenVINO Notebooks
`git clone https://github.com/openvinotoolkit/openvino_notebooks.git`

## Step 4: Change Directory to openvino_notebooks
`cd openvino_notebooks`

## Step 5: Upgrade pip
`python -m pip install --upgrade pip`

## Step 5b: Install Requirements
`pip install -r requirements.txt`

## Step 6: Add openvino_env to PATH
`set PATH="/anaconda/envs/openvino_env/bin;%PATH%"`

## Step 7: Run the Notebooks!
To run the notebooks, click on the top level ‘openvino_notebooks’ folder and navigate to your example:
![image](https://user-images.githubusercontent.com/15709723/199785006-aeb50c9a-2c37-43c9-b741-176e0632be14.png)

We chose the hello world notebook.

_Note: Please also make sure you are using the 'openvino_env' environment (not Python 3)._
![image](https://user-images.githubusercontent.com/15709723/199785119-d26c68e9-6876-41c7-bef8-ca29581c8e97.png)

Next, run the cells: 
![image](https://user-images.githubusercontent.com/15709723/199785179-7fb69118-5d0e-4b9d-8164-6badb0f9df23.png)
