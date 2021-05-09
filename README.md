# Shopify-challenge
shopify challenge
Question 1

The problem with the number calculated is that there are outliers/errors in the data set which are making the AOA way higher than it should be. After importing the data and creating arrays for the order amount(orderamount) and total items per order(totalitems). After this the average sneaker amount(average_sneaker_amount) which was calculated by dividing each element in the orderamount array by the elements in the totalitems array. Next the outliers needed to be identified and deleted since they were skewing the data. This was done by plotting the average sneaker amount

Next I created a function called Outliers, which removed the corresponding orderamount and totalitem values, if the average_sneaker_value for that pair exceeded $500, since a sneaker should definitely not cost more than that. 
The metrics that I calculated now were the average sneaker price(mean(ASA)), the average order amount(mean(OA))  and the average total number of items(mean(TI)).


The values for these metrics were:
average sneaker price: $152.48
average order amount: $2717
average total number of items: 8
Since the average total number of items is 8, it makes sense that the average order amount is $2717.


Question 2

SELECT * FROM [Shippers]
WHERE ShipperName="Speedy Express"
Answer: ShipperID=3

SELECT COUNT(OrderID)
FROM Orders
WHERE ShipperID=3;

Answer: 1

Select e.LastName, e.EmployeeID,COUNT(s.EmployeeID) AS MOST_FREQUENT
From (Employees e
Join Orders o ON e.EmployeeID=o.EmployeeID) as s;

Answer: Buchanan, EmployeeID 5, 196 Orders

select p.ProductName, MaxProd.ProductID, MAX(MaxProd.NumSales)
from((
( select OrderDetails.OrderID, OrderDetails.ProductID, count(*) as NumSales from OrderDetails group by ProductID
) MaxProd 
join Orders o ON MaxProd.OrderID=o.OrderID) withorder
join Customers c ON o.CustomerID=c.CustomerID) maxprodid
join Products p ON p.ProductID=MaxProd.ProductID
where c.Country= "Germany"
Answer: Rössle Sauerkraut
