# v2Matrix
## 简介
- v2Matrix是一个能够对接v2board后台的简易客户端，相对传统工具来讲，能够直接登录注册，支付订阅，解决了用户留不下，工具无法直接变现的问题  
- 目前仅开放基础版，处于公测阶段，拿出来免费给大家用，这里是后台的源码和部署教程，完成后台部署后，可进入飞机群，拿安卓和windows的客户端

## 环境准备
- 1.安装宝塔 https://www.hostcli.com/
- 2.创建数据库
-   数据库名称：foobar
-   数据库密码：foobar
-   用户密码：foobar
- 3.导入数据库文件(见附件sql)
- 4.安装python2.7.13和pip9.0.1(centos可使用python项目管理器进行安装)
-   安装python2.7 (pip安装别用这里的)
-   https://blog.csdn.net/Auspicious_air/article/details/127800463
-   安装pip 9.0.1
-   https://blog.csdn.net/m0_72838865/article/details/126931672

## 安装第三方依赖
- pip install peewee
- pip install flask
- pip install flask-script
- pip install flask-wtf  
- pip install flask-login
- pip install Flask-SQLAlchemy==2.1
- pip install apscheduler
- pip install PyJWT
- pip install jason
- pip install --upgrade pip
- pip install html
- pip install requests
- pip install pymysql

## 系统文件替换
- 1.替换文件__init__.py 路径：
-   python2.7/site-packages/flask_sqlalchemy/__init__.py	
- 2.替换文件impl.py 路径：
-   python2.7/site-packages/sqlalchemy/pool/impl.py
- 3.替换文件util.py 路径：
-   python2.7/site-packages/apscheduler/util.py
- 备注：具体目录与python的安装目录有关，可以在根目录搜索flask_sqlalchemy，sqlalchemy，apscheduler进行查找。
  
## 运行
- 1.宝塔中打开端口：3306,5000
- 2.进入到你工程路径下flask-saas-platform-main，运行python run_app_dev.py 或后台运行nohup python run_app_dev.py &   
-   查看后台进程指令：ps aux |grep python 
  
## 其他
### 系统参数配置
```
编辑`config.py`， 修改SECRET_KEY及MySQL数据库相关参数
SECRET_KEY = os.environ.get('SECRET_KEY') or 'your-secret'
DB_HOST = '127.0.0.1'
DB_USER = 'foobar'
DB_PASSWD = 'foobar'
DB_DATABASE = 'foobar'
```

## 后台功能
- 1.系统配置(首页):配置你的面板地址
- 2.广告配置
- 3.套餐配置：
-   1).套餐1名字，套餐2名字，其中的1234对应着客户端4个套餐选项的位置
-   2).套餐名字和付款周期 共同决定这个位置对应你面板上的哪个套餐
-   3).套餐名字

## 相关学习文档
- [http://flask.pocoo.org](http://flask.pocoo.org)
- [https://flask-login.readthedocs.io](https://flask-login.readthedocs.io)
- [https://flask-script.readthedocs.io](https://flask-script.readthedocs.io)
- [https://flask-wtf.readthedocs.io](https://flask-wtf.readthedocs.io)
- [http://docs.peewee-orm.com](http://docs.peewee-orm.com)
- [https://almsaeedstudio.com/preview](https://almsaeedstudio.com/preview)

## 后台截图
![后台登陆](https://user-images.githubusercontent.com/130766519/232076003-18d55b5e-ee17-4b4d-a80b-9dd1a11dc74f.PNG)

![后台广告配置](https://user-images.githubusercontent.com/130766519/232076018-5becf129-34ae-4c91-81ec-ae72038aaa55.JPG)

![后台套餐配置](https://user-images.githubusercontent.com/130766519/232076042-c911c3a2-867e-423a-8fc1-e88490bef449.JPG)























