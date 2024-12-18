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

### СonfigMap

[СonfigMap](https://kubernetes.io/docs/concepts/configuration/configmap/) — это объект API, используемый для хранения **неконфиденциальных данных** в парах ключ-значение, который позволяет отделять данные конфигурации/файлы от образов для обеспечения переносимости контейнерных приложений.

ConfigMaps привязывает конфигурационные файлы, аргументы командной строки, переменные окружения, номера портов и альтернативные конфигурационные артефакты к контейнерам и системным частям Pods во время выполнения.

ConfigMaps полезен для хранения и обмена неконфиденциальными, незашифрованными конфигурационными данными. 
Как и в случае с Secrets, можно создавать ConfigMaps из файлов yaml.

### Secret
[Secret](https://kubernetes.io/docs/concepts/configuration/secret/) — это объект API в Kubernetes, который содержит **конфиденциальные данные**, такие как пароль, токен или ключ, в формате base64.  

Использование метода подразумевает, что не нужно включать конфиденциальные данные в файл Pods или в Образ контейнера. 
Поскольку секреты могут быть созданы независимо от Pods, которые их используют, снижает риск раскрытия Secret (и его данных). 

Secret отделяют конфиденциальные данные от кода приложения, что упрощает управление ими и их независимое изменение. Они могут быть доступны Pods в виде переменных среды, файлов конфигурации или аргументов командной строки. 

Секретные данные не шифруются. 

### ReplicaSet
[ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/) отвечает за поддержание нужного количества реплик пода, работающих в любой момент времени, чтобы обеспечить высокую доступность и балансировку нагрузки при обработке трафика. Это достигается путем создания или удаления реплик pod по мере необходимости.

В YAML-файле ReplicaSet метки, указанные в поле должны совпадать, чтобы обеспечить правильное управление репликами pod. Несовпадающие наборы меток в обоих полях могут привести к ошибкам, что приведет к непредвиденному поведению и функциональным проблемам в наборе

### TLS
TLS (Transportation Layer Security) — криптографический протокол, предназначенный для обеспечения безопасной связи по компьютерной сети. Он гарантирует, что данные, которыми обмениваются две системы, шифруются и аутентифицируются, предотвращая подслушивание, фальсификацию и подделку. 

TLS-сертификат — это специальный сертификат, обеспечивающий работу алгоритма шифрования данных. Он помогает передавать данные в зашифрованном виде, подтверждать подлинность сайта и защищать онлайн-транзакции. 

Сертификаты TLS выдаются доверенными сторонними организациями, называемыми центрами сертификации (ЦС). Сертификат содержит информацию об удостоверении сервера, такую как доменное имя сервера и открытый ключ. 

_Проверка сертификата клиентом_
1. Когда клиент подключается к серверу по протоколу HTTPS, сервер отправляет клиенту свой сертификат для подтверждения своей личности.
2. Клиент проверяет сертификат, чтобы убедиться, что он действителен и выдан доверенным центром сертификации. Клиент также проверяет, совпадает ли доменное имя в сертификате с доменным именем сервера, к которому он подключается. Если сертификат действителен и доменное имя совпадает, клиент устанавливает защищенное соединение с сервером.

Сертификаты TLS обычно действительны в течение фиксированного периода времени, после чего срок их действия истекает и их необходимо обновить. Если сертификат скомпрометирован или стал недействительным по какой-либо причине, он должен быть отозван и заменен новым сертификатом.

### Ingress
[Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) предоставляет доступ к маршрутам HTTP и HTTPS из-за пределов кластера к службам внутри кластера. 

Ingress — это набор правил внутри кластера, предназначенных для того, чтобы входящие подключения могли достичь сервисов (Services) приложений. Доступ можно настроить, создав правила, определяющих, какие входящие подключения достигают тех или иных служб.

Входящий трафик может быть настроен для предоставления Службам внешних URL-адресов, балансировки нагрузки трафика, завершения SSL/TLS и предложения виртуального хостинга на основе имен. Ingress позволяет настроить подсистему балансировки нагрузки HTTP для приложений, работающих в Kubernetes, представленных одной или несколькими внутренними службами.

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

  ![image](https://github.com/user-attachments/assets/2646e0f5-d2ca-4ff7-a5c2-e26c81b7b211)
