# Composition over Inheritance

[Python Resource](http://blog.thedigitalcatonline.com/blog/2014/08/20/python-3-oop-part-3-delegation-composition-and-inheritance/)

[C# Resource](https://scottlilly.com/c-design-patterns-composition-over-inheritance/)

Some devs find that it is better to have DRY code through composition rather than inheritance. Composition is containing instances of other classes that have the preferred functionality in the class, rather than inheriting that functionality from a parent class.

The idea is that composition allows for more flexibility, ability to change and maintain code easier and keeps systems simpler and decouples the system.

You can see inheritance above, but remember when you has a User Model and a Customer Model (Python)? The Customer model had an instance of a User as one of the properties. That’s composition!

```python
class Customer(models.Model):
    user = models.OneToOneField(
        User,
        on_delete=models.DO_NOTHING,
        primary_key=True,
    )
    address = models.CharField(max_length=255)
    phoneNumber = models.CharField(max_length=255)
    deleted = models.BooleanField(default=False)
```
