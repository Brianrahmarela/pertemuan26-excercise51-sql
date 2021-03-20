1. Tampilkan semua Customer yang tinggal di Negara German atau Mexico
   SELECT \* FROM Customers WHERE country = "Germany" OR country = "Mexico";

2. Tampilkan semua Product yang Harganya kurang dari 15
   SELECT \* FROM [Products] WHERE price BETWEEN 0 AND 15;

3. Tampilkan semua Product yang range Harganya dari 10 - 30
   SELECT \* FROM [Products] WHERE price BETWEEN 10 AND 30;

4. Tampilkan semua Customer yang tinggal di Europa
   SELECT \* FROM Customers WHERE Country NOT IN ('Mexico', 'Argentina', 'Brazil', 'Venezuela', 'USA');

5. Hitung jumlah total Order Customer dengan Nama Rattlesnake Canyon Grocery
   SELECT SUM(quantity) AS total_quantity FROM Orders
   INNER JOIN OrderDetails
   ON orders.orderid = OrderDetails.orderid WHERE CustomerID = "65";

6. Tamplikan Orderan dari Federal Shipping dengan OrderDate kurang dari bulan 12
   SELECT orderId FROM [Orders] where ShipperID = '3' AND orderdate BETWEEN '1996-01-01' AND '1996-11-31';

7. Tampilkan Semua Nama Barang yang dibeli oleh Save-a-lot Markets
   SELECT productname FROM customers AS A INNER JOIN Orders AS B ON A.CustomerID = B.CustomerID
   INNER JOIN OrderDetails AS C ON C.orderId = B.orderId
   INNER JOIN products AS D ON D.ProductID = C.ProductID WHERE A.CustomerID = '71';

8. Hitung total keseluruhan barang yang dibeli oleh B's Beverages
   SELECT SUM(quantity) AS total_quantity FROM customers
   INNER JOIN orders ON customers.CustomerID = orders.CustomerID
   INNER JOIN OrderDetails ON orders.OrderID = OrderDetails.OrderID
   WHERE CustomerName = "B's Beverages";

9. Hitung total pengiriman yang dilakukan oleh United Package pada bulan 8
   SELECT Count(ShipperID) FROM [Orders] where ShipperID = '2'
   AND OrderDate Like '%-08-%';

10. Tampilkan Product dengan Category Beverages
    SELECT ProductName FROM [Products] INNER JOIN categories
    ON Products.CategoryID = categories.CategoryID
    WHERE CategoryName = 'Beverages';
