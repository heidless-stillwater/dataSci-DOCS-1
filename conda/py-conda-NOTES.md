
# conda
```
conda config --show channels
conda config --add channels conda-forge

conda deactivate
conda remove --all -n ai_neural

conda env list

#conda create --name ml_datasci pip python=3.11
#source ~/miniconda3/bin/activate ml_datasci

#conda create --name ai_env_0 pip python=3.11
source ~/miniconda3/bin/activate ai_env_0

#conda create --name ai_neural pip python=3.9
#source ~/miniconda3/bin/activate ai_neural

conda env create -f environment.yml

# pip compatible requirements.txt
pip install --upgrade pip
pip list --format=freeze > requirements.txt

```

# install list
source ~/miniconda3/bin/activate ai_env

conda install streamlit
conda install tensorflow

conda install pandas
conda install matplotlib
conda install plotly

conda install jupyterlab
conda install icecream
conda install logging

#conda install kagglehub

#pip install numpy
#pip install seaborn
#pip install sklearn-pandas








python -m venv venv
source venv/bin/activate

pip install wheel
#pip install pip-forge::qt6-wayland
#pip uninstall qt6-wayland

pip install jupyterlab
pip install icecream
pip install kagglehub

pip install streamlit
pip install pandas
pip install numpy
pip install matplotlib
pip install seaborn

pip install tensorflow
pip install sklearn-pandas
