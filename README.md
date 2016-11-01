# PostgreSQL

### Platform

  + Ubuntu 16.04.1 64bit
  
### Reference

  + [*Official Site*](https://www.postgresql.org/docs/9.5/)
  
### Installation

  + `apt-get install postgresql`
  
  + Version: 9.5.5

### Concept
  
  1. USER & ROLE    
    
    *CREATE USER is equivalent to CREATE ROLE except that CREATE USER assumes LOGIN by default, while CREATE ROLE does not.*
    
  2. PASSWORD
  
    + system password
      
      In Ubuntu enviroment, all PostgreSQL softwares & tools only know user `postgres` which is the only administrator, and user `root` is not exist.
      
      User `postgres` can create other user which includes `root` just like:
      
      `sudo -u postgres createuser root` or `sudo -u postgres createuser root --superuser`
      
      It only creates a user for postsql itself, not for linux system, so you have to add a new system user if this user does not exist in linux system, you can create it by yourself just like:
      
      `useradd USERNAME`
      
    + database password
    
      It follows database, not user or role, so when you've created a new database, you have to assign password to user just like:
    
      ```
        sudo -u postgres createuser --superuser jack
        adduser jack
        sudo -u jack createdb jack
        psql jack
          psql (9.5.5)
          Type "help" for help.

          jack=# ALTER USER jack PASSWORD 'jack';        
      ```

### Note

  1. Users

    add user: `sudo -u postgres createuser root`
    
    delete user: `sudo -u postgres dropuser root`
    
  2. Database
    
    create database: `sudo -u postgres createdb -O root test`
    
    delete database: `sudo -u postgres dropdb test`
