The steps to use the OpenVINO notebooks with Anaconda are slightly different than with Python from an installer version. This is a modified installation guide for Anaconda. It has been tested with Miniconda on Windows 10. If you run into an issue with these steps, please [let us know](https://github.com/openvinotoolkit/openvino_notebooks/discussions).

On Windows, these steps should be executed inside an **Anaconda Prompt** (open Anaconda Prompt from the start menu, or press Windows-S and start typing *Anaconda*). Use the regular Anaconda Prompt, not the Powershell prompt.

### Step 1: Clone the Repository

```bash
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
```

### Step 2: Create a Conda Environment with Python 3.8

Python 3.6 and 3.7 are also supported. On Ubuntu 18, Python 3.6 is recommended, as it does not require installation of additional Python libraries.

```bash
cd openvino_notebooks
conda create -n openvino_env python=3.8
```

### Step 3: Activate the Environment

```bash
conda activate openvino_env
```

### Step 4: Install the Packages

Install OpenVINO, Jupyter, and other required packages to run the notebooks. 

```bash
# Upgrade pip to the latest version to ensure compatibility with all dependencies
# Use pip's legacy resolver to prevent dependency conflicts
python -m pip install --upgrade pip
pip install -r requirements.txt --use-deprecated=legacy-resolver
```

### Step 5: Install the virtualenv Kernel in Jupyter

```bash
python -m ipykernel install --user --name openvino_env
```

### Step 6 (conda): Add the OpenVINO library to your PATH

> This step is only for Windows. Skip this step for macOS and Linux.

Depending on your Conda installation, this step may be required at the moment for conda environments on Windows. In a future OpenVINO version this should no longer be necessary.

The command below assumes that Miniconda is installed in the default location: `C:\Users\<username>\Minoconda3`, where `<username>` is your Windows username. If you installed Anaconda, replace Miniconda3 with Anaconda3. If you installed Anaconda or Minoconda in a different location, you can run `python -c "import os,sys;print(os.path.dirname(sys.executable))"` to find the path to `openvino_env`.

Note that at the moment you need to run this command again if you open a new Anaconda Prompt to run the notebooks. You can add this folder to your PATH for every command prompt you open, by following [these steps](https://docs.microsoft.com/en-us/previous-versions/office/developer/sharepoint-2010/ee537574(v=office.14)) on Microsoft's website. Note however, that this may cause issues if you have multiple OpenVINO versions installed.

```bash
set PATH=C:\Users\<username>\Miniconda3\envs\openvino_env\Lib\site-packages\openvino\libs;%PATH%                           
```

### Step 7 (conda): Launch the Notebooks!

```bash
# To launch a single notebook
jupyter notebook <notebook_filename>

# To launch all notebooks in Jupyter Lab
jupyter lab notebooks
```
