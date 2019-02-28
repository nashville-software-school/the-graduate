# Encapsulation
[Code Example - Python](https://pythonprogramminglanguage.com/encapsulation/)

[Another Python Example](https://medium.com/the-renaissance-developer/python-101-object-oriented-programming-part-2-8e0db3ddd531)

Each object keeps its state private, inside a class - think of modularizing and componentizing your code. 

Other objects don’t have direct access to this state. If you want to communicate with the object, you should use the methods provided. But (by default), you can’t change the state. Python doesn’t have a way to actually protect an object’s state, but there is the convention of using `__` before the property to signal private. In C#, the word `private` is used.

Below is a Python class. 
Line 3: a publicly accessible property
Line 4: a privately accessible property
Line 6: a public setter method to allow ability to update the email property
Line 9: a public getter method to access the email data
```python
1 class Person:
2    def __init__(self, first_name, email):
3        self.first_name = first_name
4        self._email = email
5
6    def update_email(self, new_email):
7        self._email = new_email
8
9    def email(self):
10        return self._email
```
```python
# Using the code:
tk = Person('TK', 'tk@mail.com')
print(tk.email()) # => tk@mail.com
# tk._email = 'new_tk@mail.com' -- treat as a non-public part of the class API
print(tk.email()) # => tk@mail.com
tk.update_email('new_tk@mail.com')
print(tk.email()) # => new_tk@mail.com
```
C# example:
```cs
// Base class
public class Automobile {

    public string Accelerate() {
        InjectFuel();
        return "zoom";
    }

    private string InjectFuel() {
        return "fueling";
    }
}

// Usage Example in a Program.cs file somewhere
Automobile generic_auto = new Automobile();
Console.WriteLine($"Automobiles go {generic_auto.Accelerate()}");

// However, the following line of code does not compile
generic_auto.InjectFuel();
```
