# Notes on Relational Databases and MySQL

MySQL is a relational database that can handle large amounts of structured data very well. It can guarantee transactional integrity even as datasets become large and complex through [integrity constraints](http://en.wikipedia.org/wiki/Data_integrity#Types_of_integrity_constraints). However, for Big Data applications, the relational model can only scale upwards; and only to a point at which it then becomes too expensive and complex to perform the application. [Big Data](README.md), in terms of volume, is moving farther away from gigabytes and toward terabytes and petabytes of data. Relational databases may not be able to handle data sets with high velocity or variety, which is common with Big Data. Since MySQL is a relational database, it requires data to be structured with its schema explicitly specified.

Below are notes on how to use MySQL for small data. For Big Data, relational databases will need to be supplemented with other methods and file storage systems. See notes on [MapReduce](mapreduce_hadoop.md).

### Import data into MySQL

Via terminal:

#### Create table:
```
CREATE TABLE table_name (
	field_name varchar(),
	field_name TIMESTAMP,
	field_name DATE,
	field_name TIME,
	field_name INTEGER
);
```
#### Load data into table:

Example for CSV with comma separated values and quotes as text delimiter:

````
LOAD DATA LOCAL INFILE 'file_path'
INTO TABLE table_name
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\r\n'
IGNORE 1 LINES;
````