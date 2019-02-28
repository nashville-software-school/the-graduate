# Idempotency
Basically, watch this [4 minute video](https://www.restapitutorial.com/lessons/idempotency.html) ;)

The above examples show that GET implies getting the entity you request. It is idempotent which means you’ll receive identical data when performing the same request each time you visit that resource.

Every time you go to `localhost:8000/products/1` you will always get the product data related to the product with id=1

The POST request is not idempotent, which means that if you send the same data in the repeat request, it will create an entity duplicate but with a different identifier (primary key).

If you post a new product to `localhost:8000/products` and then post that exact same data again, it will not return the exact same thing because the id will be different. 
```cs
// first time you post hat
{
  id: 1, 
  name: hat
}
// second time you post hat
{
  id: 2, 
  name: hat
}
```