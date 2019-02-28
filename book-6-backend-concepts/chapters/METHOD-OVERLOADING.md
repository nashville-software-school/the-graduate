# Method overloading
[Python Resource](https://pythonspot.com/method-overloading/)

You can define a method that can be used multiple ways. So for a single method, you can have it take a different number of arguments. That single method could be called with zero, one, two, etc parameters.

```python
# Here’s a method that can accept either no arguments or one argument:
obj.sayHello()
obj.sayHello('Guido')

# The output is different, depending on the number or parameters passed in:
Hello
Hello Guido
```

Here’s the code for method overloading example above. The conditional allows different functionality, depending on the number of parameters sent when the method is called.
```python
class Human:
 
    def sayHello(self, name=None):
 
    if name is not None:
        print 'Hello ' + name
    else:
        print 'Hello '
 
# Create instance
obj = Human()
 
# Call the method
obj.sayHello()
 
# Call the method with a parameter
obj.sayHello('Guido')
```

In C#, this is really common when handling a `GET` and `POST` for a form - both methods are called `Create`. The first method doesn't take any arguments, so the form is rendered. The second method takes argument(s), so that method is run.
```cs
 // GET: PaymentTypes/Create
public IActionResult Create()
{
    return View();
}

// POST: PaymentTypes/Create
[HttpPost]
[ValidateAntiForgeryToken]
public async Task<IActionResult> Create([Bind("PaymentTypeId,AccountNumber,UserId")] PaymentType paymentType)
{
    var user = await GetCurrentUserAsync();
        paymentType.User = user;
        paymentType.UserId = user.Id;

// more code goes here, of course ;)
```