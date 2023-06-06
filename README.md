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
![image](https://user-images.githubusercontent.com/121398221/231904636-704f46b4-ebb7-4c2a-bb66-b6bee1b7015a.png)
vrrp_instance test{
state MASTER
interface eth0
virtual_router_id 10
priority 110
advert_int 4
authentication
{
auth_type AH
auth_pass 1111
}
unicast_peer{
10.128.0.24
}
virtual_ipaddress{
10.128.0.200 dev eth0 label eth0:vip
}
}

![image](https://user-images.githubusercontent.com/121398221/231904329-6c0f32d1-edfc-4f84-be1b-57f435c6dac5.png)



Вторая нода
![image](https://user-images.githubusercontent.com/121398221/231904674-914b8dd1-5237-442d-899f-40b37df453b0.png)
vrrp_instance test {
state BACKUP
interface eth0
virtual_router_id 10
priority 50
advert_int 4
authentication
{
auth_type AH
auth_pass 1111
}
unicast_peer{
10.128.0.7
}
virtual_ipaddress {
10.128.0.200 dev eth0 label eth0:vip
}
}

![image](https://user-images.githubusercontent.com/121398221/231904364-aef2ba69-5216-45d2-a229-94a72865aef4.png)


---





# Домашнее задание к занятию  10.3. "Pacemaker" - `Ачеусов Андрей`

### Задание 1

Pacemaker — мозг и по совместительству менеджер ресурсов кластера. Его главная задача — достижение максимальной доступности ресурсов, которыми он управляет, и защита их от сбоев.

Во время работы кластера происходят различные события – сбой, присоединение узлов, ресурсов, переход узлов в сервисный режим и другие. Pacemaker реагирует на эти события в кластере, выполняя действия, на которые он запрограммирован., например, остановку ресурсов, перенос ресурсов и другие.
Вкратце его достоинства:

- позволяет находить и устранять сбои на уровне нод и служб;
- не зависит от подсистемы хранения: можем забыть общий накопитель, как страшный сон;
- не зависит от типов ресурсов: все, что можно прописать в скрипты, можно кластеризовать;
- поддерживает STONITH (Shoot-The-Other-Node-In-The-Head), то есть умершая нода изолируется и запросы к ней не поступают, пока нода не отправит сообщение о том, что она снова в рабочем состоянии;
- поддерживает кворумные и ресурсозависимые кластеры любого размера;
- поддерживает практически любую избыточную конфигурацию;
- может автоматически реплицировать конфиг на все узлы кластера — не придется править все вручную;
- можно задать порядок запуска ресурсов, а также их совместимость на одном узле;
- поддерживает расширенные типы ресурсов: клоны (когда ресурс запущен на множестве узлов) и дополнительные состояния (master/slave и подобное) — актуально для СУБД (MySQL, MariaDB, PostgreSQL, Oracle);
- имеет единую кластерную оболочку CRM с поддержкой скриптов.

---



### Задание 2

Corosync — программный продукт, который позволяет создавать единый кластер из нескольких аппаратных или виртуальных серверов. Corosync отслеживает и передает состояние всех участников (нод) в кластере.

Этот продукт позволяет:

- мониторить статус приложений;
- оповещать приложения о смене активной ноды в кластере;
- отправлять идентичные сообщения процессам на всех нодах;
- предоставлять доступ к общей базе данных с конфигурацией и статистикой;
- отправлять уведомления об изменениях, произведенных в базе.

---


### Задание 3

Выполнено на 2 нодах в облаке
![image](https://user-images.githubusercontent.com/121398221/235011632-6aa317ce-962a-4dd9-9c38-652e993b20c3.png)
![image](https://user-images.githubusercontent.com/121398221/235011690-e148feea-c309-431f-80c7-23ce9871bda2.png)
![image](https://user-images.githubusercontent.com/121398221/235011718-8c66e686-f5b1-4b6f-8b33-3514b8bc8f8b.png)
![image](https://user-images.githubusercontent.com/121398221/235011805-ed487274-5c95-416a-953e-c5a32cdb550c.png)
![image](https://user-images.githubusercontent.com/121398221/235011846-21b84722-db6c-4b09-82ef-f0668f8b96e3.png)
![image](https://user-images.githubusercontent.com/121398221/235011949-d24b493a-db04-4bc1-8fb9-ab4926c61d52.png)

---






# Домашнее задание к занятию  11.2. "Кеширование Redis/memcached" - `Ачеусов Андрей`

### Задание 1

Проблемы, которые решает кэширование:
● Повышение производительности, котрое достигается за счет
складывания в кэш данных, к которым чаще всего происходит
обращение;
● Увеличение скорости ответа;
● Экономия ресурсов базы данных, например, применяя
кэширование тяжелых запросов;
● Сглаживание бустов трафика. Например, во время черной
пятницы онлайн-магазины используют кэш, чтобы переживать
резкое увеличение трафика.

---



### Задание 2

![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/df4fa4b3-a8dd-4087-b701-41e935509f6b)

---



### Задание 3

Немного расширел задание, никак не успевал вывести значение за 5 сек :)
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/b8465b7e-8f8a-4e86-a33c-e68d3228c73e)
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/5373f03d-af99-4dd8-87d8-4d9f06f4e81d)

---



### Задание 4

![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/b8007a71-0e0d-46c1-8972-2bfb84bd1577)
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/5f6f6211-431c-4111-87e5-3733ca8b87dc)

---






# Домашнее задание к занятию  11.1. "Базы данных, их типы" - `Ачеусов Андрей`

### Задание 1

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.
ОТВЕТ: Реляционная СУБД. Основная особенность — надежность и неизменяемость данных, низкий риск потери информации. При обновлении данных целостность гарантирована, они заменяются в одной таблице.

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.
ОТВЕТ: MySQL Данная СУБД работает с реляционными данными и имеет свободное программное обеспечение , СУБД заслужено считается одной из самых гибких и быстродействующих, поэтому ее предлагают использовать для проектов малых и средних объемов.

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру. 
ОТВЕТ: NoSQL СУБД, например Иерархические, Сетевые, Документо-ориентированные. Как вариант MongoDB - рассчитана на работу с данными иерархической структуры. По сути, это хранилище документов без использования схематичного или табличного форматов, поэтому ее еще называют документоориентированной. СУБД MongoDB рекомендуют использовать там, где отсутствуют потребности в сложных выборках.

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.
ОТВЕТ: Графовые Особые СУБД, предназначенные для хранения информации, связанной с графами (узлы, вершины, связи между узлами). Хорошо подходят для социальных сетей, где требуется хранить связи между пользователями по разным критериям.

---



### Задание 2

1 Оператор по запросу абонента отправляет команду в банк на пополнение моб. телефона на заданную сумму
2 Банк сверяет по базе реквизиты банковского счета абонента
3 Банк проверяет наличие денежных средств на счету абонента
4 Банк перечисляет заранее установленную сумму со счета на указанный номер
5 Средства зачисляются на счет абонента
6 Подтверждение поступления денежных средств на номер телефона

---



### Задание 3

В общем, SQL-базы данных применяются там, где необходимо хранить и управлять данными структурированной природы, например, информацией о продуктах, покупателях и оформленных заказах в магазине. NoSQL-базы данных применяются, когда необходимо хранить данные неструктурированной природы, например, большие объёмы текстовых данных, изображения и видео.
SQL - лучший выбор, когда: Доступна предопределенная структура и заданные схемы; Все данные в наборе данных должны быть строго согласованы; Анализ поведенческих и настраиваемых сеансов; Разработка пользовательских панелей мониторинга; Выполнение операций объединения и сложных запросов; Необходимо выполнить многорядные транзакции.

---



### Задание 4

Можно использовать Hadoop — это программная платформа для сбора, хранения и обработки очень больших объемов данных. Проще говоря, это база данных (database), предназначенная для работы с большими данными (Big Data).Набор утилит, библиотек и фреймворк для разработки и выполнения распределенных программ, работающих на кластерах из сотен и тысяч узлов.

Из преимуществ поисковые и контекстные механизмы высоконагруженных веб-сайтов и интернет-магазинов в том числе аналитики поисковых запросов и пользовательских логов, хранение, сортировка огромных объемов данных и разбор содержимого чрезвычайно больших файлов, быстрая обработка графических данных.

---






# Домашнее задание к занятию  11.4. "Очереди RabbitMQ" - `Ачеусов Андрей`

### Задание 1

![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/64649171-6e63-4e90-9175-2f07bdc97f6f)

---



### Задание 2

![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/8f3a46b4-9e19-48ba-b015-7d73bbb13347)
Ушло:
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/b6fd2546-5f5b-4f77-a3b6-1a75a1744e71)
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/1bc9656a-06e1-44e9-a53a-f84805bc35ec)

---



### Задание 3

Делал всё на тех же ВМ в облаке. IP сменились  
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/1c7081b5-b7b8-43e1-870f-26d38f8a85ca)  
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/c5b14c14-76d6-4260-b9be-1d316c0bbaf6)  
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/f417b537-9827-4af2-9619-43868f0f0bf0)  
Первая нода остановлена  
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/1069babe-f154-4801-b9cc-4bba5182c793)  
Параметры подключения изменены: указан IP второй ноды  
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/a0978ece-a889-4718-9570-69a31b590b0e)  
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/3fce612a-42f4-48c4-a622-b1f7f42a392c)

