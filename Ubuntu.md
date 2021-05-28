## 1. Install Python and Git

You may need to install some additional libraries on Ubuntu Linux. These steps work on a clean install of Ubuntu Desktop 20.04, and should also work on Ubuntu 18.04 and 20.10, and on Ubuntu Server.

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3-venv build-essential python3-dev git-all
```

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

## 4. Clone the Repository

```bash
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
cd openvino_notebooks
```

## 5. Install the Packages

This step installs OpenVINO and dependencies like Jupyter Lab. First, upgrade pip to the latest version. Then, use pip's legacy dependency resolver to avoid dependency conflicts.

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt --use-deprecated=legacy-resolver
```

## 6. Install the virtualenv Kernel in Jupyter

```bash
python -m ipykernel install --user --name openvino_env
```

### 7. Launch the Notebooks!

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

* If you use Anaconda or Minoconda, see the [[Conda]] wiki page.