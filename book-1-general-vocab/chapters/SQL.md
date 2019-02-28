# SQL Structured Query Language 
A language to query/interact with the data in our database

### What’s a JOIN in SQL? 
Bringing data together, at the point where there is an intersection of data. You’ll see below that the intersection between song and album is the album id, which is the primary key on Album and a foreign key on Song.
```sql
select count() as "number of songs", al.title "Album Title"
from Song s
join Album al on al.albumid = s.albumid 
group by al.albumid
```

### What does a WHERE do in SQL? 
Conditional logic to filter the returned dataset based on a certain parameter
```sql
insert into Album
select null, "the title", "2019", 234, "label", artist.ArtistId, Genre.GenreId
from artist, Genre
where Artist.ArtistName = "Black Flag"
and Genre.Label = "Punk"
```

### What is a subquery in SQL? 
A query within another query. In this code below, you’ll see that I am selecting the employee who has the max sales for 2009. That select statement has _another_ select statement within it that calculates the total sales for every employee in the database.
```sql
SELECT Top2009Sales.EmployeeName AS "EmployeeName", MAX(Top2009Sales.Sales) AS "Sales"
FROM (
	SELECT e.FirstName || " " || e.LastName AS "EmployeeName", SUM(i.Total) AS "Sales"
	FROM Employee e, Invoice i, Customer c
	WHERE i.CustomerId == c.CustomerId
	AND c.SupportRepId == e.EmployeeId
	AND i.InvoiceDate BETWEEN "2009-01-01" AND "2009-12-31"
	GROUP BY "EmployeeName"
) AS "Top2009Sales";
```

### What are some aggregate functions in SQL? 

MAX, MIN, COUNT allow you to perform operations on the data in the database (See MAX and SUM from the example above)