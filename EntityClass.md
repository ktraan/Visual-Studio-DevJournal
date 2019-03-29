# Creating Entity Classes

**First make sure that you are connected to your database**

**Next make sure that this Class Library is the data one, not the one with the BLL/DAL layer**

1. First create a class in the class library, and name it after the entity table (usually name it singular)
1. Start typing [Table] and press CTRL + . and add the namespace, it is ``` System.ComponentModel.DataAnnotations; ```
1. The format should me ```[Table("InsertTableNameHere", Schema = "dbo")]```
1. Make the class public
1. Add the namespace for ```[Key]```
1. Create the entity's of the table as auto-implemented properties - ``` { get; set; } ```

```C#
namespace WestWindModels
{
  using System.ComponentModel.DataAnnotations;
  using System.ComponentModel.DataAnnotations.Schema;
 
    [Table("Categories", Schema = "dbo")]
    public class Category
    {
        [Key]
        public int CategoryID { get; set; }
        public string CategoryName { get; set; }
        public string Description { get; set; }
        public byte[] Picture { get; set; }
        // varbinary is an aray of bytes in C#
        // Arrays are by nature reference types
        // varbinary is NULL
        public string PictureMimeType { get; set; }
    }
}
```

- Primitive Value Types can be made "nullable" by adding a ? after the data type -  decimal?
- Strings are reference types and can store null values by definition


- This example is a better way of getting the information from the DB
```C#
private string _PhotoMimeType;  // use a field as my "backing store"
public string PhotoMimeType     // an explicity implemented property
{
  get { return _PhotoMimeType; }
  set
  {
    if(string.IsNullOrWhiteSpace(value))
      _PhotoMimeType = null;
    else
      _PhotoMimeType = value.ToLower();
  }
}
```


- You can also have a [NotMapped] property
  - This property does not correspond with a column in the table
  ```C#
  [NotMapped]
  public string FullName { get { return $"{TitleOfCourtesy} {FirstName} {LastName}".Trim(); } }
  
  [NotMapped]
  public string FormalName { get { return $"{LastName}, {FirstName}"; } }
  ```
