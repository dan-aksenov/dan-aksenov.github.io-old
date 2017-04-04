---
layout: post
title: "Шпаргалка по работе docker"
date: 2017-04-03
---

## Установка
см. get.docker.com

* Запуск из-под непривилегированного пользователя:  
``sudo usermod -aG docker my_user``  
Перезапустить docker перезайти под пользователем.  

* Как ходить на dokerhub через прокси?
правим systemd'шный файл службы docker'а
``Environment="HTTP_PROXY=http://proxy.example.com:80/"``  

## Работа с контейнетами
* Запустить(если образа нет локально - попробует скачать)  
``sudo docker run -d centos some_cmd (/bin/bash -c some_cmd)``  

* Показать (запущенные/все) контейнеры:  
``sudo docker ps (-a)``  

* Удалить контейнер:  
``sudo docker rm cont_name``  

* Журнал контейнера:  
``sudo docker logs cont_name``  

* Запустить/остановить контейнер:  
``sudo docker stop/start cont_name``  

* Подключиться к контейнеру:  
``sudo docker exec -i -t cont_name /bin/bash``  

## Работа с образами  
* Скачать образ:  
``sudo docker pull centos``  

* Список образов:  
``sudo docker images``  

* Удалить образ:  
``sudo docker rmi imagename``  

## Сеть  
* Проброс порта:  
``docker run -d -p 8080:8080 centos``  
