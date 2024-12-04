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

## Ход работы
1. Запуск minikub с установленным плагином и режимом работы

- установили плагин, режим работы и развернули 2 ноды
  ![Установка плагина](https://github.com/user-attachments/assets/cf1b91c8-bd50-4265-bc8c-5fea16e9f552)

- произвели проверку





- проверка работы CNI плагина Calico и количество нод

![![image](https://github.com/user-attachments/assets/1ce2a9f8-c4fc-4530-9981-16ba9431ef01)
](https://github.com/user-attachments/assets/a25861a7-53c1-4be1-8615-c0a17679a8af)


2. Проверка режима IPAM 
- указываем label

![Метки узлов](https://github.com/user-attachments/assets/c72b1b48-b52f-4345-afac-f1c043917a8f)

- создаем манифест IPPool 

![Манифест](https://github.com/user-attachments/assets/29c68aa5-2782-4b56-a54d-a2b602bcd8a8)

- установили calicoctl

![Установка](https://github.com/user-attachments/assets/da0047f6-af25-4e77-8a70-1a809378193c)

- проверяем поды по умолчанию

  ![image](https://github.com/user-attachments/assets/d7433078-46f5-4a71-acdc-9332ac9d8ca9)

- удаляем IPPool по-умолчанию

![image](https://github.com/user-attachments/assets/08ce8249-9048-485f-804f-ec09f22bcb85)


- создаем IPPool'ы

![image](https://github.com/user-attachments/assets/2798da8c-d86c-4b9c-9ac0-053c20e65356)

  
