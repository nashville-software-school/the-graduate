# Interfaces

[C# NSS Chapter](https://github.com/nashville-software-school/bangazon-inc/blob/cohort-30/book-1-orientation/chapters/INTERFACES_INTRO.md)  (with lots of other great resources linked)


An interface in C# is a construct that you define for classes to implement. Think of it as a contract for a class. You can define methods and properties in an interface, and any class that implements that interface must "follow" those rules in the interface. If a class implements an interface, then it must define a method, property, or event for each one defined in the interface.

Imagine you run a flower shop and you want to create arrangements of flowers for Mother's day and Birthdays. You have roses, sunflowers, hydrangeas, and lilies. 

So, you create your flowers: 

```cs
public class Rose 
{
    public string Name {get; set;}
    public bool Thorny {get; set; } = True;
}

public class Sunflower 
{
    public string Name {get; set;}
    public bool Seeds {get; set;} = True;
}

public class Hydrangea 
{
    public string Name {get; set;}
}

public class Lily 
{
    public string Name {get; set;}
    public int StemThickness {get; set;}
}
```

Roses and Sunflowers go in the Mother's day arrangement and Hydrangeas and Lilies go in the birthday arrangement.

A List can only contain one type, so you can do this:
```cs
public List<Rose> Roses = new List<Rose>();
```

But you can't do this:
```cs
public List<Rose, Sunflower> MothersDay = new List<Rose, Sunflower>();
```

This is where interfaces come into play!

Let's create a Mother's day and a birthday interface
```cs
public interface IMothersDay
{
    public string ArrangementName {get; set;}

    // note: method logic does not go in the interface itself. You can define methods here, but create the logic in another class (see Rose and Sunflower classes below).
    void TrimStems();
}

public interface IBirthday 
{
    public string ArrangementName {get; set;}
}
```

Now our classes are going to implement the appropriate interface, based on which arrangement they belong in (this <em>looks</em> like inheritance, but interfaces are implemented, not inherited).

```cs
public class Rose : IMothersDay
{
    public string Name {get; set;}
    public bool Thorny {get; set; } = True;
    public string ArrangementName {get; set;}  = "Mother's Day";

    // this is a method that is unique to a rose
    public void removeThorns()
    {
        Thorny = False;
    }

    // this method must be implemented in some way in the Rose class because Rose is using the IMothersday interface, which has defined a TrimStems() method. 
    public void TrimStems()
    {
        Console.WriteLine("You trimmed the Rose's stem!");
    }
}

public class Sunflower : IMothersDay
{
    public string Name {get; set;}
    public bool Seeds {get; set;} = True;
    public string ArrangementName {get; set;}  = "Mother's Day";

    // notice how this method also implements the TrimStems() method, but the Console.WriteLine is different from Rose. The logic can be different for each class's "version" of the TrimStems() method.
    public void TrimStems()
    {
        Console.WriteLine("You trimmed the Sunflowers's stem!");
    }
}

public class Hydrangea : IBirthday
{
    public string Name {get; set;}
    public string ArrangementName {get; set;}  = "Birthday";
}

public class Lily : IBirthday
{
    public string Name {get; set;}
    public int StemThickness {get; set;}
    public string ArrangementName {get; set;}  = "Birthday";
}
```

You could then create some instances of each of these flowers and add them to an arrangement list.

```cs
// when you create a new instance of a flower, it will have two types: type of flower and type of arrangement interface

// Type: Rose, Interface: IMothersDay
Rose pinkRose = new Rose();
// Type: Sunflower, Interface: IMothersDay
Sunflower yellowSunflower = new Sunflower();
// Type: Hydrangea, Interface: IBirthday
Hydrangea blueHydrangea = new Hydrangea();
// Type: Lily, Interface: IBirthday
Lily whiteLily = new Lily();

// This is a list that contains 2 types (Rose and Sunflower) because they both have the same interface of IMothersDay
List<IMothersDay> mothersdayFlowers = new List<IMothersDay>(){
    Rose,
    Sunflower
};

List<IBirthday> birthdayFlowers = new List<IBirthday>(){
    Hydrangea,
    Lily
}

// calling some of the methods from the Rose class, Sunflower Class, and IMothersday interface 
pinkRose.TrimStems();
yellowSunflower.TrimStems();
pinkRose.removeThorns();

// or, if you want to trim all of the stems in a specific list, you can simply foreach over the list of mothersdayFlowers and call that method
mothersdayFlowers.ForEach(flower => flower.TrimStems());


```
