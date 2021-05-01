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

### 1.3 Copy/download `QueryParserVA` from local to server
```shell
scp -i ~/.ssh/va_key_rsa /home/jrd/Documents/parse_query_json/src/dist/QueryParserVA-0.1.2.tar.gz ubuntu@50.112.136.141:
```

Installing `QueryParserVA`: 
```shell
python39 -m pip install QueryParserVA-0.1.2.tar.gz
```

## 2. Installing R

### 2.1 Install R

```shell
# update indices
sudo apt update -qq
# install two helper packages we need
sudo apt install --no-install-recommends software-properties-common dirmngr
# import the signing key (by Michael Rutter) for these repo
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
# add the R 4.0 repo from CRAN -- adjust 'focal' to 'groovy' or 'bionic' as needed
add-apt-repository "deb https://cloud.r-project.org/bin/linux/ubuntu $(lsb_release -cs)-cran40/"
sudo apt-get update
sudo apt-get install r-base r-base-dev
# sudo apt-get install --no-install-recommends r-base
```

### 2.2 Install RStudio Server

```shell
sudo apt-get install gdebi-core
wget https://download2.rstudio.org/server/bionic/amd64/rstudio-server-1.3.1093-amd64.deb
sudo gdebi rstudio-server-1.3.1093-amd64.deb
rstudio-server status
```
