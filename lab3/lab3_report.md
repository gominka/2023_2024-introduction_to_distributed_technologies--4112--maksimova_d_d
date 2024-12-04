# 2024_2025-introduction_to_distributed_technologies-K4112c-maksimova_d_d
University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2023/2024
Group: K4112c
Author: Maksimova Daria Dmitrievna
Lab: Lab3
Date of create: 26.11.2024
Date of finished: 26.11.2024


# Лабораторная работа №3 "Сертификаты и "секреты" в Minikube, безопасное хранение данных."
## Описание
В данной лабораторной работе вы познакомитесь с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.

## Цель работы
Познакомиться с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.

## Теория

## Ход работы

1. Создание configMap.

- создали манифест для configMap
  
  ![configMap](https://github.com/user-attachments/assets/19b16f67-3e44-415d-9f17-76768d528683)

- запустили minikube и применили манифест
  
  ![применения манифеста](https://github.com/user-attachments/assets/69292ed1-dff5-428d-a94b-fec5225c781b)


2. Создание replicaSet с 2 репликами контейнера
- создали манифест

  ![создание манифеста](https://github.com/user-attachments/assets/c4cf58d0-3d48-4744-89fc-ebb636bb2f96)

- применили манифест

  ![применения манифеста](https://github.com/user-attachments/assets/19f420e6-0ce3-4c7b-b714-5b89783c2eab)

3. Создание Service
- создали манифест

![создание манифеста](https://github.com/user-attachments/assets/5f10bbba-959b-4d86-848e-9320e6fde79a)

- применили манифест

![применения манифеста](https://github.com/user-attachments/assets/0e610d0e-73d6-44f4-a798-be6efc667e7e)

4. Генерация TLS сертификата

- сгенерировали и подписали приватный ключ
   
 ![Генерация приватного ключа](https://github.com/user-attachments/assets/ef4d6275-36ea-4d1b-8dba-68eb95bbba30)

- подписали сертификат

 ![сертификат](https://github.com/user-attachments/assets/f7c45039-963f-4417-b2bd-ea25a8aa96ea)

5. Создание Secret

  ![Secret](https://github.com/user-attachments/assets/4e270037-f60c-4755-861f-9867505cbb8a)

6. Создание ingress

- подключение ingress в mininkub

  ![подключение ingress](https://github.com/user-attachments/assets/14c7a6c6-3ba1-448c-af04-aade6f3af757)

- создали манифест

  ![создание манифеста](https://github.com/user-attachments/assets/9bf0b19a-12e0-4694-9b4e-a90522c55aad)

- применили манифест

  ![применения манифеста](https://github.com/user-attachments/assets/1950e07f-e4c7-406e-bf48-c83a5c6877c9)

7. Подкление к Ingress

- подключение

  ![image](https://github.com/user-attachments/assets/5a39f50e-2119-450b-8d65-fa9cefe1075c)

- переход на веб-сайт

  ![Снимок экрана 2024-11-26 203155](https://github.com/user-attachments/assets/2c39fc60-95d5-4572-9a14-a9078ed6e4f5)

- сертификат

  ![Снимок экрана 2024-11-26 203225](https://github.com/user-attachments/assets/b29ec065-d9b4-45ac-9ded-daf9b1397535)
  
## Схема организации контейеров и сервисов
