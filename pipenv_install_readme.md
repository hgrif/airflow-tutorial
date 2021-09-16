# Airflow tutorial

我想在本机部署 airflow, 但是在 pipenv 默认安装顶级包使airflow安装时出现了一些问题, mysql只能5.7的版本, 8.0连接会出现异常(反正我连不上 mysql8.0)

## 首你需要
```bash
pip3 install pipenv
``` 

### 创建 python env  (3.7< python version >3.5)
```bash
mkdir ~/airflow
pipenv --three
或者
pipenv --python 3.5
```

### 安装 airflow
```bash
cd ~/airflow/
pipenv shell
pipenv install apache-airflow
```
如果一切顺利的话请跳过
### 如果抛出 jinja2 < 2.10.1 or Werkzeug < 0.15 , 那么你的 flask 需要降版本了
```bash
pipenv install flask==1.0
pipenv install apache-airflowecho "export AIRFLOW_HOME=~/airflow" >> ~/.bashrc
source ~/.bashrc
```

### 你需要额外安装
```bash
sudo apt-get install libmysqlclient-dev python3-dev
sudo apt-get install python3.几-dev  # 注意你的 python 版本

pipenv install apache-airflow[crypto]
pipenv install apache-airflow[mysql]
```
