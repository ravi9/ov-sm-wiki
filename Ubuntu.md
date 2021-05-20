You may need to install some additional libraries on Ubuntu Linux. These steps work on a clean install of Ubuntu Desktop 20.04, and should also work on Ubuntu 18.04 and 20.10, and on Ubuntu Server.

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3-venv build-essential python3-dev git-all
```

After this, you can follow the instructions in the [README](https://github.com/openvinotoolkit/openvino_notebooks). In step 2, make sure to type `python3 -m venv openvino_env`. `python3` will point to the right Python version. 

## Troubleshooting

* On Ubuntu 18.04, `python3-dev` installs the required libraries for the system default version of Python.  On Ubuntu 18 this is Python 3.6,  on Ubuntu 20.04, Python 3.8.  If you also installed other versions of Python, it is recommended to use the full path the to system default Python: `/usr/bin/python3.6 -m venv openvino_env` on Ubuntu 18, `/usr/bin/python3.8 -m venv openvino_env` on Ubuntu 20.

* If you use Anaconda or Minoconda, see the [[Conda]] wiki page.

