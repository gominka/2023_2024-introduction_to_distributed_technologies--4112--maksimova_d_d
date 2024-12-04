# 2024_2025-introduction_to_distributed_technologies-K4112c-maksimova_d_d
University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2023/2024
Group: K4112c
Author: Maksimova Daria Dmitrievna
Lab: Lab3
Date of create: 28.11.2024
Date of finished: 28.11.2024


# Лабораторная работа №3 "Сертификаты и "секреты" в Minikube, безопасное хранение данных."
## Описание
В данной лабораторной работе вы познакомитесь с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.

## Цель работы
Познакомиться с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.

## Ход работы

1. Создание configMap с переменными: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME

- создали манифест для configMap
  
  ![configMap](https://github.com/user-attachments/assets/19b16f67-3e44-415d-9f17-76768d528683)

- запустили minikube и применили манифест
![применения манифеста](https://github.com/user-attachments/assets/69292ed1-dff5-428d-a94b-fec5225c781b)



2. Создание replicaSet с 2 репликами контейнера, используя ранее созданный configMap

3. Включение minikube addons enable ingress и генерация TLS сертификат, импортировать сертификат в minikube.

4. Создание ingress в minikube, где указан ранее импортированный сертификат, FQDN по которому вы будете заходить и имя сервиса который вы создали ранее.

5. В hosts пропишите FQDN и IP адрес вашего ingress и попробуйте перейти в браузере по FQDN имени.

6. Вошли в веб приложение по FQDN используя HTTPS и проверили наличие сертификата.