---






# Домашнее задание к занятию  12.1. "Базы данных" - `Ачеусов Андрей`

### Задание 1

Таблица 1  
Сотрудники (  
-идентификатор, первичный ключ  serial,  
-фамилия varchar(100) not null,  
-имя varchar(100) not null,  
-отчество varchar(100) not null,  
-идентификатор структурного подразделения, внешний ключ, integer, ссылается на первичный ключ "идентификатор" таблицы "Структурные подразделения",  
-оклад int  not null,  
-дата найма date  not null,  
-идентификатор должности, внешний ключ, integer, ссылается на первичный ключ "идентификатор" таблицы "Должности",  
-идентификатор филиала smallint not null, ссылается на первичный ключ "идентификатор" таблицы "Филилалы".  
)

Таблица 2  
Структурные подразделения (  
-идентификатор, первичный ключ  serial,  
-наименование varchar(100) not null,  
-тип подразделения varchar(50) not null.  
)

Таблица 3  
Филиалы (  
-идентификатор, первичный ключ  serial,  
-идентификатор города int not null, ссылается на первичный ключ "идентификатор" таблицы "Города филиалов",  
-адрес varchar(200) not null.  
)

Таблица 4  
Проекты (  
-идентификатор, первичный ключ  serial,  
-наименование varchar(200) not null.  
)

Таблица 5  
Города филиалов (  
-идентификатор, первичный ключ  serial,  
-наименование varchar(100) not null,  
-наименование области varchar(200) not null.  
)

Таблица 6  
Должности (  
-идентификатор, первичный ключ  serial,  
-наименование varchar (100) not null.  
)

Таблица 7  
Сотрудник_Проект (   
-идентификатор сотрудника int not null, ссылается на первичный ключ "идентификатор" таблицы "Сотрудники",  
-идентификатор проекта int not null, ссылается на первичный ключ "идентификатор" таблицы "Проекты".  
)

---






# Домашнее задание к занятию  12.2. "Работа с данными (DDL/DML)" - `Ачеусов Андрей`

### Задание 1

![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/3764eeb2-23a3-4c49-9fd6-720f0a0ed658)
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/321fa93c-8cc4-4b7c-828a-72869232f077)
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/7e7f47f2-e584-4e49-86cc-8c89c6d36897)
![image](https://github.com/AndrewAche/8-03-hw/assets/121398221/4e09d625-c93f-4c5c-82b3-6378dd35e7ba)

---



### Задание 2

[ДЗ нетология_12.2.xlsx](https://github.com/AndrewAche/8-03-hw/files/11646566/_12.2.xlsx)

---

