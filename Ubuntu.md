You may need to install some additional libraries on Ubuntu Linux. These steps work on a clean install of Ubuntu Desktop 20.04, and should also work on Ubuntu 18.04 and 20.10, and on Ubuntu Server.

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3-venv build-essential python3-dev
```

After this, you can follow the instructions in the [README](https://github.com/openvinotoolkit/openvino_notebooks). In step 2, make sure to type `python3 -m venv openvino_env`. `python3` will point to the right Python version. 