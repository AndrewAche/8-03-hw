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

---


# Домашнее задание к занятию "9.1. Обзор систем IT-мониторинга" - `Ачеусов Андрей`


### Задание 1

![image](https://user-images.githubusercontent.com/121398221/210910139-f7f44371-d06a-4b14-83b2-57c57ae85350.png)

---
