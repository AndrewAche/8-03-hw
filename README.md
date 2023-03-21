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

![image](https://user-images.githubusercontent.com/121398221/226766310-6c8dab1b-0222-4b3f-92b6-c66524ef7996.png)

---



### Задание 3

![image](https://user-images.githubusercontent.com/121398221/226767665-5d1c5a49-ca0d-458b-9e90-1abb4187d83b.png)

---


### Задание 4



---

