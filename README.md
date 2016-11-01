# PostgreSQL

### Platform

  + Ubuntu 16.04.1 64bit
  
### Installation

  + `apt-get install postgresql`
  
  + Version: 9.5.5
  
### Note

  1. Users

    PostgreSQL has a different user control system from Ubuntu.
    
    In PostgreSQL, the defautl administrator is `postgres` not `root`, so if you want to create a new database under user `root`, you have to create this user first, just like:

    `sudo -u postgres createuser root`
    
    `sudo -u postgres dropuser root` is to delete `root` in PostgreSQL enviroment.
    
  2. Database
  
    user `root` is not powerful under PostgreSQL enviroment, so if you want to create a new database `test` which belongs to user `root`, you have to depend on user `postgres` just like:
    
    `sudo -u postgres createdb -O root test`
    
    `sudo -u postgres dropdb test` is to delete database `test`.
