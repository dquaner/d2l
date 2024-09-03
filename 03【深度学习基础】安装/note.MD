# 安装环境

## python

ref: [Download the latest version for macOS](https://www.python.org/downloads/)

已有 python 环境：

```sh
d**@localhost ~ % python -V
Python 3.11.5
d**@localhost ~ % which python
python: aliased to /Library/Frameworks/Python.framework/Versions/Current/bin/python3
```

## miniconda

ref: [Quick command line install](https://docs.conda.io/projects/miniconda/en/latest/)

```sh
mkdir -p ~/miniconda3
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh -o ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh
~/miniconda3/bin/conda init zsh
```

> init 后需要打开一个新的终端窗口。

退出 conda 环境：

```sh
conda deactivate
```

### 创建虚拟环境

```sh
d**@localhost ~ % conda env remove -n d2l-zh

Remove all packages in environment /Users/d**/miniconda3/envs/d2l-zh:

d**@localhost ~ % conda create -n d2l-zh python=3.11 pip
Collecting package metadata (current_repodata.json): done
Solving environment: done


==> WARNING: A newer version of conda exists. <==
  current version: 23.5.2
  latest version: 23.9.0

Please update conda by running

    $ conda update -n base -c defaults conda

Or to minimize the number of packages updated during conda update use

     conda install conda=23.9.0



## Package Plan ##

  environment location: /Users/d**/miniconda3/envs/d2l-zh

  added / updated specs:
    - pip
    - python=3.11


The following NEW packages will be INSTALLED:

  bzip2              pkgs/main/osx-64::bzip2-1.0.8-h1de35cc_0 
  ca-certificates    pkgs/main/osx-64::ca-certificates-2023.08.22-hecd8cb5_0 
  libffi             pkgs/main/osx-64::libffi-3.4.4-hecd8cb5_0 
  ncurses            pkgs/main/osx-64::ncurses-6.4-hcec6c5f_0 
  openssl            pkgs/main/osx-64::openssl-3.0.11-hca72f7f_2 
  pip                pkgs/main/osx-64::pip-23.2.1-py311hecd8cb5_0 
  python             pkgs/main/osx-64::python-3.11.5-hf27a42d_0 
  readline           pkgs/main/osx-64::readline-8.2-hca72f7f_0 
  setuptools         pkgs/main/osx-64::setuptools-68.0.0-py311hecd8cb5_0 
  sqlite             pkgs/main/osx-64::sqlite-3.41.2-h6c40b1e_0 
  tk                 pkgs/main/osx-64::tk-8.6.12-h5d9f67b_0 
  tzdata             pkgs/main/noarch::tzdata-2023c-h04d1e81_0 
  wheel              pkgs/main/osx-64::wheel-0.41.2-py311hecd8cb5_0 
  xz                 pkgs/main/osx-64::xz-5.4.2-h6c40b1e_0 
  zlib               pkgs/main/osx-64::zlib-1.2.13-h4dc903c_0 


Proceed ([y]/n)? y


Downloading and Extracting Packages

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate d2l-zh
#
# To deactivate an active environment, use
#
#     $ conda deactivate

d**@localhost ~ % conda activate d2l-zh                 
(d2l-zh) d**@localhost ~ % python -V                             
Python 3.11.5
(d2l-zh) d**@localhost ~ % pip -V                                
pip 23.2.1 from /Users/d**/miniconda3/envs/d2l-zh/lib/python3.11/site-packages/pip (python 3.11)
(d2l-zh) d**@localhost ~ % conda list
# packages in environment at /Users/d**/miniconda3/envs/d2l-zh:
#
# Name                    Version                   Build  Channel
bzip2                     1.0.8                h1de35cc_0  
ca-certificates           2023.08.22           hecd8cb5_0  
libffi                    3.4.4                hecd8cb5_0  
ncurses                   6.4                  hcec6c5f_0  
openssl                   3.0.11               hca72f7f_2  
pip                       23.2.1          py311hecd8cb5_0  
python                    3.11.5               hf27a42d_0  
readline                  8.2                  hca72f7f_0  
setuptools                68.0.0          py311hecd8cb5_0  
sqlite                    3.41.2               h6c40b1e_0  
tk                        8.6.12               h5d9f67b_0  
tzdata                    2023c                h04d1e81_0  
wheel                     0.41.2          py311hecd8cb5_0  
xz                        5.4.2                h6c40b1e_0  
zlib                      1.2.13               h4dc903c_0  
```

## 安装需要的包

```sh
pip install -y jupyter d2l torch torchvision
```

## 下载代码

```sh
curl https://zh-v2.d2l.ai/d2l-zh.zip
unzip d2l-zh.zip
```

## 启动 Jupyter

```sh
jupyter notebook
```

> 在 notebook 中查看幻灯片：`pip install rise`