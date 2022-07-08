Skip Steps 1 and 2 if you already installed Python 3 and Git on macOS.

### 1. Install Python

* Download a Python installer from python.org. Choose Python 3.7, 3.8 or 3.9. For example, this 3.7 installer: https://www.python.org/ftp/python/3.7.9/python-3.7.9-macosx10.9.pkg
* Double click on the installer to run it, and follow the steps in the installer. Please read the "Important Information" displayed during installation for information about SSL/TLS certificate validation and the running the "Install Certificates.command". These certificates are required to run some of the notebooks.

### 2. Install Git 

* Download [Git](https://git-scm.com/download/mac) from [this link](https://sourceforge.net/projects/git-osx-installer/files/git-2.31.0-intel-universal-mavericks.dmg/download?use_mirror=autoselect)
* Double click on the installer to run it, and follow the steps in the installer.

## 3. Install the Notebooks

After installing Python 3 and Git, run each step below in a terminal. Note: If OpenVINO is installed globally, please do not run any of these commands in a terminal where setupvars.sh is sourced.

## 4. Create a Virtual Environment

Note: If you already installed openvino-dev and activated the openvino_env environment, you can skip to [Step 6](#6-clone-the-repository). If you use Anaconda, please see the [Conda guide](https://github.com/openvinotoolkit/openvino_notebooks/wiki/Conda).

```bash
python3 -m venv openvino_env
```

## 5. Activate the Environment

```bash
source openvino_env/bin/activate
```

## 6. Clone the Repository

> Note: Using the `--depth=1` option for git clone reduces download size.

```bash
git clone --depth=1 https://github.com/openvinotoolkit/openvino_notebooks.git
cd openvino_notebooks
```

## 7. Install the Packages

This step installs OpenVINO and dependencies like Jupyter Lab. First, upgrade pip to the latest version. Then, install the required dependencies.

```bash
python -m pip install --upgrade pip wheel setuptools
pip install -r requirements.txt
```

## 8. Launch the Notebooks!

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

* If you have Apple M1, please see the [community discussion page](https://github.com/openvinotoolkit/openvino_notebooks/discussions/10) about using Rosetta* 2. For example, there are known issues with the use of model optimizer, and thus you may need to convert the model on x86 machines in prior.

* If you use Anaconda or Miniconda, see the [[Conda]] wiki page.