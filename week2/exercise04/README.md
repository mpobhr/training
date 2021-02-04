## Setup Database
## Make sure your MariaDB installed and running
* Download MariaDB
* Install MariaDB
* Secure / Set Password
* Run service

## Add MySqlConnector Nuget Package
* using dotnet sdk on project folder 
```shell
src> dotnet add package MySqlConnector
```
* modify Hrs.csproj add section bellow:
```xml
  <ItemGroup>
    <PackageReference Include="MySqlConnector" Version="1.2.1" />
  </ItemGroup>
```

## Connection Setting
* Modify appsettings.Development.json add
```json
"ConnectionStrings": {
    "mysql":"server=localhost;user=root;password=password;database=test" 
},
```

## Uses the configuration on Razor Page
```cs
using Microsoft.Extensions.Configuration;

namespace Hrs.Pages.Staffs
{
    public class IndexModel : PageModel
    {
        readonly string _cn;
        public IndexModel(IConfiguration cfg)
        {
            _cn = cfg.GetConnectionString("mysql");
        }
    }
}

```

### Query and Getting the result
* ADO.NET Connection to Database
```cs
using var cn = new MySqlConnection(_cn); 
cn.Open();
```
* uses ADO.NET Command to Query
```cs
using var cmd = new MySqlCommand(sql, cn);
```
* add Parameter if the Query has parameter
```cs
cmd.Parameters.Add("@id", MySqlDbType.Int32).Value = id;
```

* Uses `Command Reader` to Loop over result
```cs
using var reader = cmd.ExecuteReader();
Items = new List<Staff>();
while (reader.Read()) {
    Items.Add(new Staff {
        Id = (int) reader["Id"],
        Name = reader["Name"].ToString(),
        StaffId = reader["StaffId"].ToString(), 
    });
}
```

* Uses `Command ExecuteNonQuery` to execute non result query
```cs
cmd.ExecuteNonQuery();
```

* For details implementation see [anton-hrs](https://github.com/mpobhr/anton-hrs) [crud branch](https://github.com/mpobhr/anton-hrs/tree/crud/src/Pages/Staffs)