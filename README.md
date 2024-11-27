# Samples Repeater

A number of the samples require a repeater

## Version

1.0

## Database

Create a MSSQL database called "StadiumFilterData" by running the SQL script called filterdata.sql in this repo 

## Connector
Add a Database connector in the Stadium Designer

1. Click on the *Connectors* button in the toolbar and selecting *Database* in the dropdown
2. Enter the connection details in the popup window
   1. Server name
   2. Username
   3. Password
   4. Database
3. Check the "Trust Server Certificate" checkbox

## Query
Add a query to select the data for the DataGrid

1. Click the plus icon next to the connector to add a query
2. Name the query as you see fit
3. Right-click on the table called "MyData" in the main tab
4. Select "Generate Select" or copy and paste the SQL below into the *Query* tab
```
SELECT ID
      ,FirstName
      ,LastName
      ,NoOfChildren
      ,NoOfPets
      ,StartDate
      ,EndDate
      ,Healthy
      ,Happy
      ,Subscription
  FROM dbo.MyData;
```
5. Click the *Fetch Fields & Parameters* button 

## Type

1. Add a type called "MyData"
2. Add the following properties to the type
   1. ID (Any)
   2. FirstName (Any)
   3. LastName (Any)
   4. NoOfChildren (Any)
   5. NoOfPets (Any)
   6. StartDate (Any)
   7. EndDate (Any)
   8. Healthy (Any)
   9. Happy (Any)
   10. Subscription (Any)

## Repeater

1. Add a *Repeater* Control to a page
2. Set the *Repeater* *ListItem Type* property to the "MyData" type you created
3. In order to display the data in rows, uncheck the *Repeater* *Item Inline* property checkbox
4. Open the StartPage.load event handler
5. Drag the query in the StartPage.Load event handler of the page
6. Drag a SetValue function under the query in the StartPage.load event handler
7. Assign the data returned by the query to the *Repeater*