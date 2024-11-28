# 2024_2025-introduction_to_distributed_technologies-K4112c-maksimova_d_d
University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2023/2024
Group: K4112c
Author: Maksimova Daria Dmitrievna
Lab: Lab2
Date of create: 15.11.2024
Date of finished: 15.11.2024

# Лабораторная работа №2  "Развертывание веб сервиса в Minikube, доступ к веб интерфейсу сервиса. Мониторинг сервиса."
## Описание
В данной лабораторной работе вы познакомитесь с развертыванием полноценного веб сервиса с несколькими репликами

## Цель работы
Ознакомиться с типами "контроллеров" развертывания контейнеров, ознакомится с сетевыми сервисами и развернуть свое веб приложение.

## Теория
Развёртывание (Deployment) — это абстракция Kubernetes, которая позволяют нам управлять изменениями приложений. 

Ресурс вида Deployment позволяет автоматизировать процесс перехода от одной версии приложения к другой. 
Это делается без прерывания работы системы, а если в ходе этого процесса произойдёт ошибка,у нас будет возможность быстро вернуться к предыдущей, рабочей версии приложения.

## Ход работы
1. Cоздание deployment с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master
- скачиваем образ и проверяем его появление 
![Скачиваем образ](https://github.com/user-attachments/assets/8f73a53c-7d0b-47ab-9859-3e97a25f1389)

- создаем контейнер на основе образа и проверяем его появление
![Создаем контейнер](https://github.com/user-attachments/assets/3333a416-39e4-4897-89c5-1cfd8001b1e9)

-  запускаем minikube
![Запуск minikube](https://github.com/user-attachments/assets/5aad332f-54b6-459e-862d-a6001e087cf1)

- создаем файл манифеста
![Файл манифеста](https://github.com/user-attachments/assets/1133a93f-6b25-459c-b0aa-7ebd5bb31328)

- применяем созданный файл
![Манифест](https://github.com/user-attachments/assets/5cab8eeb-ebbc-4ffe-a837-ccfe30028249)





Создать сервис через который у вас будет доступ на эти "поды". Выбор типа сервиса остается на ваше усмотрение.

Запустить в minikube режим проброса портов и подключитесь к вашим контейнерам через веб браузер.

Проверьте на странице в веб браузере переменные REACT_APP_USERNAME, REACT_APP_COMPANY_NAME и Container name. Изменяются ли они? Если да то почему?

Проверьте логи контейнеров, приложите логи в отчёт.

Результаты лабораторной работы
Файлы с разработанными вами манифестами с расширением .yaml.

Схема организации контейеров и сервисов нарисованная вами в draw.io или Visio.

Скриншоты c результатами работы.
