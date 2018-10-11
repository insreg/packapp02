FROM gliderlabs/alpine:3.6 

RUN apk-install mysql-client

ENV MYSQL_ROOT_PASSWORD=""
ENV MYSQL_DATABASE="containerbank"

ENV MYSQL_DOCKER_SERVICE_HOST="mysql-packapp02-svc" 
ENV MYSQL_DOCKER_SERVICE_PORT="3306"

ADD initFullDB.sql /tmp/initFullDB.sql
#ADD initDB.sql /tmp/initDB.sql
#ADD populateDB.sql /tmp/populateDB.sql


#RUN "mysql -u root --password="bagabu" imhere < /tmp/imhere.sql"
#ENTRYPOINT mysql --host=172.17.0.4 --port=3306 -u root  < /tmp/initFullDB.sql
#RUN "mysql -u root  < /tmp/initFullDB.sql"
ENTRYPOINT mysql --host=$MYSQL_DOCKER_SERVICE --port=$MYSQL_DOCKER_SERVICE_PORT --verbose -u root  < /tmp/initFullDB.sql