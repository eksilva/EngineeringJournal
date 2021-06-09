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
    - Commands can also be input within each search, such as displaying a sorted list of successfully purchased products descending by counts of each product purchased 
      - e.g. ```sourcetype=access_combined action=purchase status=200 | stats count by product_name | sort -count``` The "|" operator indicates a new command to be invoked upon the results of the previous command.
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

## **How to MySQL/PostGreSQL**

## **How to Redux/React-Redux**

## **How to React**

## **How to Git**

## **How to JavaScript**
