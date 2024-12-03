# 2024_2025-introduction_to_distributed_technologies-K4112c-maksimova_d_d
University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2023/2024
Group: K4112c
Author: Maksimova Daria Dmitrievna
Lab: Lab4
Date of create: 03.12.2024
Date of finished: 03.12.2024


# Лабораторная работа №4 "Сети связи в Minikube, CNI и CoreDNS"
## Описание
Это последняя лабораторная работа в которой вы познакомитесь с сетями связи в Minikube. Особенность Kubernetes заключается в том, что у него одновременно работают underlay и overlay сети, а управление может быть организованно различными CNI.

## Цель работы
Познакомиться с CNI Calico и функцией IPAM Plugin, изучить особенности работы CNI и CoreDNS.

## Ход работы
1. При запуске minikube устанавливаем плагин CNI=calico и режим работы Multi-Node Clusters

![Установка плагина](https://github.com/user-attachments/assets/cf1b91c8-bd50-4265-bc8c-5fea16e9f552)

- проверяем появление нод

![![image](https://github.com/user-attachments/assets/1ce2a9f8-c4fc-4530-9981-16ba9431ef01)
](https://github.com/user-attachments/assets/a25861a7-53c1-4be1-8615-c0a17679a8af)



Проверьте работу CNI плагина Calico и количество нод, результаты проверки приложите в отчет.

Для проверки работы Calico мы попробуем одну из функций под названием IPAM Plugin.

Для проверки режима IPAM необходимо для запущеных ранее нод указать label по признаку стойки или географического расположения (на ваш выбор).

Оригинальная инструкция для назначения IP адресов в Calico ссылка

После этого вам необходимо разработать манифест для Calico который бы на основе ранее указанных меток назначал бы IP адреса "подам" исходя из пулов IP адресов которые вы указали в манифесте.

Вам необходимо создать deployment с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и передать переменные в эти реплики: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME.

Создать сервис через который у вас будет доступ на эти "поды". Выбор типа сервиса остается на ваше усмотрение.

Запустить в minikube режим проброса портов и подключитесь к вашим контейнерам через веб браузер.

Проверьте на странице в веб браузере переменные Container name и Container IP. Изменяются ли они? Если да то почему?

Используя kubectl exec зайдите в любой "под" и попробуйте попинговать "поды" используя FQDN имя соседенего "пода", результаты пингов необходимо приложить к отчету.
