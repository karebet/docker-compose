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

#### membuat netword di internal docker
`docker network create --driver bridge --subnet 172.26.0.0/24 internal`

mask IP /24 memiliki 254 IP yang dapat digunakan
| Container		    | IP				      | Port |
| webproxy		    | 172.26.0.10 	  | 80:80 |
| phpinternal		  | 172.26.0.11     | 9000:9000 |
| mysqldb			    | 172.26.0.12     | 3308:330 |
| nodejavascript	| 172.26.0.13     | 3001:3000 |


ip port untuk web
| Domain		| IP				    | Port |
| abc.com 	| 172.26.0.101 	| 9001:9000 |
| def.com 	| 172.26.0.102	| 9002:9000 |
| ghi.com 	| 172.26.0.103	| 9003:9000 |
| nod.com 	| 172.26.0.104	| 3001:3000 |

##### mysql

masuk ke docker container yg sedang berjalan
`docker exec -it DOCKER_CONTAINER_ID bin/bash`

import ke database
`mysql -u root -p NAMADATABASE < /etc/mysql/NAMADATABASE.sql`

export database
`mysqldump -u root -p NAMADATABASE > /etc/mysql/NAMADATABASE.sql`
