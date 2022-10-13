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
- To run an image on CPU, use the following command:
```
docker run -it -p 8888:8888 openvino_notebooks
```
- To run inference on GPU, the host system is required to be Windows 10 21H2 or Windows 11, and have [Intel iGPU drivers](https://www.intel.com/content/www/us/en/download/19344/30579/intel-graphics-windows-dch-drivers.html) with version 30.0.100.9684 or above installed. Use the following command (available since 2022.1.0 release):
```
docker run -it --rm --device /dev/dxg --volume /usr/lib/wsl:/usr/lib/wsl -p 8888:8888 openvino_notebooks
```
- If your host system is Ubuntu* 20.04 then inference run inside the docker image is available for CPU, GPU, Myriad* (NCS2), HDDL targets. Default run:
```
docker run -it --device /dev/dri:/dev/dri --device-cgroup-rule='c 189:* rmw' -v /dev/bus/usb:/dev/bus/usb --rm -p 8888:8888 openvino_notebooks
```
- If you need GPU accelerator only, run the image with the following command:
```
docker run -it --device /dev/dri:/dev/dri --rm -p 8888:8888 openvino_notebooks
```
- If you need Myriad* (NCS2) accelerator only, run the image with the following command:
```
docker run -it --device-cgroup-rule='c 189:* rmw' -v /dev/bus/usb:/dev/bus/usb --rm -p 8888:8888 openvino_notebooks
```
> **NOTE:** If your host system is Ubuntu 20, follow the [Configuration Guide for the Intel® Graphics Compute Runtime for OpenCL™ on Ubuntu* 20.04](https://github.com/openvinotoolkit/docker_ci/blob/master/configure_gpu_ubuntu20.md).

> **NOTE:** If you plan to run model training notebooks, allocate additional memory by running `docker run -it -p 8888:8888 --shm-size 8G openvino_notebooks`

## Step 3: Open Browser
Copy the URL printed in the terminal and open in a browser. If it is a remote machine, replace 127.0.0.1 with the correct IP address. 
<img width="980" alt="Jupyter_URL" src="https://user-images.githubusercontent.com/15709723/127793994-355e4d29-d131-432d-a12a-b08ca6131223.png">

The Dockerfile can be used to run a local image on Windows, Linux or macOS. It is also compatible with Open Data Hub and Red Hat OpenShift Data Science. The base layer is a [UBI 8](https://catalog.redhat.com/software/containers/ubi8/5c647760bed8bd28d0e38f9f?container-tabs=overview)-based image provided by [Project Thoth](https://thoth-station.ninja/). 

> **NOTE**: When running the container on Windows and macOS, only CPU devices can be used. To access the iGPU, please install the notebooks locally following the instructions on the main [README](https://github.com/openvinotoolkit/openvino_notebooks/blob/main/README.md#-installation-guide)