# RDBMS setup for development environment
I have been wanting to setup sandbox environments for common databases so I could compare the feature and performance. Using chatGPT, I was able to generate docker-compose skeletons quickly for most popular databases such as MySQL, SQLServer, and Oracle databases. The parameters are tweaked accordingly.

## RDBMS
To setup the credentials for the RDBMS below, rename `.env.dist` to `.env` and place the credentials after the `=` for each line

### MySQL

```shell

	#Use -d parameter to run it as detached
	docker-compose -f docker-compose-mysql.yml up -d
```

### SQLServer

```shell
	#Using docker file
	docker-compose -f docker-compose-sqlserver.amd64.yml up -d

	docker-compose -f docker-compose-azureedge.yml up -d

```

### Oracle

```shell
	#Using docker file
	docker-compose -f docker-compose-oracle.amd64.yml up -d

```

## Run multiple RDBMS
To run all 3 RDBMS at the same time, use the following command

``` shell
	# amd64 architecture
	docker-compose -f docker-compose-rdbms-trio.amd64.yml up -d
```

## Notes
* The oracle images has been tested with `container-registry.oracle.com/database/free:latest`. For the first commit, the lastest version translates to `container-registry.oracle.com/database/free:23.2.0.0` version
* Some of the file names has CPU architecture in the file extension which means it only works on that particular architecture. When it's not provided, means it works with amd64 and arm64.


## Roadmap:
+ Add ability to execute sql
+ Add healthcheck


## Docker compose command reference
https://docs.docker.com/engine/reference/commandline/compose/