# conda
```
conda config --show channels
conda config --add channels conda-forge

conda deactivate
conda remove --all -n ml_datasci

conda env list

conda create --name ml_datasci pip python=3.11
source ~/miniconda3/bin/activate ml_datasci

conda install wheel --channel conda-forge
#conda install conda-forge::qt6-wayland
#conda uninstall qt6-wayland

conda install jupyterlab --channel conda-forge
conda install icecream --channel conda-forge
conda install kagglehub --channel conda-forge

conda install streamlit --channel conda-forge
conda install pandas --channel conda-forge
conda install numpy --channel conda-forge
conda install matplotlib --channel conda-forge
conda install seaborn --channel conda-forge

conda install tensorflow --channel conda-forge
conda install sklearn-pandas --channel conda-forge

conda env create -f environment.yml

```