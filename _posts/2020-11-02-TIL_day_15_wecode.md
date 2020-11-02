---
title: "TIL day 15 (Nov 2)"
date: 2020-11-02
categories: wecode TIL python django github mysql database
toc: true
toc_sticky: true
---

# Django C.R.U.D 
  
## What did I study?
  
Used Django web framework and write the** Model**.
  
Will make tables at databases through ORM
  
and learned how to Create, Read, Update, Delete data
  below image will help to understand.
  
![](https://images.velog.io/images/noahshin__11/post/612e7f21-39f8-40d6-8d3f-a04e555dc7d8/image.png)
  
#### What I have to focus on?
  
1. Understanding of data flow on (Server - Database) 
2. Understanding how to write Models among MTV via 3rd generation web standard
3. Practice and understanding of QUERYSET API
  
First of all,
  
I need to set up the Web Application Server & Database
  
1. Install Virtual Environment through Miniconda 3,   
2. Install MySQL  
3. Install django on miniconda3  
4. Install pip (Python Install Package) for project
  
$pip install django
$pip install mysqlclient
  
5. Create Django project & application
  
$ django-admin startproject starbucks_project  <<<< project name 
cd starbucks_project  
$ python manage.py startapp products    <<<<< app name
  ![](https://images.velog.io/images/noahshin__11/post/eb2bc676-c772-4c3d-80f5-75d9d9d20269/image.png)
  
when I created project, it had same name of folder in it so I changed the name of the first folder.
  (Just letting you know)
  
6. set the settings.py,,,,, in setting.py  
Allow IP by
  ![](https://images.velog.io/images/noahshin__11/post/aff2e504-e4ce-4b1a-8f96-0e7b6c9a3f72/image.png)
  
7. Turn into commentary that you don't use this practice,,, such as admin, csrf, auth
  
![](https://images.velog.io/images/noahshin__11/post/8c84aeef-8b9b-40e0-881a-d64da73b5fc1/image.png)
  
The Most important thing that you should not forget:
  You need to change starbucks(project name)/urls.py as below
```python
from django.urls import path
  urlpatterns = [
]
```
  8. create Database
  ```python
mysql.server start
  myql -u root -p
  mysql create database "name" chracter set utf8mb4 collate utf8mb4_general_ci;
```
  9. Link with MySQL Database
  ![](https://images.velog.io/images/noahshin__11/post/d85c35ed-e3a4-4c4f-a092-98df3523ab30/image.png)
  10. Write products/models.py
  
```python
from django.db import models
  class Menu(models.Model):
		name = models.CharField(max_length=20)
  class Category(models.Model):
		name = models.CharField(max_length=20)
		menu = models.ForeignKey('Menu', on_delete=models.CASCADE)
  class Product(models.Model):
		name  = models.CharField(max_length=100)
		price = models.IntegerField()
		menu = models.ForeignKey('Category', on_delete=models.CASCADE)
```





