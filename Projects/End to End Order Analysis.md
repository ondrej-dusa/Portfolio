```sql
CREATE TABLE Products (
    product_id INTEGER PRIMARY KEY,
    product_name TEXT,
    category TEXT);

INSERT INTO products (product_id, product_name, category) VALUES
('...','...','...');

ALTER TABLE Orders_Python ADD COLUMN Product_Category TEXT;

UPDATE Orders_Python
SET Product_Category = ( 
	SELECT Products.category
	FROM Products
	WHERE Products.product_name = Orders_Python.'Item Name');
```
