# api_postgres_go
API in Golang using Docker container Postgres as database  
This api was create following a tutorial by Aprenda Golang

Command used for create Docker container Postgres

> $docker run -d --name api-todo -p 5432:5432 -e POSTGRES_PASSWORD=1234 postgres:13.5

Using psql inside Postgres container

> $docker exec -it api-todo psql -U postgres

Inside psql, the following commands were used

> $create database api_todo;  
> $create user_todo;  
> $alter user user_todo with encrypted password '1234';  
> $grant all privileges on database api_todo to user_todo;  

List tables - psql terminal
> $\l  

Creating table in psql
> $\c api_todo;  
> $create table todos (id serial primary key, title varchar, description text, done bool default false);  
> $\dt // just for check table creation;  
> $grant all privileges on all tables in schema public to user_todo;  
> $grant all privileges on all sequences in schema public to user_todo;


After all, just testing http://localhost:9000 in Insomnia