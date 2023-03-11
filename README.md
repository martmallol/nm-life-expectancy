# Numerical Methods: "Life Expectancy and Linear Regression" Group Project
## Made by Oscar Álvarez, Andrés Barbuto, Sebastián Bocaccio and Martín Mallol, 2021, 2nd semester
![Life Expectancy](./life-expectancy.jpg)
## Local Setup
1. Create an empty git repo and clone this project
```
git init
git remote add origin <new-git-url>
```

2. Download the pybind` and `eigen` repos as submodules
```
git submodule init
git submodule add https://github.com/eigenteam/eigen-git-mirror
git submodule add https://github.com/pybind/pybind11
git mv eigen-git-mirror eigen
# We choose the versions of eigen and pybind
cd pybind11/ && git checkout v2.2.4 && cd ..
cd eigen && git checkout 3.3.7 && cd ..
```

3. Install requirements (*Previously, activate the virtual environment in your PC. See below.*)
```
pip install -r requirements.txt
```

4. Decompress data
```
cd data && gunzip *.gz && cd ..
```

5. Run Jupyter
```
jupyter lab
```

That's it!

## Python's virtual environment creation

### With Python3 (this one worked best for me)
```
python3 -m venv your-project-name
source your-project-name/bin/activate
```

### With pyenv
```
curl https://pyenv.run | bash
```

Then, it is suggested to add some code lines into the basrch. After that, **RESTART THE SHELL** and add the following code...
```
pyenv install 3.6.5
pyenv global 3.6.5
pyenv virtualenv 3.6.5 your-project-name
```

On the project's directory:
```
pyenv activate your-project-name
```

### With Conda
```
conda create --name your-project-name python=3.6.5
conda activate your-project-name
```

## Dependencies installment
```
pip install -r requirements.txt
```

## How to run Jupyter Notebooks
### 1st way
```
cd notebooks
jupyter lab
```

### 2nd Way
```
jupyter notebook
```

## Compilation
Execute the first cell of the `cm.ipynb` notebook.

## Overview
This project tries to analise a vast dataset provided by the World Health Organization. It attempts to compare a country's life expectancy with other attributes, searching for a correlation and explanation on why life expectancy on that country/region has that value. 

First, an exploratory analiis is made, looking for outliers or curious cases on the dataset. Then, we add new info to the provided dataset by attaching attributes such as: suicide rates, viruses, geographic location, deseases, etc. With all this information on the palm of our hand, we made multiple experiments searching for a reason on why these characteristics may impact life expectancy on a specific country or region. 

### Project's directories and files
In `data/` one can find the principal dataset and all the `.csv` files added and utilised on the project.

In `notebooks/` reside all the experiments we made.

In `src/` C++ code can be found. There, we implemented the Least Square Method. 

Finally, `Informe.pdf` is the essay. 

### Users should be able to
- Compile and run the C++ code.
- Run every Notebook in the project (experiments and testing).
- Read the essay and compare our conclusions with theirs.

### Built with
- C++
- Python
- Jupyter Notebooks
- Life Expectancy WHO (World Health Organization) dataset

### What I learnt
- Add new information to an existent dataset
- Find outliers, and similarities on different attributes of an object.
- Work with linear regression.
- Apply studentized Residuals, H Leverage, Cook Distance, influence plots.
- Utilise metrics such as $R^2$, $R^2$ adjusted and RMSE.
