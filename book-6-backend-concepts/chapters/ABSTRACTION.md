# Abstraction
Each object should only expose a high-level mechanism for using it and should hide internal implementation details. It should only reveal operations relevant for the other objects.

![abstraction](../images/abstraction.png)

Another example, you want to make things run - you create a run function and are able to call it on human/animal instances to make those instances run. If you were to abstract this method, the other developers wouldn’t be able to really see the code behind your run function, but they know that they can do `human_instance.run()` and it will make that instance run. 

Another example that’s abstracted away from you: 
Django ORM and Entity Framework ORM - you don’t see the SQL behind the scenes in this code, but that’s what it is doing to interact with your database - imagine everything under the hood to get the `get_object_or_404` or the `_context.Department.ToListAsync()` method to work! You don’t have to worry about how it does what it does, because it’s just there for you to use and you know how to use it.