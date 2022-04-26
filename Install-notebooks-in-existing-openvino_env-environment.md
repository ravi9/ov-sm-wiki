# 📚 OpenVINO Notebooks Installation in an Existing Virtual Environment

If you already installed `openvino-dev` in an `openvino_env` environment according to the [openvino-dev installation instructions](https://github.com/openvinotoolkit/openvino/blob/master/docs/install_guides/pypi-openvino-dev.md), follow these instructions to install the notebook requirements in the same environment.

If you have not installed `openvino-dev` yet, do not use this guide, but follow the main [Notebooks Installation Guide](https://github.com/openvinotoolkit/openvino_notebooks) to install both openvino-dev and the requirements for the notebooks.


## 📝 Installation Guide

> **NOTE:** If OpenVINO is installed globally, please do not run any of these commands in a terminal where setupvars.bat or setupvars.sh are sourced. For Windows, we recommend using _Command Prompt (cmd.exe)_, not _PowerShell_.

### Step 1: Activate the Environment

> **NOTE:** This step can be skipped if `openvino_env` is already activated: if you see (openvino_env) at the start of the command line.

> **NOTE:** This step should be done in the directory that contains `openvino_env`.

#### For Linux and macOS:

```bash
source openvino_env/bin/activate
```

#### For Windows:

```bash
openvino_env\Scripts\activate
```

### Step 2: Clone the Repository

> Note: Using the --depth=1 option for git clone reduces download size.

```bash
git clone --depth=1 https://github.com/openvinotoolkit/openvino_notebooks.git
```

### Step 3: Go to the Notebooks Directory
```bash
cd openvino_notebooks
```

### Step 4: Install the Packages


#### Option A: Full installation for all notebooks

The `requirements.txt` file contains the requirements for all notebooks. This includes Jupyter Lab to run the notebooks, and PyTorch and TensorFlow to convert models to OpenVINO. Installing all the requirements may take some time.

```bash
pip install -r requirements.txt
```

#### Option B: Minimal installation

To run notebooks that demonstrate OpenVINO Inference Engine, you only need to install Jupyter Notebook. This enables running the Hello World and Monodepth notebook.

```bash
pip install notebook
```

### Step 5: Launch the Notebooks!

```bash
# To launch a single notebook, for example monodepth:
jupyter notebook notebooks/201-vision-monodepth/201-vision-monodepth.ipynb

# To launch all notebooks in Jupyter Lab
jupyter lab notebooks
```

In Jupyter Lab, select a notebook from the file browser using the left sidebar. Each notebook is located in a subdirectory within the `notebooks` directory.

## 🧹 Cleaning Up

See the main [Installation Guide](https://github.com/openvinotoolkit/openvino_notebooks) about how to deactivate or delete the virtual environment.

## ⚠️ Troubleshooting

- If you get an `ImportError`, doublecheck that you installed the kernel in [Step 5](#step-5-install-the-virtualenv-kernel-in-jupyter). If necessary, choose the openvino*env kernel from the \_Kernel->Change Kernel* menu)
