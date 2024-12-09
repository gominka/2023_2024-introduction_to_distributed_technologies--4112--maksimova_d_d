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
Особенность Kubernetes заключается в том, что у него одновременно работают underlay и overlay сети, а управление может быть организованно различными CNI.

## Цель работы
Познакомиться с CNI Calico и функцией IPAM Plugin, изучить особенности работы CNI и CoreDNS.

## Теория
CNI Calico и функцией IPAM Plugin, изучить особенности работы CNI и CoreDNS.
## Ход работы
1. Запуск minikub с установленным плагином и режимом работы

- установили плагин, режим работы и развернули 2 ноды
  ![Установка плагина](https://github.com/user-attachments/assets/cf1b91c8-bd50-4265-bc8c-5fea16e9f552)

- проверили создание нод

  ![проверка создания нод](https://github.com/user-attachments/assets/643b8edd-932f-48bd-814b-52fcc8a7c414)

- произвели проверку работы CNI Calico

  ![![image](https://github.com/user-attachments/assets/1ce2a9f8-c4fc-4530-9981-16ba9431ef01)

2. Проверка режима IPAM 
- указывали label

  ![image](https://github.com/user-attachments/assets/a1722494-3a80-44e8-953d-21e41f867d4d)

- создали манифест IPPool 

![Снимок экрана 2024-12-03 204232](https://github.com/user-attachments/assets/5fd2e3f1-9659-435e-8477-0a31424f4a7a)

- применили манифест

  ![image](https://github.com/user-attachments/assets/39d2a493-5c98-451d-946e-fe00c82be690)

- удалили IPPool по-умолчанию

![image](https://github.com/user-attachments/assets/7c181eab-353c-4415-8dfa-bfcf5f4dcc53)

- создали IPPool'ы

![Снимок экрана 2024-12-03 201955](https://github.com/user-attachments/assets/238318b2-4130-4ce0-933d-a90428f91ef1)

3. Создание Deployment и Service

- создали манифест Deployment

  ![image](https://github.com/user-attachments/assets/052b70c7-5568-4a58-abb0-aa14eb81502b)

- создали манифест Service

  ![Снимок экрана 2024-12-03 201215](https://github.com/user-attachments/assets/5e80cd0c-34c0-4e38-a72b-f054c0d4803e)

- применили манифесты

  ![image](https://github.com/user-attachments/assets/122203b6-66cd-4c2c-bbe2-ee3bbdecfe5b)

- произвели проверку

  ![image](https://github.com/user-attachments/assets/b45fa14f-96ee-4e50-8555-cda61731f398)

  4. Подключение к контейнерам

 - пробрасываем порты
   
  ![Снимок экрана 2024-12-03 201316](https://github.com/user-attachments/assets/5ce62ddd-0e83-49ea-8738-6eaea490fc29)

- подключаемся к веб-сайту

  ![Снимок экрана 2024-12-03 201426](https://github.com/user-attachments/assets/85ca7bdd-b531-4a60-8168-2c9823c94a2e)

- отправляем эхо-запрос

  ![Снимок экрана 2024-12-03 201757](https://github.com/user-attachments/assets/a6dcd9db-7875-437f-9240-410816ef205c)

## Схема организации контейеров и сервисов

  ![image](https://github.com/user-attachments/assets/a7a9e68b-552e-42ff-bed6-a344ea78fd84)
