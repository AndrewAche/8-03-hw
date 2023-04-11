# Домашнее задание к занятию "8.1. Git" - `Ачеусов Андрей`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

https://github.com/AndrewAche/homework8.1/blob/main/README.md

---

### Задание 2

https://github.com/AndrewAche/homework8.1/blob/main/.gitignore


---

### Задание 3
ДОДЕЛАНО, кидаю ссылку сразу а граф
https://github.com/AndrewAche/homework8.1/network



# Домашнее задание к занятию "8.2. Что такое DevOps. СI/СD" - `Ачеусов Андрей`


### Задание 1
![image](https://user-images.githubusercontent.com/121398221/223711414-87c6a330-004b-462c-889c-2ee88311ae69.png)
![image](https://user-images.githubusercontent.com/121398221/223711432-f23e7e71-f92f-415f-a22a-4eea0f0c119f.png)
![image](https://user-images.githubusercontent.com/121398221/223711460-f827895b-a9bf-425b-9ec5-d5efb2b847b5.png)

---

### Задание 2
![image](https://user-images.githubusercontent.com/121398221/223711487-ee6040f9-45c3-4dd3-b83b-e9917708e2cc.png)
![image](https://user-images.githubusercontent.com/121398221/223711518-e5b412c1-a09e-452d-80a0-7b103ba74bbe.png)
![image](https://user-images.githubusercontent.com/121398221/223711551-e9ae72dc-002e-45b0-8c44-514e3e8d071a.png)

---

### Задание 3
Nexus поднял, создал репозиторий
![image](https://user-images.githubusercontent.com/121398221/223711649-6e507a5e-807d-4fe5-8482-32652e3a2266.png)
НЕ МОГУ СОБРАТЬ бинарник go и запушить его. Подскажите, пожалуйста, команды, в чем ошибка?
![image](https://user-images.githubusercontent.com/121398221/223712432-346588d6-a5c9-4e7c-98db-d9c618a5de5e.png)

pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git 'https://github.com/netology-code/sdvps-materials.git'}
  }
  stage('Test') {
   steps {
    sh '/usr/local/go/bin/go test'
   }
  }
  stage('Build') {
   steps {
    sh 'go build -a -installsuffix nocgo -o /app .'
   }
  }
  stage('Push') {
   steps {
    sh 'docker login ubuntu-bionic:8082 -u admin -p admin && docker push ubuntu-bionic:8082/hello-world:v$BUILD_NUMBER && docker logout'   }
  }
 }
}

![image](https://user-images.githubusercontent.com/121398221/223712285-cc975e1a-41cb-460c-8f35-dcaebeb70874.png)

АКТУАЛИЗАЦИЯ ОТ 12.03
Получилось выполнить задание
![image](https://user-images.githubusercontent.com/121398221/224513621-b1ee1572-217f-48b4-95ff-4f8982e35dfd.png)
![image](https://user-images.githubusercontent.com/121398221/224513628-5102e514-9844-4f03-bf09-bc94ef0e0979.png)
![image](https://user-images.githubusercontent.com/121398221/224513630-f474f665-6b95-470f-a906-b57b2cd90886.png)
![image](https://user-images.githubusercontent.com/121398221/224513634-f4512ddb-d4d1-4998-ab3a-986f5fbf2f2c.png)

ЕСТЬ ПРОБЛЕМА:
В самом нексусе в репозиториях не вижу изменений, т.е. самого файла outfile.go нет. Почему так? Может не туда смотрю?
![image](https://user-images.githubusercontent.com/121398221/224513752-8d6a0dab-fb5f-43ae-a809-f965f6cae6d4.png)
![image](https://user-images.githubusercontent.com/121398221/224513779-8c6e58b2-5476-4b29-9654-f065016f6f4d.png)
![image](https://user-images.githubusercontent.com/121398221/224513761-dbbe7972-bada-4d3b-bc5f-22068b91cdda.png)


АКТУАЛИЗАЦИЯ ОТ 14.03
Всё удалось. Файл появился в моём репозитории:
![image](https://user-images.githubusercontent.com/121398221/224857084-67157c28-26d0-456e-a631-fa19308ff73a.png)
Ранее ошибся с паролем. Так правильно:
![image](https://user-images.githubusercontent.com/121398221/224857176-fedb9271-4e30-49bb-b700-49d67cb31017.png)



---



# Домашнее задание к занятию "9.1. Обзор систем IT-мониторинга" - `Ачеусов Андрей`


### Задание 1

![image](https://user-images.githubusercontent.com/121398221/210910139-f7f44371-d06a-4b14-83b2-57c57ae85350.png)

---




# Домашнее задание к занятию "9.2. Система мониторинга Zabbix. Часть 1" - `Ачеусов Андрей`

### Задание 1

![image](https://user-images.githubusercontent.com/121398221/226485067-4ff7ba32-bdbe-438f-ba0a-6e35abc73522.png)
![image](https://user-images.githubusercontent.com/121398221/226485086-291bdb2c-2ce1-46ae-87cc-0bdde200e802.png)

Команды для загрузки в GitHub изменений ("классические"):
-git init
-git add README.md 
-git commit -m "some useful comment here"
-git add
-git push origin master

Но честно говоря скриншоты я вставляю через Ctrl-C, Ctrl-V на github.com  :)

---



### Задание 2

Выполнять с использованием 2-х ВМ в Облаке Яндекса:
![image](https://user-images.githubusercontent.com/121398221/226485154-88b2022c-2576-43ae-bef0-bafd735f9d9c.png)
![image](https://user-images.githubusercontent.com/121398221/226485182-6003d707-86e7-4759-987e-886030bab570.png)
![image](https://user-images.githubusercontent.com/121398221/226485201-35084d8d-7529-4e10-8527-732d4fa47b3c.png)
![image](https://user-images.githubusercontent.com/121398221/226485222-27f22574-699c-452d-881c-636d9ed1c10f.png)
![image](https://user-images.githubusercontent.com/121398221/226485240-f6da61e4-eefa-4125-9a11-663222e688f9.png)
![image](https://user-images.githubusercontent.com/121398221/226485262-0bf57b51-6c93-4ba2-a331-93bd84c8df5c.png)
![image](https://user-images.githubusercontent.com/121398221/226485286-e144bdc0-7a90-41cf-ace4-263e11977e96.png)
![image](https://user-images.githubusercontent.com/121398221/226485309-b81efec8-68ad-4235-9fba-0879342473fe.png)
![image](https://user-images.githubusercontent.com/121398221/226485326-f8fe1b3d-3483-4bc5-8de2-8cb3e59dcc10.png)

Команды для загрузки в GitHub изменений ("классические"):
-git init
-git add README.md 
-git commit -m "some useful comment here"
-git add
-git push origin master


---




# Домашнее задание к занятию "9.3. Система мониторинга Zabbix. Часть 2" - `Ачеусов Андрей`

### Задание 1

![image](https://user-images.githubusercontent.com/121398221/226768062-c577e00c-c550-4206-bc6b-803dd6b62dc3.png)

---



### Задание 3

![image](https://user-images.githubusercontent.com/121398221/226767665-5d1c5a49-ca0d-458b-9e90-1abb4187d83b.png)
![image](https://user-images.githubusercontent.com/121398221/226768157-371e6d00-e281-4bc6-93e3-1b0edc979923.png)
А вот на параметр RAM почему-то ругается...
![image](https://user-images.githubusercontent.com/121398221/226768490-dbca20c5-392a-47a7-997b-a8ebeb35c37e.png)

---


### Задание 4

![image](https://user-images.githubusercontent.com/121398221/226768898-b317d891-1e7e-4917-a6b6-126d808adf1d.png)

---




# Домашнее задание к занятию "9.4. Система мониторинга Prometheus" - `Ачеусов Андрей`

### Задание 1

![image](https://user-images.githubusercontent.com/121398221/228389738-665aa3b2-6dc1-4c73-b0d0-fdbc265f61b2.png)

---



### Задание 2

![image](https://user-images.githubusercontent.com/121398221/228389222-4162a1e2-1c95-44a0-9c62-5e2d36934b6d.png)

---


### Задание 3

![image](https://user-images.githubusercontent.com/121398221/228390390-0a6cfc3b-2ec6-4cc5-8d4b-614105a2e51c.png)
![image](https://user-images.githubusercontent.com/121398221/228390438-7649c204-1195-4dec-8709-815baf21ca01.png)

---


### Задание 4

![image](https://user-images.githubusercontent.com/121398221/228390905-075497bf-3002-4a8f-80d5-08d882aff6fd.png)

---


### Задание 5

![image](https://user-images.githubusercontent.com/121398221/228391729-83f104b2-9b60-4ecf-bf1e-da3ca016b1b7.png)
![image](https://user-images.githubusercontent.com/121398221/228391746-3d8dee59-f897-49b0-8454-6696bb6fa9e1.png)
![image](https://user-images.githubusercontent.com/121398221/228391781-3e215eca-467d-4e37-bee3-2295233560dd.png)

---





# Домашнее задание к занятию "9.5. Prometheus. Часть 2" - `Ачеусов Андрей`

### Задание 1

![image](https://user-images.githubusercontent.com/121398221/228992031-50ebdd31-1acd-4cb6-a474-b7924b22b189.png)

---



### Задание 2

![image](https://user-images.githubusercontent.com/121398221/228992159-4e771dba-6e36-4bb9-8ccf-cfbc9430b192.png)
![image](https://user-images.githubusercontent.com/121398221/228992203-e6b646dd-0235-4f71-9bd3-966e88270bad.png)

---


### Задание 3

![image](https://user-images.githubusercontent.com/121398221/228994951-408b392e-b120-4f72-9241-da601a0b2f69.png)
![image](https://user-images.githubusercontent.com/121398221/228994715-c93754fe-9fe5-4818-b4a8-e41a3e58708d.png)

---





# Домашнее задание к занятию "10.2. Кластеризация" - `Ачеусов Андрей`

### Задание 1

SMP (Symmetric Multiprocessing) – сильно связанные кластерные системы, MPP (Massive Parallel Processing) – слабо связанные.
Самой большой особенностью SMP является совместное использование всех ресурсов. Нет разницы между несколькими процессорами, равным доступом к памяти, периферийным устройствам и операционной системе. Каждый ЦП разделяет одну и ту же физическую память, и время, необходимое каждому ЦП для доступа к любому адресу в памяти, одинаково, поэтому SMP также называют унифицированной структурой доступа к памяти.
Основная особенность MPP состоит в том, что он образован несколькими серверами SMP (каждый сервер SMP называется узлом), соединенными сетью межузловых соединений. Каждый узел имеет доступ только к своим собственным локальным ресурсам (память, хранилище и т.д.), что является своего рода полным отсутствием совместного использования.

---



### Задание 2

Основное различие между слабо связанной и сильно связанной многопроцессорной системой состоит в том, что слабосвязанная система имеет распределенную память, тогда как сильносвязанная система имеет общую память.

---


### Задание 3

Преимущества кластерных систем:
● абсолютная масштабируемость,
● нет ограничений на размер узлов и кластеров,
● наращиваемая масштабируемость,
● можно расширять узлы по необходимости,
● высокий коэффициент готовности,
● отказоустойчивость, благодаря автономности узлов,
● соотношение цена/производительность,
● можно строить кластер из любых строительных блоков: чем проще и стандартнее блоки, тем дешевле обходится вычислительная мощность.

---


### Задание 4

Типов кластерных систем:
● отказоустойчивые кластеры (High-availability clusters, HA, кластеры высокой доступности);
● кластеры с балансировкой нагрузки (Load balancing clusters);
● вычислительные кластеры (High performance computing clusters, HPC);
● системы распределенных вычислений.

---


### Задание 5

Оба инструмента используются для обмена данными между приложениями, но реализуют принципиально разные модели доставки. RabbitMQ — push, когда сообщения отправляются получателям, а Kafka — pull, получатели сами достают сообщения из топика

---






# Домашнее задание к занятию "10.1. Keepalived/vrrp" - `Ачеусов Андрей`

### Задание 1

Мастер-нода:
vrrp_instance failover_test {
state MASTER
interface eth0
virtual_router_id 10
priority 110
advert_int 4
authentication {
auth_type AH
auth_pass 1111
}
unicast_peer {
10.128.0.7
}
virtual_ipaddress {
10.128.0.200 dev eth0 label eth0:vip
}
}

![image](https://user-images.githubusercontent.com/121398221/231025815-c6baae4b-ed67-4885-9b5f-15c28f7e6808.png)


Вторая нода
vrrp_instance failover_test {
state BACKUP
interface eth0
virtual_router_id 10
priority 110
advert_int 4
authentication {
auth_type AH
auth_pass 1111
}
unicast_peer {
10.128.0.24
}
virtual_ipaddress {
10.128.0.50 dev eth0 label eth0:vip
}
}

![image](https://user-images.githubusercontent.com/121398221/231026956-b555a9f3-57cc-485c-9602-b8362349f120.png)

---




