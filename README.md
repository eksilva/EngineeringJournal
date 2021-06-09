# **Engineering Journal**

## **How to Splunk**

**Splunk**
: a tool that provides a user-friendly interface used for the quick organization of machine-generated data.

- What can you do with it?
  - **Search**: providing fields and/or terms and a time frame, Splunk will provide all logs matching your criteria.
    - Searches can also include ranges, utilizing the operators "<", "<=", "=", "!=", ">=", ">", as well as boolean operators such as "OR" and "AND" (leaving a space between terms implies the inclusion of an "AND" operator between them).
    - Wildcard characters can also be searched using the " * " symbol (e.g. "status=50*")
    - When searching for phrases, quotes must be applied around the entire phrase, or else Splunk will think you are searching for multiple inclusive terms (e.g. "product_name='Dream Crusher'" as opposed to "product_name=Dream Crusher").
    - Within the results list, hovering over terms or fields in each result gives you the option of including, excluding, or starting a new search based on the hovered term.
    - Commands can also be input within each search, such as displaying a sorted list of successfully purchased products descending by counts of each product purchased (e.g. "sourcetype=access_combined action=purchase status=200 | stats count by product_name | sort -count"). The "|" operator indicates a new command to be invoked upon the results of the previous command.
  - **Create Reports**: reports can give statistical and visual feedback about your logs in a one-time or scheduled fashion.
    - w

## **How to Cypress**

## **How to MongoDB/Mongoose**

## **How to MySQL/PostGreSQL**

## **How to Redux/React-Redux**

## **How to React**

## **How to JavaScript**
