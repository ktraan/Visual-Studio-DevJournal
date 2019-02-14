# Razor Html Helper Methods

## `.DropDownList()`

I can get an item selected by setting the Selected property for the individual item, as in this code snipet. 

```csharp
    List<SelectListItem> catOptions = new List<SelectListItem>();
    catOptions.Add(new SelectListItem { Value = "", Text = "[Select a Category]" });

    foreach (var item in allCategorys)
    {
        catOptions.Add(new SelectListItem
        {
            Text = item.CategoryName,
            Value = item.CategoryID.ToString(),
            Selected = item.CategoryID.ToString() == categorySelection
        }
        );
    }
```
