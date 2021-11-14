# PythonAppleM1
Python setup guide for new apple M1 MacBook Pro. Solve a lot of issues due to the new apple M1 chip. Not using rosetta. 

# 1. Install python via miniforge.

## 1.1. Install anaconda

Miniforge provides a lightweight conda environment which has several advantages: Conda packaging manager, swithching python version effectively and so on. <br>
What you want to do is install miniforge for your M1 chip (arm64 architecture). 
You can download it [there](https://github.com/conda-forge/miniforge) <br>
Go for : OS X	x86_64	Miniforge3-MacOSX-x86_64

```bash
bash Miniforge3-MacOSX-x86_64.sh
```

After that, you want to add conda to your path.

## 1.2. Choose your python version 

```bash
conda search python
conda install python=3.8.12
```

> We can only access to python version equal or order to py 3.8. We recommand python 3.8.12 as it is a security version known to be reliable.

# 2. Install Pipenv

```bash
brew install pipenv
```

By doing so you are installing pipenv using, homebrew, the package manager for mac.

# 3. Using pipenv 

