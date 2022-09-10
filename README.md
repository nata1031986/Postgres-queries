Find products that were sold less than 2000$








Find customers that bought more than 5000$ of products
SELECT companyname, SUM (quantity*order_details.unitprice)AS AmountBought
FROM customers
NATURAL JOIN orders
NATURAL JOIN order_details
GROUP BY companyname
HAVING SUM (quantity*order_details.unitprice)>5000
ORDER BY AmountBought DESC
