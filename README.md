

# RDBMS setup for development environment
Using chatGPT to quickly generate docker-compose skeletons for most popular databases such as MySQL, SQLServer, and Oracle databases. The parameters are tweaked accordingly.


Note: Some of the file names has CPU architecture in the file extension which means it only works on that particular architecture. When it's not provided, means it works with amd64 and arm64.

# TODO:
+ Add ability to execute sql
+ Add healthcheck


## MySQL

```shell

	#Use -d parameter to run it as detached
	docker-compose -f docker-compose-mysql.yml up -d
```

## SQLServer

```shell
	#Using docker file
	docker-compose -f docker-compose-sqlserver.amd64.yml up -d

	docker-compose -f docker-compose-azureedge.yml up -d

```

## Oracle

```shell
	#Using docker file
	docker-compose -f docker-compose-oracle.amd64.yml up -d

```

To run all 3 RDBMS at the same time, use the following command

docker-compose -f docker-compose-rdbms-trio.amd64.yml up -d



## Docker compose command reference
https://docs.docker.com/engine/reference/commandline/compose/