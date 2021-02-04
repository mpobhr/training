# Listing Staff 

## Prepare Staff Model
* Create Models folder
* Add Staff.cs file:
```cs
using System;

namespace Hrs
{
    public class Staff
    {
        public int Id { get; set; }
        public string Title { get; set; }
        public string Name { get; set; }
        public string Ic { get; set; }    
        public string Email { get; set; }    
        public string StaffId { get; set; }
        public bool IsPermanent { get; set; }
        public bool IsActive { get; set; }
        public DateTime? CreatedDate { get; set; }
        public DateTime? ModifiedDate { get; set; }
        public int CreatedById { get; set; }
        public int ModifiedById { get; set; }
        public override string ToString() => $"{Title} {Name}";
    }
}
```

* Initialize Staff in Index.cshtml.cs
```cs
public List<Staff> Items { get; set; }

Items = new List<Staff> {
    new Staff { Id = 1, Name = "Anton Heryanto Hasan"},    
};
```

* Listing in Index.cshtml
```html
<table class="table">
<thead>
    <tr>
        <td>Bil</td>
        <td>Nama</td>
    <tr>
</thead>
<tbody>
@{var i = 1;}
@foreach (var item in Model.Items) {
    <tr>
        <td>@(i++).</td>
        <td>@item.Name</td>
    </tr>
}
</tbody>
</table>
```
