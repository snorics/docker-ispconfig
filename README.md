# docker-ispconfig
Dockerfile for ISPConfig with MariaDB database


ISPConfig is an Open source, BSD-licensed, hosting control panel for Linux, designed to manage Apache, BIND, FTP, and databases, supporting many Linux distributions.

ISPConfig 3.1.13 ( August 17, 2018 )

Official website https://www.ispconfig.org

ISPConfig 3 Screenshots https://www.ispconfig.org/ispconfig/screenshots/


Start ISPConfig

docker run --name ispconfig \
-e MAILMAN_EMAIL_HOST=test.com \
-e MAILMAN_EMAIL=test@test.com \
-e MAILMAN_PASS=pass \
-d \
-v $(pwd)/mysql:/var/lib/mysql \
-v $(pwd)/www:/var/www \
-v $(pwd)/mail:/var/mail \
-p 20:20 \
-p 21:21 \
-p 30000-30009:30000-30009 \
-p 80:80 \
-p 443:443 \
-p 8080:8080 \
-p 53:53 \
-p 2222:22 \
jerob/docker-ispconfig /start.sh
ISPConfig administration

https://your-ip:8080

ISPConfig login : admin

ISPConfig password : admin

SSH PORT : 2222 ( ssh -p 2222 user@host )

Shell access

docker exec -i -t jerob/docker-ispconfig bash

Reconfigure ISPConfig

ispconfig_update.sh

Webmail

The open source webmail solution Roundcube is available here :

http://your-ip/webmail

PHPMyAdmin

http://your-ip/phpmyadmin

MariaDB login : root

MariaDB password : pass

It is strongly recommended that you change the MariaDB and ISPConfig password as soon as possible
