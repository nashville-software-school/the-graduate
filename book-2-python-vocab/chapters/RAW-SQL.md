# Writing Raw SQL in Python
You can query your SQLite database with raw SQL in two ways.

1. Using the `raw()` method. This method works only with SELECT statements. This method does go through your models to access the data.

Example: 
`all_products = Product.objects.raw("SELECT * from website_product")`

2. Using the cursor connection. This creates a direct connection to your database and bypasses your models (and their restrictions) completely.

Example: 
```sql
sql = "INSERT INTO website_product VALUES(%s, %s, %s, %s, %s, %s)"
    product_params = [
        None,
        p_form_data['title'],
        p_form_data['description'],
        p_form_data['price'],
        p_form_data['quantity'],
        p_form_data['category']
    ]

    with connection.cursor() as cursor:
        cursor.execute(sql, product_params)
        product_id = cursor.lastrowid
```


