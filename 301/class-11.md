# MongoDB and Mongoose

## NoSQL vs SQL


- Fill in the chart below with five differences between SQL and NoSQL databases:

<table>
    <tr>
        <th>SQL</th>
        <th>NoSQL</th>
    </tr>
    <tr>
        <td>Relational Databases</td>
        <td>Non-relational/Distributed Database</td>
    </tr>
    <tr>
        <td>Table based, based on # of rows of data</td>
        <td>Document Based, based on key-value pairs, documents, graph databases or wide-column stores</td>
    </tr>
    <tr>
        <td>SQL db's have predefined schema, scaled by increasing horse power of hardware (Scales Vertically adding CPU, RAM, SSD, etc on single server)</td>
        <td>NoSQL db's are horizontally scalable, scaled by increasing the db's servers in the pool of resources to reduce the load (Scales Horizontally, adding more servers) </td>
    </tr>
    <tr>
        <td>Db Examples: MySQL, Oracle, Sqlite, Postgres, MS-SQL. Uses SQL (Structured Query Language) to manipulate data.</td>
        <td>DB Examples: MongoDB, BigTable, Redis, RavenDBb, Cassandra, HBase, Neo4j, CouchDB. Uses UnQL (Unstructured Query Language), varying syntax depending on db used. </td>
    </tr>
    <tr>
        <td>Good for complex query intensive environments not best fit for hierarchical data storage.</td>
        <td>Not good for complex queries. Fits better for hierarchical data storage and large data sets. </td>
    </tr>
</table>


- What kind of data is a good fit for an SQL database?

SQL databases are great for storing and processing structured data.

- Give a real world example.

An example of structured data is a defined table that includes fields like date, name, address and credit card number.

- What kind of data is a good fit a NoSQL database?

The kind of data that fits good for a NoSQL db is unstructured data.

- Give a real world example.

Examples of unstructured data are social media posts, texts, mobile activity, internet sensor data.

- Which type of database is best for hierarchical data storage?

NoSQL databases are best for hierarchical data storage.

- Which type of database is best for scalability? 

NoSQL would be best for scalability since it is as easy as adding a few more servers. 


## SQL vs NoSQL


- What does SQL stand for?

Structured Query Language

- What is a relational database?

Relational databases are based on the relational model, an intuitive, straightforward way of representing data in tables.

- What type of structure does a relational database work with?

It works with data structured as a table with columns and rows.

- What is a ‘schema’?

A predefined table that includes fields (columns) and Records(rows) of data. All records in that table have to follow this schema. 

- What is a NoSQL database?

MongoDB is a NoSQL Database.

- How does it work?

In the database, instead of tables in SQL, we have 'collections.' In a collection we have documents that kind of look like JSON or JS objects with no schema.

- What is inside of a MongoDB database?

In the MongoDB data base, we have collections which are like the tables in a SQL database, and we have documents which are like the columns and rows. 

- Which is more flexible - SQL or MongoDB? and why.

It depends on the type of data that you're storing and the type of application you're building. But NoSQL is more flexible because it is schema-less, no or few relations for reading data, performance for READS and WRITES is great and NoSQL can scale horizontally and vertically. 

- What is the disadvantage of a NoSQL database?

Having none or few relations can cause updating data to be tedious, the schema-less data structure can be a disadvantage when creating data.

>References 
>
>[SQL vs NoSQL Database Differences Explained with few Example DB](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)
>
>[SQL vs NoSQL or MySQL vs MongoDB](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)