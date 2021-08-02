To run notebooks inside a Linux-based Docker container, please use the [Dockerfile](https://github.com/openvinotoolkit/openvino_notebooks/blob/main/Dockerfile) by following the steps below. 

## Step 0: Clone the Notebooks Repo
```
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
cd openvino_notebooks
```

## Step 1: Build the Docker Image
```
docker build -t openvino_notebooks .
```

## Step 2: Run the Docker Image
```
docker run -it -p 8888:8888 openvino_notebooks
```

## Step 3: Open Browser
Copy the URL printed in the terminal and open in a browser. If it is a remote machine, replace 127.0.0.1 with the correct IP address. 
<img width="980" alt="Jupyter_URL" src="https://user-images.githubusercontent.com/15709723/127793994-355e4d29-d131-432d-a12a-b08ca6131223.png">

The Dockerfile can be used to run a local image on Windows, Linux or macOS. It is also compatible with Open Data Hub and Red Hat OpenShift Data Science. The base layer is UBI 8 provided by the Thoth project. 

> **NOTE**: When running the container on Windows and macOS, only CPU devices can be used. To access the iGPU, please install the notebooks locally following the instructions on the main [README](https://github.com/openvinotoolkit/openvino_notebooks/blob/main/README.md#-installation-guide)