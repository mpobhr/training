## Show Edit Staff
* copy Index.cshtml and Index.cshtml.cs
* rename Index.cshtml to Edit.cshtml and Index.cshtml.cs to Edit.cshtml.cs
* modify Edit.cshtml.cs
```cs 
namespace Hrs.Pages.Staffs
{
    public class EditModel : PageModel
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
                Item = Items[id - 1];
            }
        }
    }
}
```
* modify Edit.cshtml
```html
@page "{id?}"
@model EditModel
@{
    ViewData["Title"] = Model.Item != null ? "New Staff": "Edit Staff";
}

<form class="card">
    <div class="card-body">
        <div class="form-group">
            <label asp-for="Item.Name"></label>
            <input asp-for="Item.Name">
        </div>
    </div>
</form>

```