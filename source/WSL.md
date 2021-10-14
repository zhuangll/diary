
# WSL

## 安装ubuntu20.04

安装到非系统盘目录，下载离线安装包，复制到想要安装的目录下，解压，以管理员身份运行ubuntu2004.exe

## 卸载wsl

```sh
wslconfig /l
# 从列表中选择要卸载的发行版（例如Ubuntu）并键入命令
wslconfig /u Ubuntu
```
参考链接：
https://blog.csdn.net/zhangpeterx/article/details/97616268


## 设置wsl
```sh
# 更改默认root用户登录
ubuntu1804.exe config --default-user root
# 更改默认登陆目录
# list 中 Ubuntu-20.04 条目中添加
"startingDirectory": "//wsl$/Ubuntu-20.04"
```

## ubuntu 换源

```sh
# 备份
cp /etc/apt/sources.list /etc/apt/sources.list.20211013
lsb_release -c
lsb_release -a
# 

sudo apt-get update
sudo apt-get upgrade

```
参考链接：
https://blog.csdn.net/qq_33706673/article/details/106869016


## Read The Docs 环境搭建

```sh

sudo apt-get install python3-pip

pip install sphinx sphinx-autobuild sphinx_rtd_theme
pip install recommonmark
pip install sphinx-markdown-tables
pip install Pyinstaller -i http://pypi.douban.com/simple --trusted-host pypi.douban.com
（其中的Pyinstaller是你需要下载的库或包名，根据自己需求自行更改即可）

extensions = [
    'recommonmark',
    'sphinx_markdown_tables'
]

python3 -m pip freeze > requirements.txt
```

参考链接：
https://zhuanlan.zhihu.com/p/112919704
https://zhuanlan.zhihu.com/p/264647009
https://zhuanlan.zhihu.com/p/388640347


## git

git push -u origin main

https://zhuanlan.zhihu.com/p/252505037

