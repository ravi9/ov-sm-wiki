## 1. Install Python and Git

You may need to install some additional libraries when using Red Hat, CentOS, Amazon Linux 2 or Fedora. These steps should work on a clean install, but please file an Issue if you have any trouble.

```
sudo yum update
sudo yum upgrade
sudo yum install python36-devel mesa-libGL
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

* If you use Anaconda or Miniconda, see the [[Conda]] wiki page.