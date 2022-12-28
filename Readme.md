<h2>!!!!!!!!!!!!!   Задание B9.5.2    !!!!!!!!!!!!!<br>
<h3>Создайте свой docker-image и опубликуйте его в Docker Hub. Можете руководствоваться инструкцией из юнита B9.4. </h3><br>
<br>
1. Создайте Dockerfile с нужными настройками. <br>
<b>#-------------------------------------------------------- <br>
#- My Dockerfile: build Docker Image Apache Task-9.5.2  -<br>
#--------------------------------------------------------<br>
FROM ubuntu:18.04<br>
RUN apt-get -y update<br>
# Установка Apache<br>
RUN apt-get install -y apache2<br>
# Создаем тестовую страницу для Apache<br>
RUN echo 'Hello Docker Apache Task-9.5.2' > /var/www/html/index.html<br>
# Запускаем на DFOREGROUND<br>
CMD ["/usr/sbin/apache2ctl","-DFOREGROUND"]<br>
# Указываем порт<br>
EXPOSE 80<br></b>
 <br>
2. Соберите образ локально.<br>
<b>root@npm:/home/odmin/project9.5.2# docker image ls <br>
REPOSITORY   TAG          IMAGE ID       CREATED          SIZE <br>
apache       Task-9.5.2   9ec05c2800f6   12 minutes ago   203MB 
</b><br><br>
3. Запустите от него контейнер.<br>
<b>root@npm:/home/odmin/project9.5.2# docker ps <br>
CONTAINER ID   IMAGE               COMMAND                  CREATED          STATUS          PORTS                NAMES<br>
e5a144aa5f77   apache:Task-9.5.2   "/usr/sbin/apache2ct…"   12 minutes ago   Up 12 minutes   0.0.0.0:80->80/tcp   vigilant_khayyam
</b><br><br>
4. Опубликуйте свой докер-образ.<br>
<b>root@npm:/home/odmin/project9.5.2# docker push sairus/apache-task9.5.2:latest <br>
The push refers to repository [docker.io/sairus/apache-task9.5.2]<br>
ac3949e7263e: Pushed<br>
7b147ab34d7f: Pushed<br>
4912e8d533aa: Pushed<br>
45bbe3d22998: Mounted from library/ubuntu<br>
latest: digest: sha256:ba0088ad48c8a617d97d37a4237bbaab254ae8727418cb7fca23ac1c7df596b9 size: 1160<br>
</b><br><br>

5. Ссылку на Docker Hub-репозиторий опубликуйте в форме для ответа (напишите, пояснение, что это ссылка для задания B9.5.2).<br>
<b>https://hub.docker.com/repository/docker/sairus/apache-task9.5.2</b><br>
