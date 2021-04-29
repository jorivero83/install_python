# Installing `QueryParserVA` environment

Install `QueryParserVA` environment in order to use it inside `rmarkdown` reports. Thus, we need to install as 
dependencies `Python` and `R` + `RStudio Server`.

## 1. Installing python in ubuntu

### 1.1 Install python in ubuntu

List what already we have installed
```
ls -al /usr/bin/ | grep python
```

List all installation options of python3 we have available in ubuntu.
```
sudo apt list | grep python3
```

Install the choosed version (Python-3.9)
```
sudo apt install python39
```

Descargar y ejecutar el script get-pip.py:
```shell
curl -O https://bootstrap.pypa.io/get-pip.py 
```
```shell
python39 get-pip.py
```

Installing a package:
```shell
python39 /usr/bin/pip3.9 install boto3
```

Installing `QueryParserVA`: 
```shell
python39 -m pip install QueryParserVA-0.1.2.tar.gz
```

### 1.2 Install python from source:

Install some packages required to build:
```shell
sudo apt update; sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev
```

Download:
```shell
wget https://www.python.org/ftp/python/3.9.4/Python-3.9.4.tgz
```

Extract:
```shell
tar -xf Python-3.9.4.tgz
```

Change of dir and configurations

```shell
cd Python-3.9.4
```

```shell
./configure --enable-optimizations
```

Compilation
```shell
make -j 12
```

Install
```shell
sudo make altinstall
```
