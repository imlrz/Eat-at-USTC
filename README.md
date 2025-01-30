# 初步环境设置
## 数据库配置
打开myproj\settings.py,找到如下的代码块，改成你自己希望连接的数据库
```
DATABASES = {
    'default': {
        # 自己的数据库
    }
}
```

## 环境创建
### 先到达manage.py所在的目录下
### 创建虚拟环境并启动（这里使用conda进行创建）
这里使用的python版本为3.11.4
创建一个名字为"xxx"的虚拟环境xxx
` conda create -n xxx python==3.11.4 `
激活该环境
`conda activate proj`
### 安装一些需要的包
```
pip install django==4.1
pip install pillow
pip install mysqlclient
```
### 数据库迁移、创建超级管理者、启动runserver
注意，下面的代码应该是一行一行的复制到conda中运行的，python manage.py createsuperuser后需要根据conda命令行中给出的提示填写相关内容
```    
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```
最后手动将UPDATE_GRADE.sql文件导入数据库中即可

一般主页：127.0.0.1:8000/
超级管理员界面：127.0.0.1:8000/admin