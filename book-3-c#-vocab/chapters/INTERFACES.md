# Interfaces

[C# NSS Chapter](https://github.com/nashville-software-school/bangazon-inc/blob/cohort-30/book-1-orientation/chapters/INTERFACES_INTRO.md)  (with lots of other great resources linked)


An interface in C# is a construct that you define for classes to implement. Think of it as a contract for a class. If a class implements an interface, then it must define a method, property, or event for each one defined in the interface.

Imagine you run a flower shop and you want to create arrangements of flowers for Mother's day and Birthdays. You have roses, sunflowers, hydrangeas, and lilies. 

So, you create your flowers: 

```cs
public class Rose 
{
    public string name {get; set;}
    public boolean spikes {get; set; } = True;
}

public class Sunflower 
{
    public string name {get; set;}
    public boolean seeds {get; set;} = True;
}

public class Hydrangea 
{
    public string name {get; set;}
}

public class Lily 
{
    public string name {get; set;}
    public int stemThickness {get; set;}
}
```

Roses and Sunflowers go in the Mother's day arrangement and Hydrangeas and Lilies go in the birthday arrangement.

A List can only contain one type, so you can do
```cs
public List<Rose> Roses = new List<Rose>();
```

But you can't do
```cs
public List<Rose, Sunflower> MothersDay = new List<Rose, Sunflower>();
```

That's where interfaces come into play!

Let's create a Mother's day and a birthday interface
```cs
public interface IMothersDay
{
    public string ArrangementName {get; set;} = "Mother's Day"
    void addToMothersDayArrangement();
}

public interface IBirthday 
{
    public string ArrangementName {get; set;} = "Birthday"
    void addToBirthdayArrangement();
}
```

Now our classes are going to implement the appropriate interface, based on which arrangement they belong in

```cs
public class Rose : IMothersDay
{
    public string name {get; set;}
    public boolean spikes {get; set; } = True;
}

public class Sunflower : IMothersDay
{
    public string name {get; set;}
    public boolean seeds {get; set;} = True;
}

public class Hydrangea : IBirthday
{
    public string name {get; set;}
}

public class Lily : IBirthday
{
    public string name {get; set;}
    public int stemThickness {get; set;}
}
```

You could then create some instances of each of these flowers and add them to an arrangement list.

```cs
// when you create a new instance of a flower, it will automatically have the interface applied, as well

// Type: Rose, Interface: IMothersDay
Rose pinkRose = new Rose();
// Type: Sunflower, Interface: IMothersDay
Sunflower yellowSunflower = new Sunflower();
// Type: Hydrangea, Interface: IBirthday
Hydrangea blueHydrangea = new Hygrangea();
// Type: Lily, Interface: IBirthday
Lily whiteLily = new Lily();

// This is a list that contains 2 types (rose and sunflower) because they both have the same interface of IMothersDay! 
List<IMothersDay> = new List<IMothersDay>(){
    Rose,
    Sunflower
};

List<IBirthday> = new List<IBirthday>(){
    Hydrangea,
    Lily
}
```