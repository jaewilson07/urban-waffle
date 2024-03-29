


 New features and enhancements
--------------------------------

Features and enhancements in this release include the following:

##
 Personalized Data Permissions (PDP)

Personalized Data Permissions (PDP) allow you to create a customized experience for each Domo user through the definition of Entitlement Policies. Using Entitlement Policies, you can filter data in a DataSet for specified users and/or groups. PDP policies are applied almost anywhere in Domo that data from this DataSet is used, including the following:

 Cards. If a card is powered by a DataSet with PDP policies applied, affected users and groups see only data in the card that applies to them.
* Alerts. An alert's PDP policies filter the alert data and control which users can subscribe.
* DataFusions. When you add input DataSets with PDP policies applied to a DataFusion, only the data allowed by the policy is incorporated into the DataFusion.

You cannot add input DataSets to a DataFlow if you are restricted by PDP policies; however, you can add policies to the output DataSets generated by the DataFlow. When executing a DataFlow with PDP policies applied, you
 *must*
 have an "Admin" security role or be the DataFlow owner; otherwise the DataFlow will break.


 If no Entitlement Policies have been created for a DataSet, anyone the DataSet has been shared with will have full access to the data. If a policy is created, only those users in the policy can see data.

*PDP Tab in Data Center**

*PDP Policy Selection in Alert Dialog**


 For more information, see

Personalized Data Permissions (PDP)

.

##
 Design Studio updates

The following enhancements have been made to the Design Studio:

 Notifications for users with older versions. Creative Cloud syncs version updates to users, so if users have turned off the Creative Cloud desktop sync application or if they need IT permission to upgrade, their version of Design Studio may be out of date. To accommodate this problem, a notification system has been built to identify users with older versions and instruct them on how to upgrade.
* New font selection interface. The former interface required users to type the font name into a text field. This has now been changed to a drop-down menu that populates with supported web fonts.

 Cool new widgets, including...

+ A Canadian FSA Map widget that shows data by province and FSA areas.
	+ Image and text link widgets that allow you to link to URLs on Domo's whitelist.
	+ Table Widget V2. The new table widget allows you to add sorts; define width by pixels or points; have alternating row colors; and set background transparency, cell borders, and border size.


###
 New Beast Mode functions

The following functions are now available for use in building Beast Mode calculations:


**String Functions**


 Function
  |
 Description
  |
 Example
  |
| --- | --- | --- |
|
`INSTR`
 |
 Returns the position of the first instance of a specified string in a given column, starting from the first letter in the name.


 In the example at right, the calculation would return the position of the first instance of the letter "e" in each string in the column.
  |
`INSTR(`Group`,'e')`
 |
|
`LEFT`
 |
 Returns the specified number of characters in each string in the the given column, starting from the left.
  |
`LEFT(`Group`,3)`
 |
|
`LENGTH`
 |
 Returns the number of characters in each string in the given column.
  |
`LENGTH(`Group`)`
 |
|
`REPLACE`
 |
 Replaces all of the specified strings in a given column with another specified string.
  |
`REPLACE(`Department`,'Human Resnources','Human Resources')`
 |
|
`RIGHT`
 |
 Returns the specified number of characters in the given column, starting from the right.
  |
`RIGHT(`Group`,3)`
 |


**Date/Time Functions**


|  |  |  |
| --- | --- | --- |
|
`UNIX_TIMESTAMP`
 |
 Returns UNIX time stamps for all values in a date/time column.
  |
`UNIX_TIMESTAMP(`DateCol`)`
 |
|
`WEEKOFYEAR`
 |
 Returns the week number for all dates in a date/time column.
  |
`WEEKOFYEAR(`DateCol`)`
 |

For more information about Beast Mode calculations, see

Beast Mode Functions Reference Guide

.

##
 Previews of previous/next cards

In the Details view for a card, when you mouse over the previous or next button, a thumbnail image of the previous or next card in the page appears.

For more information about the Details view, see

Card Details View Layout

.

##
 Card Builder resizable column containers

In the Card Builder, you can now expand the pane on the left that displays the category and value columns. This will allow you to read longer column names that would have been cut off previously.


###
 Filtering on unused data columns

An issue was corrected in which you were not able to filter on data columns not being used in your visualization.

##
 End of Support for IE9

Beginning with our July release, Domo will no longer be supporting Internet Explorer 9.

##
 End of Support for Workbench 2

Beginning in September, Domo will be ending support for Workbench 2.


 Getting Help
--------------

You can view the latest release notes information in the Help Center, which you can access from Domo by clicking

*> Help Center**
 .


 If you have questions about Domo,

 search for a topic in the Help Center
* train in Domo University at

http://www.domo.com/university
* get answers in the Domo Community at

dojo.domo.com
* contact Technical Support by using @DomoSupport in Buzz, by email at

support@domo.com

or by phone at 801-805-9505 (Monday through Friday, 7 am to 6 pm MST)
* reach out to your Domo Customer Success Manager or Technical Consultant

If you have feedback, please send it from within Domo (

*> Feedback**
 ). Or send an email to

product.feedback@domo.com

.


 For more information about getting help, see

Getting Help

.

