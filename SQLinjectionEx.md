# SQL Injection
## NOSQL Injection 1
### You need to exploit a NoSQL injection vulnerability to retrieve Mario's GamerID
![button](/images/nosqli1.png)

all this is is just pressing the button that was meant for Mario. Pretty simple

## SQL Injection 1
### To complete this challenge, you must exploit SQL injectionflaw in the following form to find the result key.
![entry field](/images/sqli1.png)

We want to print all the details of every customer. The query before entering anything should read `SELECT * FROM customer WHERE customerid=''`. Our input will go in between the quotes. At first, we can enter any string to match, followed by quotes to escape the field. TO print all of the customers, we OR that text field with a statement that is always true, such as `'1'='1'`. In the form enter `anything' OR '1'='1.` This will make the query `SELECT * FROM customer WHERE customerid='anything' OR '1'='1'` This will show every attribute of every customer in the table.

## SQL Injection 2
### To complete this challenge, you must exploit the SQL injection flaw in the following form to find the result key.
![email field](/images/sqli2.png)

In this problem we are basically doing the same thing as SQL injection 1; we are looking up every customer using an attribute, but in this case we're using the email field. The query would look similar to SQL injection 1, `SELECT * FROM customers WHERE email=''`. However if we try using  the same tactic as earlier, the form will return with an invalid format flag, because the php script is checking to see if its in email format.This includes being in someone@example.com format with  no spaces. To do this, we enter `'OR'0'!='@gmail.com`, which is an always true statement in email format.The resulting query would be `SELECT * FROM customers WHERE email=''OR'0'!='@gmail.com'` and will print all of the customers' information

## SQL Injection 3
### To complete this challenge, you must exploit a SQL injection issue in the following sub application to acquire the credit card number from one of the customers that has a customer name of Mary Martin. Mary's credit card number is the result key to this challenge.
![name field](/images/sqli3.png)

In this example, we're dealing with the name field again. We are given the name Mary Martin, however when we enter in her name, the only her name gets returned. Alternatively, we want her credit card. The query right now looks like `SELECT customername WHERE customername=''` So we need to add a `UNION` to attach another query into the same query. in the  field, we would enter `Mary Martin' UNION SELECT creditcard WHERE customername='Mary Martin` the resulting query would look like `SELECT customername WHERE customername='Mary Martin' UNION SELECT creditcard WHERE customername='Mary Martin'` which returns Mary's name and credit card. Notice we didn't use the always true statement bc we knew something about the target

## SQL Injection 4
### To acquire the result key for this challenge you must successfully sign in as an administrator.
![login field](/images/sqli4.png)

to be continued..
