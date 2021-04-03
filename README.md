# springboot-liquibase-generator-template-postgresql

## Prerequisite:
* Make sure to install maven (https://maven.apache.org/install.html)
* Make sure to install postgresql

## Install PostgreSQL local
- Open up the Terminal and install `postgresql` with `brew`
```
$ brew install postgresql
```
- Start postgresql
```
$ brew services start postgresql
```
- To stop postgresql anytime
```
$ brew services stop postgresql
```
- Login to postgresql
```
$ psql postgres
postgres=#
```
- Create account to be use
```
postgres=# CREATE ROLE postgreslocal WITH LOGIN PASSWORD 'postgreslocal';
postgres=# ALTER ROLE postgreslocal CREATEDB;
postgres=# ALTER ROLE postgreslocal SUPERUSER;
postgres=# \q
```

- Create test database `test_liquibase`
```
$ psql -d postgres -U postgreslocal
postgres=> CREATE DATABASE test_liquibase;
```
- Checkout the project in your chosen local directory
```
$ mkdir dev
$ cd dev
$ git clone https://github.com/arisculala/springboot-liquibase-generator-template-postgresql.git
```

- Browse inside the project directory and run liquibase
```
$ cd springboot-liquibase-generator-template-postgresql
$ mvn liquibase:update
```

- You should be able to see success build message
```
[INFO] Scanning for projects...
[INFO]
[INFO] --< com.liquibase.generator.template:springboot-liquibase-generator-template >--
[INFO] Building Springboot Liquibase Generator Template 0.0.1-SNAPSHOT
[INFO] --------------------------------[ war ]---------------------------------
[INFO]
[INFO] --- liquibase-maven-plugin:4.2.2:update (default-cli) @ springboot-liquibase-generator-template ---
[INFO] ------------------------------------------------------------------------
[project, pluginDescriptor]
[INFO]
[INFO]
[INFO] Liquibase Community 4.2.2 by Datical
[INFO] ####################################################
##   _     _             _ _                      ##
##  | |   (_)           (_) |                     ##
##  | |    _  __ _ _   _ _| |__   __ _ ___  ___   ##
##  | |   | |/ _` | | | | | '_ \ / _` / __|/ _ \  ##
##  | |___| | (_| | |_| | | |_) | (_| \__ \  __/  ##
##  \_____/_|\__, |\__,_|_|_.__/ \__,_|___/\___|  ##
##              | |                               ##
##              |_|                               ##
##                                                ##
##  Get documentation at docs.liquibase.com       ##
##  Get certified courses at learn.liquibase.com  ##
##  Free schema change activity reports at        ##
##      https://hub.liquibase.com                 ##
##                                                ##
####################################################
Starting Liquibase at 01:44:22 (version 4.2.2 #36 built at 2020-12-09 20:07+0000)
[INFO] Executing on Database: jdbc:postgresql://localhost:5432/test_liquibase
[INFO] Successfully acquired change log lock
[INFO] Reading from databasechangelog
[INFO] Successfully released change log lock
[INFO] ------------------------------------------------------------------------
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.940 s
[INFO] Finished at: 2021-04-04T01:44:23+08:00
[INFO] ------------------------------------------------------------------------
```
