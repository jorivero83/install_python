# Installing `QueryParserVA` environment

Install `QueryParserVA` environment in order to use it inside `rmarkdown` reports. Thus, we need to install as 
dependencies `Python` and `R` + `RStudio Server`.

## Install python in ubuntu

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