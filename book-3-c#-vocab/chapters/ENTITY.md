# Entity Framework

Entity is an [ORM](../../book-1-general-vocab/chapters/ORM.md) that abstracts away interacting with your database - that means that it's much less code to write! This means that you don't need to write raw SQL like you did in ADO.NET. Entity creates a SQL query for you and sends it to your database. 

ADO.NET example to get all Departments
```cs
public List<Department> GetAllDepartments()
{
    using (SqlConnection conn = Connection)
    {
        conn.Open();

        using (SqlCommand cmd = conn.CreateCommand())
        {
            cmd.CommandText = "SELECT Id, DeptName FROM Department";

            SqlDataReader reader = cmd.ExecuteReader();

            List<Department> departments = new List<Department>();

            while (reader.Read())
            {
                int idColumnPosition = reader.GetOrdinal("Id");

                int idValue = reader.GetInt32(idColumnPosition);

                int deptNameColumnPosition = reader.GetOrdinal("DeptName");
                string deptNameValue = reader.GetString(deptNameColumnPosition);

                Department department = new Department
                {
                    Id = idValue,
                    DeptName = deptNameValue
                };

                departments.Add(department);
            }

            reader.Close();

            return departments;
        }
    }
}
```

Entity Framework example to get all Departments
```cs
public async Task<IActionResult> Index()
{
    return View(await _context.Department.ToListAsync());
}
```