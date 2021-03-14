---
title: "PostgreSQL"
date: 2020-08-03T00:16:39-04:00
draft: false
menuTitle: "PostgreSQL"
weight: 2
---
#### Installation 
Steps to install postgreSql in Ubuntu 20.04
- `sudo apt update` - to refresh package index
- `sudo apt install postgresql-contrib` - to install postgresql alongwith additional tools and packages
- By default, a postgres user is created which can be used to manage postgres. `sudo -i -u postgres`
- `psql` to interact with postgres and `\q` to exit postgresql prompt
- `createuser --interactive --password postgres-user` to create new user
- `createdb demo-db -O postgres-user` to create a new db
- update the `pg_hba.conf` to allow local connections 
	```bash
    # "local" is for Unix domain socket connections only
	local   all             all                                     trust
	# IPv4 local connections:
	host    all             all             127.0.0.1/32            trust
	```
- `sudo service postgresql restart` to enable the changes done

##### Demo Project with Spring boot 
https://github.com/vyomrastogi/spring-postgres-learner.git


##### Reference 
http://zetcode.com/springboot/postgresql/ 
