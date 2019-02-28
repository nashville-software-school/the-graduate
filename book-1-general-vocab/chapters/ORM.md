# ORM (Object Relational Mapper)
A tool that lets you query and manipulate data from a database using an object-oriented paradigm. When talking about ORM, most people are referring to a library that implements the Object-Relational Mapping technique, hence the phrase "an ORM". 

English explanation of ORM: So, if you aren’t using an ORM, you’d be writing raw SQL queries in your code to interact with data in the database. An ORM abstracts all that away so you don’t see any SQL queries (but it’s happening behind the scenes!). 

Python ORM Example to get all Departments from database:
```python
departments = Department.objects.all()
```

C# Entity Framework Example to get all Departments from database:
```cs
public async Task<IActionResult> Index()
{
    return View(await _context.Department.ToListAsync());
}
```