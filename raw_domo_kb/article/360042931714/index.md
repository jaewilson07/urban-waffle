

Intro
-------

IBM DB2 contains database server products developed by IBM. These products support the relational model with some support for object-relational features and non-relational structures like JSON and XML. You can use Domo's IBM DB2 SSH Connector to create a secure, encrypted connection with your DB2 database to bring your data into Domo and start making better decisions.


 You connect to your IBM DB2 database in the Data Center. This topic discusses the fields and menus that are specific to the IBM DB2 SSH connector user interface. General information for adding DataSets, setting update schedules, and editing DataSet information is discussed in

Adding a DataSet Using a Data Connector

.


 Prerequisites
---------------

To connect to an IBM DB2 database and create a DataSet, you must have the following:

 The username and password you use to log into your DB2 database
* The host name for the database
* The port number for the database
* The database name
* Your SSH host name
* Your SSH username and password
* Your SSH port number
* Your SSH private key

Before you can connect to an IBM DB2 database, you must also whitelist a number of IP addresses on your database server on the port you want to connect to. For the full list of IP addresses, see

Whitelisting IP Addresses for Connectors

.


**Note: Domo does not support the SSH keys generated using ssh-keygen. The SSH keys need to be the DES or RSA keys (in PEM format) generated by OpenSSL.**


 Connecting to Your IBM DB2 Database
-------------------------------------


 This section enumerates the options in the
 **Credentials**
 and
 **Details**
 panes in the IBM DB2 SSH Connector page. The components of the other panes in this page,
 **Scheduling**
 and
 **Name & Describe Your DataSet**
 , are universal across most connector types and are discussed in greater length in

Adding a DataSet Using a Data Connector

.


###

Credentials Pane


 This pane contains fields for entering credentials to connect to your IBM DB2 database. The following table describes what is needed for each field:


|

Field

|

Description

|
| --- | --- |
|
 SSH User
  |
 Enter your SSH username.
  |
|
 SSH Password
  |
 Enter your SSH password.
  |
|
 SSH Port
  |
 Enter your SSH port number.
  |
|
 SSH Private Key
  |
 Enter your SSH private key.
  |
|
 Database User
  |
 Enter your DB2 database username.
  |
|
 Database Password
  |
 Enter your DB2 database password.
  |
|
 Database Port
  |
 Enter the port number for the DB2 database.
  |
|
 Database Name
  |
 Enter the name of the DB2 database.
  |
|
 Database Host
  |
 Enter the host name for the DB2 database. For example:


 db.company.com


 |
|
 SSH Host
  |
 Enter your SSH host name.
  |


 Once you have entered valid credentials, you can use the same account any time you go to create a new IBM DB2 DataSet. You can manage connector accounts in the
 **Accounts**
 tab in the Data Center. For more information about this tab, see

Managing User Accounts for Connectors

.


###
 Details Pane

In this pane you create an SQL query to pull data from your database. The
 **Query**
 parameter is required. The other three parameters are here to help you construct this query if you choose.


 Menu
  |
 Description
  |
| --- | --- |
|
 Query
  |
 Enter the Structured Query Language (SQL) query to use in selecting the data you want. For example:

select \* from Employee

If you want help in constructing your query, copy and paste the automatically generated query from the
 **Query Helper**
 field.
  |
|
 Table Name (Optional)
  |
 Select the table containing the data you want to pull into Domo. The selected table will be added to the automatically generated query in the
 **Query Helper**
 field.
  |
|
 Column Names (Optional)
  |
 Select the table columns with data you want to pull into Domo. The selected columns will be added to the automatically generated query in the
 **Query Helper**
 field.
  |
|
 Query Helper (Optional)
  |
 Copy and paste this query into the
 **Query**
 field if you need help building a query. This query is automatically generated when you select a table and columns in the
 **Database Table**
 and
 **Table Columns**
 fields, respectively.
  |


###
 Other Panes

For information about the remaining sections of the connector interface, including how to configure scheduling, retry, and update options, see

Adding a DataSet Using a Data Connector

.


 FAQs
------


#####
 Are there any API limits I should be aware of?

Limits depend on your server configuration.

####
 How often can the data be updated?

DataSets can run as often as every 15 minutes. However, depending on the runtime of the query, DataSets may need to run less frequently.

