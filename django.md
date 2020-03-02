django 

是一个 python Web框架  开源

和flask想比,django框架更重量级.功能全面

常用命令:

django-admin django  是否安装成共

django-admin startproject  pro_name  创建项目

python manage.py runserver 运行django初始化项目

python manage.py startapp app_name 启动一个django应用

python manage.py shell 进入python shell 环境

python manage.py createsuperuser 创建管理员用户

python manage.py makemigrations 模型变更成迁移文件

python manage.py migrate 运行迁移文件,把迁移文件的内容同步到数据库

django项目目录结构

models.py 定义应用模型

views.py	 视图处理

admin.py  定义admin模块管理对象的地方

apps.py 	 声明应用的地方

test.py  编写应用测试用例的地方

urls.py  管理应用路由的地方

settings.py 配置文件

创建dajngo项目创建app,在settings.py中注册app(INSTALLED_APPS),关于数据库时间比本地时间早几个小时的问题,可以设置时区,语言,改为亚洲 上海

创建模板,并设置模板,工程和应用都可以创建 ]

路由配置:准换器,path转换器

视图层:视图函数,HttpRequest对象 HttpResponse() render() redirect() 

模型层位于视图层和数据库之间  屏蔽不同的数据库支夹的差异,使开发者更加专注于逻辑的开发,提供了很多便捷的工具

模型层定义字段:数字类型:IntegerField  ,文本类型:TextField,日期类型:DateTimeField,自增:AutoField,主键:primary_key属性,

定义一个模型需要到应用中的models.py的文件中创建一个类,并且继承models.Model,然后运行数据库的两个命令,进行数据库迁移

模板系统:jinja2语法 {{变量}}{% for x in xxx%}{%endfor%}

http请求 与 Django Request对象的对应

请求方法  ----Request对象 的method属性

请求参数  ---Request对象的GET,POST等等(QueryDict当成dict来用)

请求端信息 ---  Request对象的META属性

header

cookie   ---  Request对象 的COOKIES属性

HTTP应答与Response对象的对应

状态码             status

应答内容          content

内容格式         

Response子类:JsonResponse,FileResponse等



restfull 一种架构风格 面向资源为核心

解决问题:降低开发的复杂性,提高系统的可伸缩性  

api的restful设计:  	接口/版本/

增删改查的RESTful设计

get,post,put,delete方法

GET:从服务器获取资源

POST:在服务器新建一个资源

put:在服务器更新资源

delete:从服务器删除资源

​	举个例子:  GET : 一个用户信息  /api/v1/user

- 但是无法获取具体哪一个?需要过滤

- url中的过滤信息(分页,指定)
  - 两种设计
  - GET:/api/v1.0/user/1 (后边的1不明确,需要内定)
  - GET:/api/v1.0/user?page=1
  - 还可以指定: GET:/api/v1.0/user?name=lisi

路径:接口/版本/资源类型/过滤类型

聚合api使用

注册 找想选择的接口