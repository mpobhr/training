# ADO.NET Get and Update Data
```cs
public void OnGet(int id = 0) 
{
    using var cn = new MySqlConnection(_cn);
    using var cmd = new MySqlCommand(sql, cn);
    cmd.Parameters.Add("@id", MySqlDbType.Int32).Value = id;
    using var reader = cmd.ExecuteReader();
    Items = new List<Staff>();
    while (reader.Read()) {
        Items.Add(new Staff {
            Id = (int) reader["Id"],
            Name = reader["Name"].ToString(),
            StaffId = reader["StaffId"].ToString(), 
        });
    }
}

public IActionResult OnPost()
{
    if (string.IsNullOrEmpty(Item.Name))
        return Page();
    var sql = Item.Id == 0 ? "insert into staffs (Id, Name, StaffId) values(@Id, @Name, @StaffId)"
     : "update staffs set Name=@Name, StaffId=@StaffId where Id=@Id";
    using var cn = new MySqlConnection(_cn); 
    using var cmd = new MySqlCommand(sql, cn);
    cmd.Parameters.Add("@Id", MySqlDbType.Int32).Value = Item.Id;
    cmd.Parameters.Add("@Name", MySqlDbType.VarString).Value = Item.Name;
    cmd.Parameters.Add("@StaffId", MySqlDbType.VarString).Value = Item.StaffId;
    cn.Open();
    cmd.ExecuteNonQuery();
    cn.Close();
    return RedirectPage("Index");
}
```
