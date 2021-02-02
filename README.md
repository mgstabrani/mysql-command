# mysql-command
## Running MariaDB or MySQL
- Running the server
```
sudo systemctl start mariadb
```
- Running MariaDB
```
mysql -u {username} -p
```
## Database Administrator Query
- Creating new database
```
create database {database_name};
```
- Showing list of databases
```
show databases;
```
- Changing database
```
use {database_name};
```
- Showing list of tables in particular database
```
show tables;
```
- Showing the field description in a table
```
describe {table_name};
```
- Deleting a database
```
drop database {database_name};
```
- Dumping a database to external file
```
mysqldump -c -u {username} -p --databases {database_name} > {external_file_name}.sql
```
- Restoring a database from external file
```
mysql -u {username} -p {database_name} < {external_file_name}>.sql
```
- Dumping all databases to external file
```
mysqldump -u root -p --opt > {external_file_name}.sql
```
## User Administrator Query
- Creating new user
```
mysql -u root -p /* masuk sebagai root */
mysql> use mysql; /* gunakan tabel mysql */
mysql> INSERT INTO user (Host,User,Password) VALUES('%','username', PASSWORD('password')); /* buat user baru */
mysql> flush privileges; /* update privilege */
```
- Changing user password
```
mysqladmin -u username -h hostname.blah.org -p password 'new-password'
```
- Changing user password from MariaDB prompt
```
mysql -u root -p /* masuk sebagai root */
mysql> SET PASSWORD FOR 'user'@'hostname' = PASSWORD('passwordhere'); /* ganti password */
mysql> flush privileges; /* update privilege */

```
- Creating root password
```
mysqladmin -u root -p {newpassword}
```
- Changing root password
```
mysqladmin -u root -p {oldpassword} {newpassword}
```