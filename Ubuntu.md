## 1. Install Python, Git and GPU drivers (optional)

You may need to install some additional libraries on Ubuntu Linux. These steps work on a clean install of Ubuntu Desktop 20.04, and should also work on Ubuntu 18.04 and 20.10, and on Ubuntu Server.

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3-venv build-essential python3-dev git-all
```

If you have a CPU with an Intel Integrated Graphics Card, you can install the [Intel Graphics Compute Runtime](https://github.com/intel/compute-runtime) to enable inference on this device. The command for Ubuntu 20.04 is:

> Note: Only execute this command if you do not yet have OpenCL drivers installed.

```
sudo apt-get install intel-opencl-icd
```

Also, please follow the instructions discussed [here](https://github.com/openvinotoolkit/openvino_notebooks/discussions/540) to ensure you enabled the right permissions.  

See the [documentation](https://github.com/intel/compute-runtime) for other installation methods and instructions for other versions.

## 2. Install the Notebooks

After installing Python 3 and Git, run each step below in a terminal. Note: If OpenVINO is installed globally, please do not run any of these commands in a terminal where setupvars.sh is sourced.

## 3. Create a Virtual Environment

Note: If you already installed openvino-dev and activated the openvino_env environment, you can skip to [Step 4](#4-clone-the-repository). If you use Anaconda, please see the [Conda guide](https://github.com/openvinotoolkit/openvino_notebooks/wiki/Conda).

```bash
python3 -m venv openvino_env
```

## 4. Activate the Environment

```bash
source openvino_env/bin/activate
```

## 5. Clone the Repository

> Note: Using the `--depth=1` option for git clone reduces download size.

```bash
git clone --depth=1 https://github.com/openvinotoolkit/openvino_notebooks.git
cd openvino_notebooks
```

## 6. Install the Packages

This step installs OpenVINO and dependencies like Jupyter Lab. First, upgrade pip to the latest version. Then, install the required dependencies.

```bash
python -m pip install --upgrade pip 
pip install wheel setuptools
pip install -r requirements.txt
```

## 7. Launch the Notebooks!

To launch a single notebook, like the Monodepth notebook

```bash
jupyter notebook notebooks/201-vision-monodepth/201-vision-monodepth.ipynb
```

To launch all notebooks in Jupyter Lab

```bash
jupyter lab notebooks
```

In Jupyter Lab, select a notebook from the file browser using the left sidebar. Each notebook is located in a subdirectory within the `notebooks` directory.

## Troubleshooting

* On Ubuntu 18.04, `python3-dev` installs the required libraries for the system default version of Python.  On Ubuntu 18 this is Python 3.6,  on Ubuntu 20.04, Python 3.8.  If you also installed other versions of Python, it is recommended to use the full path the to system default Python: `/usr/bin/python3.6 -m venv openvino_env` on Ubuntu 18, `/usr/bin/python3.8 -m venv openvino_env` on Ubuntu 20.

* If you use Anaconda or Miniconda, see the [[Conda]] wiki page.

* On Ubuntu, if you see the error **"libpython3.7m.so.1.0: cannot open shared object file: No such object or directory"** please install
  the required package using `apt install libpython3.7-dev`.

* On Ubuntu, if you see the error **"OSError('sndfile library not found') OSError: sndfile library not found"** please install
  the required package using `apt install libsndfile1`.

* On Ubuntu, if the GPU device is not found, please follow the instruction here to ensure you have installed the drivers and set the right permission. (https://github.com/openvinotoolkit/openvino_notebooks/discussions/540) 