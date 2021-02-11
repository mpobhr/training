# ADO.NET Get and Update Data
```cs
public void Edit(int id = 0) 
{
    using var cn = new MySqlConnection(_cn);
    using var cmd = new MySqlCommand(sql, cn);
    cmd.Parameters.Add("@id", MySqlDbType.Int32).Value = id;
    using var reader = cmd.ExecuteReader();
    Items = new List<Staff>();
    if (reader.Read()) {
        Items.Add(new Staff {
            Id = (int) reader["Id"],
            Name = reader["Name"].ToString(),
            StaffId = reader["StaffId"].ToString(), 
        });
    }
}
```