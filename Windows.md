Skip Steps 1 and 2 if you already installed Python3 and Git on Windows.

## 1. Install Python

> **NOTE:** The version of Python that is available in the Microsoft Store is not recommended. It may require installation of additional packages to work well with OpenVINO and the notebooks.

* Download a Python installer from python.org. Choose Python 3.6, 3.7 or 3.8, and make sure to pick an x86-64 version. For example, this 3.7 installer: 
https://www.python.org/ftp/python/3.7.9/python-3.7.9-amd64.exe
* Double click on the installer to run it, and follow the steps in the installer. Check the box to add Python to your PATH, and to install `py`. At the end of the installer, there is an option to disable the PATH length limit. It is recommended to click this.

## 2. Install Git 

* Download [GIT](https://git-scm.com/) from [this link](https://github.com/git-for-windows/git/releases/download/v2.31.1.windows.1/Git-2.31.1-64-bit.exe)
* Double click on the installer to run it, and follow the steps in the installer.

## 3. Install the Notebooks

After installing Python 3 and Git, run each step below using _Command Prompt (cmd.exe)_, not _PowerShell_. Note: If OpenVINO is installed globally, please do not run any of these commands in a terminal where setupvars.bat is sourced.

## 4. Create a Virtual Environment

Note: If you already installed openvino-dev and activated the openvino_env environment, you can skip to [Step 6](#6-clone-the-repository). If you use Anaconda, please see the [Conda guide](https://github.com/openvinotoolkit/openvino_notebooks/wiki/Conda).

```bash
python -m venv openvino_env
```

## 5. Activate the Environment

```bash
openvino_env\Scripts\activate
```

## 6. Clone the Repository

```bash
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
cd openvino_notebooks
```

## 7. Install the Packages

This step installs OpenVINO and dependencies like Jupyter Lab. First, upgrade pip to the latest version. Then, install the required dependencies.

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## 8. Install the virtualenv Kernel in Jupyter

```bash
python -m ipykernel install --user --name openvino_env
```

## 9. Launch the Notebooks!

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

* If you have installed multiple versions of Python, use `py -3.7` when creating your virtual environment to specify a supported version (in this case 3.7).

* If you use Anaconda, you may need to add OpenVINO to your Windows PATH. See the [wiki/Conda](https://github.com/openvinotoolkit/openvino_notebooks/wiki/Conda) page.

* If you see an error about needing to install C++, please either install [Microsoft Visual C++ Redistributable](https://visualstudio.microsoft.com/downloads/#microsoft-visual-c-redistributable-for-visual-studio-2019) or use Python 3.7, which does not have this requirement.