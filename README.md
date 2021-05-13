# SQL-SCRIPTS
syntax codes

CREATE DATABASE some_database;

CREATE DATABASE IF NOT EXISTS some_database;

USE some_database;

CREATE TABLE table_name (
  column_name1 data_type(size) constraint_name,
  column_name2 data_type(size) constraint_name,
  PRIMARY KEY (field_name),
  FOREIGN KEY (other_field) REFERENCES table_name(primary_key)
);

Types of contraints
NOT NULL
UNIQUE
DEFAULT
PRIMARY KEY and FOREIGN KEY

CREATE TABLE my_table (
  name varchar(100) NOT NULL
);

CREATE TABLE my_table (
  name varchar(100) NOT NULL,
  rank int UNIQUE NOT NULL
  
  CREATE TABLE my_table (
  name varchar(100) NOT NULL,
  rank int UNIQUE NOT NULL,
  status varchar(10) DEFAULT 'unranked'
);

CREATE TABLE my_table (
  person_id int AUTO_INCREMENT,
  name varchar(100) NOT NULL,
  rank int UNIQUE NOT NULL,
  status varchar(10) DEFAULT 'unranked'
);

CREATE TABLE my_table (
  person_id int AUTO_INCREMENT,
  name varchar(100) NOT NULL,
  rank int UNIQUE NOT NULL,
  status varchar(10) DEFAULT 'unranked',
  PRIMARY KEY(person_id)
);

A PRIMARY KEY can be made up of two fields, also known as a composite key;
CREATE TABLE example (
    field1 INT,
    field2 INT,
    PRIMARY KEY (field1, field2)
);

CREATE TABLE orders (
      fk_customer_id INT NOT NULL,
      fk_product_id INT NOT NULL, 
      quantity INT NOT NULL, 
      total DEC(10,2) NOT NULL,
      date_placed DATETIME NOT NULL,
      PRIMARY KEY (fk_customer_id, fk_product_id, date_placed),
      FOREIGN KEY (fk_customer_id) REFERENCES customers(id),
      FOREIGN KEY (fk_product_id) REFERENCES products(id)
);

FOREIGN KEYS;
CREATE TABLE my_table (
  person_id int NOT NULL AUTO_INCREMENT,
  name varchar(100) NOT NULL,
  rank int UNIQUE NOT NULL,
  status varchar(10) DEFAULT 'unranked',
  PRIMARY KEY (person_id)
);
CREATE TABLE my_second_table (
  account_id int NOT NULL AUTO_INCREMENT,
  fk_person_id int NOT NULL,
  account_type varchar(100) NOT NULL,
  PRIMARY KEY (account_id),
  FOREIGN KEY (fk_person_id) REFERENCES my_table(person_id)
);

To add a field to a table:

ALTER TABLE table_name
ADD column_name data_type;
And to delete a field from a table:

ALTER TABLE table_name
DROP COLUMN column_name;

If not all the listed tables exist, MySQL will still drop all tables that do exist.

DROP TABLE IF EXISTS table_that_should_not_be_dropped;

CANCEL EXAMPLE
mysql> SELECT * FROM my_table WHERE name = 'Smith AND age < 30;
    '>'\C
