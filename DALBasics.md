# Data Access Layer Basics

**Make sure the project has Entity Framework for each part and then add the System.Data.Entity reference to the project**

- The DAL class will inherit from Entity Framework's DbContext class in order to get all the functionallity to map our 
entity classes to the database tables.
- You can think of this class as being a virtual representation of the database


1. First create the internal class that inherits from "DbContext"
1. Press CTRL + . on the DbContext to add the namespace System.Data.Entity to the project.
1. Create a default constructor that assigns the base value of your database

`public ConstructorName() : base("name=[insertDBNameHere]"`
   - This will prevent initialization
   
4. Create the properties that align with the Entity Classes
   - When creating the `DbSet<EntitynName>`, press CTRL + . to grab the namespace needed from the other class library
   - Make the names of the properties the same name as the entity but plural.
   - Give the properties default attributes (`{get;set;}`)

```C#
using System;
using System.Collections.Generic;
using System.Data.Entity; // DbContext is in this namespace
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using WestWindModels;

namespace WestWindSystem.DAL
{
    // Our DAL class will inherit from EF's DbContext class
    // in order to get all the functionallity to map our
    // Entity classes to the database tables
    // You can think of this context class as being a 
    // virtual representation of the database.
    internal class WestWindContext : DbContext
    {
        #region Constructors
        public WestWindContext() : base("name=WWdb")
        {
            // We can programmatically prevent the default behavior 
            // that EF uses, which is to create the database if it 
            // can't find it based on the connection string name above.
            Database.SetInitializer<WestWindContext>(null); // Prevent initialization
        }
        #endregion

        #region Properties
        public DbSet<Product> Products { get; set; }
        public DbSet<Supplier> Suppliers { get; set; }
        public DbSet<Category> Categories { get; set; }
        #endregion
    }
}
```
