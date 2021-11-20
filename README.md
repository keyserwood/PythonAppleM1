# PythonAppleM1
Python setup guide for new apple M1 MacBook Pro. The M1 chip is superb, however it leads to incompatibility and for the moment I do not recommend a python setup without rosetta. Hence, all the following advice needs to have previously setup a terminal with rosetta activated. If you do not know how to this, let's check this [tutorial](https://www.youtube.com/watch?v=9W8rTTE1WEA).

# 1. Install python via miniforge.

## 1.1. Install anaconda

Miniforge provides a lightweight conda environment which has several advantages: Conda packaging manager, swithching python version effectively and so on. <br>
What you want to do is install miniforge for your M1 chip (arm64 architecture). 
You can download it [there](https://github.com/conda-forge/miniforge) <br>
Go for : OS X	x86_64	Miniforge3-MacOSX-x86_64. Open your Rosetta terminal, and place in the folder containing this file.

```bash
bash Miniforge3-MacOSX-x86_64.sh
```

Follow the installation guide, and do not forget to restart your terminal after it is completed.

## 1.2. Choose your python version 

```bash
conda search python
conda install python=3.8.12
```

> We can only access to python version equal or order to py 3.8. I recommand python 3.8.12 as it is a security version known to be reliable.

You can know check that the python version has changed.

```
python -V
```



## 1.3. A Minimal Setup for Data science.

As a data scientist, sometimes I have a csv files to analyze without wanting to create a virtual environment (even if it the pratice I use and recommend for bigger project). Big running the following command, you have all the essential package installed at once.

```
conda install pandas numpy numba matplotlib seaborn scikit-learn jupyter
```

> Using jupyter on a macbook with an Azerty Keyboard (that's the french way 🇫🇷), can be tricky especially regarding toggle comment shortcut, which I will cover at the end of this tutorial.

# 2. Pipenv - A python best practice

```bash
conda install pipenv
```

By doing so you are installing pipenv using conda. [Pipenv](https://pipenv.pypa.io/en/latest/) is the best way to integrate virtual development to your python practice. It enables you to create a minimal python environment with all the required package for your project (no more; no less🚀).

## 2.1. Create a new environment 

##### A best pratice is to setup the virtual env within your project folder 
> This will change your life when you have to deploy (like really 🤝) (on heroku for instance)
* Create .venv folder within your project [project/.venv] 

```shell
mkdir .venv
```
* Pipenv recognize this folder and settle the venv in it
* Know you can create the virtual environment


```shell
pipenv shell --python 3.8.12 #As we said python 3.8.12 is secured & reliable
```

#### Install packages

##### One package

```python
pipenv install pandas
```

> Use pipenv as pip --> Pipenv will install the package. It might take some time to lock the depencies

##### Several packages

> Store all the packages in requirements.txt file (see on git repo)

```python
pipenv install -r requirements.txt
```

> Faster, better, stronger. 

## 2.2. Work with a PipFile
* One can share its own pipenv to another by sharing PipFile. For setting, it is easy !
  * It contains all the necessary packages, and it is really useful. To be more advance use [pipfile.lock](https://pipenv.pypa.io/en/latest/basics/#example-pipfile-pipfile-lock), which handles dependencies.
##### Create again .venv folder
```shell
mkdir .venv
```
##### Launch Pipenv
```shell
pipenv install
```

## 2.4 Run back pipenv 

> Go into the folder

```
pipenv shell
```

## 2.5 Remove pipenv environement.

```
pipenv --rm
```

# 3. Jupyter notebook setup

