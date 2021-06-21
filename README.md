# **Engineering Journal**

## **How to Splunk**

**Splunk**
: a tool that provides a user-friendly interface used for the quick organization of machine-generated data.

- What can you do with it?
  - **Search**: providing fields and/or terms and a time frame, Splunk will provide all logs matching your criteria.
    - Searches can also include ranges, utilizing the operators "<", "<=", "=", "!=", ">=", ">", as well as boolean operators such as "OR" and "AND" (leaving a space between terms implies the inclusion of an "AND" operator between them).
    - Wildcard characters can also be searched using the " * " symbol 
      - e.g. ```status=50*```
    - When searching for phrases, quotes must be applied around the entire phrase, or else Splunk will think you are searching for multiple inclusive terms 
      - e.g. ```product_name="Dream Crusher"``` as opposed to ```product_name=Dream Crusher```.
    - Within the results list, hovering over terms or fields in each result gives you the option of including, excluding, or starting a new search based on the hovered term.
    - Transforming Commands can also be input within each search, such as displaying a sorted list of successfully purchased products descending by counts of each product purchased 
      - e.g. ```sourcetype=access_combined action=purchase status=200 | stats count by product_name | sort -count``` The "|" operator indicates a new command to be invoked upon the results of the previous command.
      - The Primary Commands are ```chart, timechart, top, rare, stats```
    - **Lookups**: Not exactly sure what the definition is, but seems to be a more specific way to search; implemented as a command following the ```|``` (pipe) operator within the search bar, and generally follows the structure ```lookup <lookup-table-name> <lookup-field1> OUTPUT <lookup-field2>```
    - **Lookup Tables** can convert hard to read search results into more user-readable translations based on an imported converter file, usually .csv.
  - **Generate Reports**: reports can give statistical and visual feedback about your logs in a one-time or scheduled fashion.
    - After receiving the resulting data from your search, clicking ```Save As``` -> ```Report``` will bring up the modal to title your report/add a description, add time range capabilities, change permissions, and other aspects. These other options can be changed after viewing the report as well.
    - All reports you have permission to view will be in the reports section.
    - A quick report can be generated from just a search by selecting an action/field and selecting one of the quick report options in the modal that pops up upon selection.
  - **Trigger Alerts**: Alerts can be triggered based upon user-defined criteria on a scheduled or real-time basis.
    - Users can also define what they want Splunk to do when the Alert is triggered and what severity the alert should have, and what to send along with the alert if an action is defined. 
    - All alerts and their criteria can be changed under ```Activity``` -> ```Triggered Alerts``` or under the ```Alerts``` Splunk menu bar tab.

## **How to Docker**

## **How to Heroku**

## **How to GitHub Pages (Main Page/Portfolio)**

## **How to Cypress**

## **How to MongoDB/Mongoose**

## **How to SQL**
### **SQL**
: stands for Structured Query Language, which is a performant database querying language used to create, read, update, and delete (CRUD) entries in a database. Common database options that use SQL are MySQL, SQLite, and PostGreSQL.

### What can you do with it?
  - **CREATE**: used to create tables (which store records or actual data entries) within a database, setting columns, primary key, foreign keys, and more.
    - **ALTER**: tables can be altered after creation using this command, including the new column name and data type, and optionally default value.
  ```SQL
  CREATE TABLE table1 (
    id INTEGER PRIMARY KEY,
    name TEXT,
    age INTEGER
  );

  ALTER TABLE table1 ADD zip INTEGER;
  ```

  - **SELECT**: one of the most used commands in SQL is the SELECT command/keyword which allows users to search and read data within a database table based on supplementary information within the command, as well as reading the entire table/tables.
  ```SQL
  SELECT id, name FROM table1 WHERE age >= 25;
  ```
  - **INSERT INTO**: used for adding an entry (row of data) into a table, and will include data based on columns included in the command.
  ```SQL
  INSERT INTO table1 (id, name, age, zip) VALUES (1, 'Kimo', 105, 90210);
  ```
  - **UPDATE**: used for changing an existing entry's values without deleting the entry or creating a whole new one.
  ```SQL
  UPDATE table1 SET age = 26, zip = 92122, WHERE id = 1;
  ```
  - **DELETE**: useed for deleting an entry/entries within a table. Must be used with caution, as it will delete everything within the given specifications (i.e. ensure specificity).
  ```SQL
  DELETE FROM table1 WHERE id = 1;
  ```

### Useful Concepts
  - **TRANSACTIONS**: used for significantly improving the reliability and time performance of implementing large quantities of queries/commands as a single group, like inserting 10,000 entries into a table. Reliable, in the way that if ONE entry attempt fails, the entire group fails.
    - **ROLLBACK**: a safety catch in case a large number of queries succeeded but unintentionally. Will revert table to its previous state before transaction began.
  ```SQL
  BEGIN TRANSACTION;
    INSERT INTO table1 (id, name, age, zip) VALUES(...);
    .
    .
    .
    INSERT INTO...;
    ROLLBACK;
  END TRANSACTION;
  ```

  - **TRIGGERS**: used to invoke reactionary commands/queries upon desired trigger actions. Triggers give you access to the ```NEW``` keyword which refers to the newly created row of data within the target table, in the example below, the new row in the "widgetSale" table.
  ```SQL
  CREATE TRIGGER newWidgetSale AFTER INSERT ON widgetSale
    BEGIN
      UPDATE widgetCustomer set last_order_id = NEW.id WHERE widgetCustomer.id = NEW.customer_id;
    END
  ;
  ```
  - Triggers can also be used to prevent changes if desired circumstances have already been met/not met yet. The ```RAISE``` keyword will throw and error in the console with a message provided in the trigger definition. 
  ```SQL
  CREATE TRIGGER reconciledTrigger BEFORE UPDATE ON widgetSale;
    BEGIN
      SELECT RAISE(ROLLBACK, 'cannot update table "widgetSale"') FROM widgetSale
        WHERE id = NEW.id AND reconciled = 1;
    END
  ;
  ```
  - Another use for Triggers is creating a timestamp for each query made on an entry. 
  ```SQL
  Just Google it.
  ```
  - **SUBSELECTS**: using the results of a ```SELECT``` within another ```SELECT```. For example, select the first three letters of a set of entries and use those to select the full country name within another table.
  ```SQL
  SELECT co.Name, ss.CCode FROM (
    SELECT SUBSTR(a, 1, 2) AS State, SUBSTR(a, 3) AS SCode, SUBSTR(b, 1, 2) AS Country, SUBSTR(b,  3) as CCode FROM t
    ) AS ss
    JOIN Country AS co ON co.Code2 = ss.Country
  ;
  ```
  - **VIEWS**: essentially stored SELECTS which produce tables to easily view data. Can be stored and used later as a subselect.
  ```SQL
  CREATE VIEW company_view AS
    SELECT id, name, age
    FROM  company
  ;
  ```

## **How to Redux/React-Redux**

## **How to React**

## **How to Git**

## **How to JavaScript**
