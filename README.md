# boot

sql server 

DATABASE :

  Data base creation :
  1. CREATE DATABASE "Name"
    
  2.  Rename Database :
    1. Alter DATABASE <<olddatabasename>> Modify NAME="newName"
    2.using system stored procedure
      sp_renameDB oldname,newname
      
  3. DROP DATABASE:
   1. drop database <name of the database>
    before doing that put it in single user mode. using alter database command
    Alter Database <<database Name>> SET SINGLE_USER with Rollback immediate
    
    
  TABLES: 
  
 1.  CREATE TABLE <TABLE NAME>
 (
  Name DATAType Constraints 
 )
 constriants are catogorized into NOT NULL,PRIMARY KEY,UNIQUE,FORIEGN KEY REFERENCES
 2. Alter Table <Table Name> ADD|DROP|MODIFY CONSTRAINT|Column <<NAME>> <VALUES>  DEFAULT <VALUE>
 
 3. DELETING A REFERENCING ROw
    Deleting a row which is being referenced in a different table throws an error, to over come this we have few options
    
    1. SET TO DEFAULT
    2. SET TO NULL
    3. CASCADE
    4. NOACTION( By default this will be checeked )
    
    CREATE TABLE child_table
(
  column1 datatype [ NULL | NOT NULL ],
  column2 datatype [ NULL | NOT NULL ],
  ...

  CONSTRAINT fk_name
    FOREIGN KEY (child_col1, child_col2, ... child_col_n)
    REFERENCES parent_table (parent_col1, parent_col2, ... parent_col_n)
    ON DELETE CASCADE
    [ ON UPDATE { NO ACTION | CASCADE | SET NULL | SET DEFAULT } ] 
);


    
 
