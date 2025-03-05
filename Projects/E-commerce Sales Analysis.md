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

```python
orders = pd.read_csv('Orders_New.csv')
orders.drop(orders.columns[[3, 4, 5, 6, 7, 9, 11, 12, 13, 14, 15, 16, 17, 18, 19, 35, 37]], axis=1, inplace=True)

orders['Order Date'] = pd.to_datetime(orders['Order Date'])
orders['Order Date'] = orders['Order Date'].dt.strftime('%d/%m/%Y')

orders['City (Billing)'] = orders['City (Billing)'].str.replace(r'\s\d+', '', regex=True)
orders['City (Billing)'] = orders['City (Billing)'].str.title()

orders['Discount Amount'] = orders['Discount Amount'].fillna(0)

orders.columns =orders.columns.str.replace(" ", "_")
orders.rename(columns={"Quantity_(-_Refund)": "Quantity"}, inplace=True)

desc_stat = {}

for col in orders.columns:
    if orders[col].dtype == "object":
        desc_stat[col] = {"Number missing": orders[col].isna().sum()}
    else:
        desc_stat[col] = { "Number missing": orders[col].isna().sum()}

def adjust_prices(row):
  if row['Country_Code(Shipping)'] == 'CZ':
    row['']

desc_stat = pd.DataFrame(desc_stat)
orders = orders.dropna()

Orders_grouped = orders.groupby(["Order_Number", "Order_Status", "Order_Date", "City_(Billing)", 
                         "Postcode_(Billing)", "Country_Code_(Shipping)", "Payment_Method_Title", 
                         "Cart_Discount_Amount", "Cart_Discount_Amount(inc._tax)", 
                         "Order_Subtotal_Amount", "Shipping_Method_Title", 
                         "Order_Shipping_Amount", "Order_Refund_Amount", 
                         "Order_Total_Amount", "Order_Total_Tax_Amount"], as_index=False).agg({
    "Quantity": "sum"
})                        

Orders_grouped["Country_Full_Name"] = Orders_grouped["Country_Code_(Shipping)"].map({"SK": "Slovakia", "CZ": "Czech Republic"})

Orders_SK = Orders_grouped[Orders_grouped["Country_Code_(Shipping)"] == "SK"].reset_index(drop=True)
Orders_CZ = Orders_grouped[Orders_grouped["Country_Code_(Shipping)"] == "CZ"].reset_index(drop=True)
```
