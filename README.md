# docker-compose
Doker ini berisi docker compose template
php7.2, nginx, mysql

#### Docker
##### docker up dan build
`docker-compose up --build`
##### stop dan menghapus
`docker-compose down`
##### cek container yg sedang run
`docker ps -a -f status=running`

##### menyetop dan menghapus container
`docker kill container NAMACONTAINER`

`docker rm container NAMACONTAINER`


##### mysql

masuk ke docker container yg sedang berjalan
`docker exec -it DOCKER_CONTAINER_ID bin/bash`

import ke database
`mysql -u root -p NAMADATABASE < /etc/mysql/NAMADATABASE.sql`

export database
`mysqldump -u root -p NAMADATABASE > /etc/mysql/NAMADATABASE.sql`
