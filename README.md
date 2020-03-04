Springboot JWT
--------------

Taken from: https://bezkoder.com/spring-boot-jwt-authentication/


Postgres Setup
--------------

a. Install the Postgres CLI 

brew install postgres

b. From command line, create db, user

createdb test-db
createuser security

c. Login into postgres default schema
psql postgres
ALTER ROLE security SUPERUSER;
CREATE SCHEMA security;
ALTER USER security WITH PASSWORD 'security';

d. Modify application.properties to mirror the above values

e. Startup the application and flyway will create the tables

f. Validate the tables
psql security;
select * from security.roles;
select * from security.users;
