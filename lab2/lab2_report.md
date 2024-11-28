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

2. Создание сервиса для доступа на "поды"
- cоздаем сервис и пробрасываем локальный порт на порт контейнера
![Создание сервиса](https://github.com/user-attachments/assets/913d3293-f279-485f-bcbd-44a069011ef4)

- подключаемся к контейнерам через веб браузер
![Сайт](https://github.com/user-attachments/assets/f4892333-f4fa-4c05-881f-99c5e998f15d)

3. Провяем логи подов
- список подов
![Снимок экрана 2024-11-12 194009](https://github.com/user-attachments/assets/a6eca004-c66a-49b6-84df-3a69a6078f4e)

- логи подов
![Снимок экрана 2024-11-12 194111](https://github.com/user-attachments/assets/8ba22c7f-4aea-4251-a89f-35ebad12eebd)


## Схема организации контейеров и сервисов




