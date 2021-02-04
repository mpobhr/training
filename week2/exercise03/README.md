## Show Edit Staff
* copy Index.cshtml and Index.cshtml.cs
* rename Index copy.cshtml to Edit.cshtml and Index copy.cshtml.cs to Edit.cshtml.cs
* modify Edit.cshtml.cs
```cs 
namespace Hrs.Pages.Staffs
{
    public class EditModel : PageModel
    {
        public List<Staff> Items { get; set; } 
        [BindProperty] public Staff Item { get; set; }
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

        public IActionResult OnPost()
        {
            if (string.IsNullOrEmpty(Item.Name))
                return Page();
            
            return Redirect("~/staffs");
        }
    }


}
```
* modify Edit.cshtml
```html
@page "{id?}"
@model EditModel
@{
    ViewData["Title"] = Model.Item != null ? "Edit Staff": "New Staff";
}

<form class="card" method="post">
    <div class="card-body">
        <div class="form-group">
            <label asp-for="Item.Name"></label>
            <input asp-for="Item.Name" class="form-control">
        </div>
        <div class="form-group">
            <button class="btn btn-primary">Save</button>
        </div>
    </div>
</form>

```