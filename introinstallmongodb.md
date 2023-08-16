<div align="center">
  <h1>MongoDB Introduction and Installation</h1>
  <sub>Author:
<a href="https://www.linkedin.com/in/bhuvanaganesan-l-2209047a" target="_blank">Bhuvan Ganesan</a><br>
</sub>
</div>

<hr>

# Introduction

MongoDB is an open-source, cross-platform, and distributed document-based database designed for ease of application development and scaling. It is a NoSQL database developed by MongoDB Inc.

MongoDB name is derived from the word "Humongous" which means huge, enormous. MongoDB database is built to store a huge amount of data and also perform fast.

MongoDB is not a Relational Database Management System (RDBMS). It's called a "NoSQL" database. It is opposite to SQL based databases where it does not normalize data under schemas and tables where every table has a fixed structure. Instead, it stores data in the collections as JSON based documents and does not enforce schemas. It does not have tables, rows, and columns as other SQL (RDBMS) databases.

The following table lists the relation between MongoDB and RDBMS terminologies.

<table>
  <tr>
    <td>MongoDB (NoSQL Database)</td>
    <td>RDBMS (SQL Server, Oracle, etc.)</td>
  </tr>
  <tr>
    <td>Database</td>
    <td>Database</td>
  </tr>
  <tr>
    <td>Collection</td>
    <td>Table</td>
  </tr>
  <tr>
    <td>Document</td>
    <td>Row (Record)</td>
  </tr>
  <tr>
    <td>Field</td>
    <td>Column</td>
  </tr>
</table>

In the RDBMS database, a table can have multiple rows and columns. Similarly in MongoDB, a collection can have multiple documents which are equivalent to the rows. Each document has multiple "fields" which are equivalent to the columns. Documents in a single collection can have different fields.

<img src='jsonsample.webp'>

