# markdownn maths cheatsheet
[Cheat Sheet: Adding Math Notation to Markdown](https://www.upyesp.org/posts/makrdown-vscode-math-notation/#:~:text=Including%20Math%20Notation%20in%20Markdown&text=Inline%20math%20notation%20is%20wrapped,signs%2C%20wrapped%20inside%20triple%20backticks.)


# account & docs
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'ml-sc'

# conda
```
conda config --show channels
conda config --add channels conda-forge

conda deactivate
conda remove --all -n ml-sc 

conda env list

#export ML_ENV=ml-sc
#conda create --name ${ML_ENV} pip python=3.11

conda create --name ml-sc pip python=3.12
source ~/miniconda3/bin/activate ml-sc

conda install jupyterlab --channel conda-forge
conda install icecream --channel conda-forge
conda install kagglehub --channel conda-forge

conda install tensorflow --channel conda-forge
conda install sklearn-pandas --channel conda-forge
conda install seaborn --channel conda-forge
conda install matplotlib --channel conda-forge

conda env create -f environment.yml

```

# [Simple Linear Regression in Python](https://medium.com/@shuv.sdr/simple-linear-regression-in-python-a0069b325bf8)

```
Path to dataset files: /home/heidless/.cache/kagglehub/datasets/karthickveerakumar/salary-data-simple-linear-regression/versions/1
--
cp -rf /home/heidless/.cache/kagglehub/datasets/karthickveerakumar/salary-data-simple-linear-regression/versions/1 ./data/

--

# python script
--
jupyter nbconvert --to python ml-train.ipynb 

--

```

# [exemplar notbook]()


