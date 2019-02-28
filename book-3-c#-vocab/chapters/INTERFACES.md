# Interfaces

[C# NSS Chapter](https://github.com/nashville-software-school/bangazon-inc/blob/master/book-1-orientation/chapters/INTERFACES_INTRO.md)  (with lots of other great resources linked)


The combination of all public methods and properties of an object form the object's public interface. In other words, the public methods and properties form a group of rules that you can depend on. Interfaces define the required behavior for something to be considered a specific type of thing. They do not actually contain the required functionality. An interface is often called a contract.

Imagine a `Pen` class. There are `line()` and `circle()` methods as public methods in `Pen`. You can call them anytime in your code. By contract, being a `Pen` means always having those two methods available and public.

Consider the following reasoning:
`Pen`'s public interface consists of two methods named `line()` and `circle()`
`FountainPen` and `RollerBallPen` descend from `Pen`
Therefore `FountainPen` and `RollerBallPen` can be used to fulfill the same contract as `Pen`, and “draw” a line or circle