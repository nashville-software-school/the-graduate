# Classes
[Python Class Resources](https://medium.com/the-renaissance-developer/python-101-object-oriented-programming-part-1-7d5d06833f26)

[C# Class Resources](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/classes)

Python and C# are object-oriented programming languages. We use classes to keep related things together. A class can have attributes and/or methods. 

Objects are a representation of the real world objects like cars, dogs, bike, etc. The objects share two main characteristics: data and behavior.

Cars have data like number of wheels, number of doors, seating capacity and also have behavior: accelerate, stop, show how much fuel is missing and so many other.

We call data as attributes and behavior as methods in object oriented programming. 

A Class is the blueprint from which individual objects are created. In the real world we often find many objects with all the same type. Like cars. Most cars have an engine, wheels, doors, etc. Each car was built from the same set of blueprints and has the same components.

Python example:
```python
class Vehicle:
    def __init__(self, number_of_wheels, seating_capacity, color):
        <!-- These are properties that define what a Vehicle looks like -->
        self.number_of_wheels = number_of_wheels
        self.seating_capacity = seating_capacity
        self.color = color

    <!-- This is a method that defines a behavior of the Vehicle -->
    def make_noise(self):
        print('VRUUUUUUUM')
```
C# example:
```cs
public class Vehicle
{
    <!-- These are properties that define what a Vehicle looks like -->
    [Key]
    public int VehicleId { get; set; }

    [Display(Name="Number of Wheels")]
    [Required]
    public int NumberOfWheels { get; set; }

    [Display(Name="Seating Capacity")]
    [Required]
    public int SeatingCapacity { get; set; }

    [Display(Name="Is car sold")]
    [Required]
    public boolean IsSold { get; set; } = False

    <!-- This is a method that defines a behavior of the Vehicle -->
    public void MakeNoise()
    {
        Console.WriteLine("VRUUUUUM");
    }
}
```