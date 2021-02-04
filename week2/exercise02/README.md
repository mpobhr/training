## Show Details Staff
* Create folder Staffs
* copy Index.cshtml and Index.cshtml.cs
* modify Index.cshtml.cs
```cs
namespace Hrs.Pages.Staffs
{
    public class IndexModel : PageModel
    {
        public List<Staff> Items { get; set; } 
        public Staff Item { get; set; }
        public void OnGet(int id = 0)
        {            
            Items = new List<Staff> {
                new Staff { StaffId="K01231", Name = "Anton Heryanto Hasan" },
                new Staff { StaffId="K01232", Name = "Aishah Rodzi" },
                new Staff { StaffId="K01233", Name = "Faiq ITCS" },
                new Staff { StaffId="K01234", Name = "Liyana" },
                new Staff { StaffId="K01235", Name = "Muhamad Zul Razak" },
            };

            if (id > 0) {
                Item = Items[id];
            }
        }
    }
}
```
* modify Index.cshtml
```html
@page "{id?}"
@model IndexModel
@{
    ViewData["Title"] = Model.Item != null ? "Details": "Listing";
    int i = 1;
}

@if (Model.Item != null) {
<div class="card">
    <div class="card-body">
        @Model.Item
    </div>
</div>

} else {
<h2>Senarai Peserta Latihan</h2>
<table class="table table-bordered">
    <thead>
        <tr>
            <th>Bil</th>
            <th>Nama</th>
            <th>No Pekerja</th>
        </tr>
    </thead>
    <tbody>
        @foreach (var item in Model.Items)
        {
            <tr>
                <td>@(i++).</td>
                <td>@item</td>
                <td>@item.StaffId</td>
            </tr>
        }
    </tbody>
</table>
}
```