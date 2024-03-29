

Intro
-------

MySQL is a widely used open-source relational database management system. You can use Domo's MySQL SSH Multi-Statement Connector to pull data from your MySQL database and compile custom reports. You indicate the data you want by inputting an SQL query. For more information about the MySQL API, visit their website. (

http://dev.mysql.com/doc/refman/5.0/en/c-api.html

)


 The MySQL SSH MultiStatement connector is a "Database" connector, meaning it retrieves data from a database using a query. In the Data Center, you can access the connector page for this and other Database connectors by clicking
 **Database**
 in the toolbar at the top of the window.


 You connect to your MySQL database in the Data Center. This topic discusses the fields and menus that are specific to the MySQL SSH MultiStatement connector user interface. General information for adding DataSets, setting update schedules, and editing DataSet information is discussed in

Adding a DataSet Using a Data Connector

.

  |  |
| --- | --- |
|
**Primary Use Cases**
 |
 Pulling data mart and data warehouse SQL queries
  |
|
**Primary Metrics**
 |
 N/A
  |
|
**Primary Company Roles**
 | * CIO
* CTO
 |
|
**Average Implementation Time**
 |
 5-40+ hours
  |
|
**Ease of Use (on a 1-to-10 scale with 1 being easiest)**
 |
 7
  |

Best Practices
----------------


* Limit the results set size as much as possible.
* Keep the number of columns to a minimum.

Prerequisites
---------------

To connect to a MySQL database via an SSH server and create a DataSet, you must have the following:

 The hostname of the UNIX server you are SSH-tunneling through
* The SSH username and password for your UNIX account
* The host name for the database
* The SSH private key (either DES or RSA) in PEM format
* The database name
* The username and password you use to log into your MySQL database

*Note: Domo does not support the SSH keys generated using ssh-keygen. The SSH keys need to be the DES or RSA keys (in PEM format) generated by OpenSSL.**

##
 Creating MySQL Accounts

You can create MySQL accounts two ways:

 By using account management statements intended for creating accounts and establishing their privileges, such as

CREATE USER

and

GRANT

. These statements cause the server to make appropriate modifications to the underlying grant tables.
* By manipulating the MySQL grant tables directly with statements such as

INSERT

,

UPDATE

, or

DELETE.

The preferred method is to use account management statements because they are more concise and less error-prone than manipulating the grant tables directly.


 Another option for creating accounts is to use the GUI tool MySQL Workbench. Also, several third-party programs offer capabilities for MySQL account administration, such as phpMyAdmin.

##
 Whitelisting

Before you can connect to a MySQL database, you must also whitelist a number of IP addresses on your database server on the port you want to connect to. For the full list of IP addresses, see

Whitelisting IP Addresses for Connectors

.


 Connecting to Your MySQL Database
-----------------------------------

This section enumerates the options in the
 **Credentials**
 and
 **Details**
 panes in the MySQL SSH Multistatement Connector page. The components of the other panes in this page,
 **Scheduling**
 and
 **Name & Describe Your DataSet**
 , are universal across most connector types and are discussed in greater length in

Adding a DataSet Using a Data Connector

.

##
 Credentials Pane

This pane contains fields for entering credentials to connect to your database. The following table describes what is needed for each field:


 Field
  |
 Description
  |
| --- | --- |
|
 SSH Server Hostname
  |
 Enter the hostname of the UNIX server to SSH-tunnel through.
  |
|
 SSH Username
  |
 Enter the SSH username for your UNIX account.
  |
|
 SSH Password
  |
 Enter the SSH password for your UNIX account.
  |
|
 Database Hostname
  |
 Enter the hostname or IP address for the SQL database. For example:


 db.company.com


 |
|
 SSH Private Key
  |
 Enter the SSH private key (either DES or RSA).
  |
|
 Database Name
  |
 Enter the name of the SQL database or schema.
  |
|
 Database Username
  |
 Enter your MySQL username.
  |
|
 Database Password
  |
 Enter your MySQL password.
  |

Once you have entered valid credentials, you can use the same account any time you go to create a new MySQL SSH Multistatement DataSet. You can manage connector accounts in the
 **Accounts**
 tab in the

Data Center

. For more information about this tab, see

Managing User Accounts for Connectors

.

##
 Details Pane

In this pane you create an SQL query to pull data from your database as well as specify a few options.


 Menu
  |
 Description
  |
| --- | --- |
|
 Query Type
  |
 Select a query type.


|
 Query Type
  |
 Description
  |
| --- | --- |
|
 Query
  |
 Regular SQL query without parameter.
  |
|
 Query Parameter
  |
 SQL query with parameter.
  |

|
|
 Query Parameter
  |
 Enter the query parameter value. It is the initial value for query parameter. The last run date is optional. The default value for the last date is '02/01/1700' if not provided.

Example:


 !{lastvalue:\_id}!=1,!{lastrundate:start\_date}!=02/01/1944

|
|
 SQL Query
  |
 Structured Query Language (SQL) query to use in selecting the data you want. For example:

select \* from Employee

|
|
 TINYINT Values Treated as Bit (Boolean) Values?
  |
 Select
 **Yes**
 if you want TINYINT values to be treated as Boolean values.
  |
|
 Keep Connection Alive For Large Queries
  |
 Runs an additional thread to keep the connection alive. Useful for long runs.
  |
|
 Query Timeout
  |
 Enter connector timeout value in minute(s).
  |
|
 Remove Duplicate Records (Connector Update Mode is MERGE)
  |
 Check this box to remove duplicate records when connector is using Merge/Upsert functionality, bringing in only the most recently modified data. Duplicates are removed using a SQLite query that keeps the most recently modified row.

Checking this box will slow your connector run, so use this feature only when necessary.
  |


###
 Other Panes

For information about the remaining sections of the connector interface, including how to configure scheduling, retry, and update options, see

Adding a DataSet Using a Data Connector

.


 Troubleshooting
-----------------


* Verify the credentials using MySQL Workbench.
* Confirm the server supports encrypted connections.
* Confirm the Domo IPs are whitelisted.


