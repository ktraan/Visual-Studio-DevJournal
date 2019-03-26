# Web forms with accessing database

* There are three components to creating a web form that are important
  * Presentation Layer (WebForm)
  * Business Logic Layer (BLL - SystemClassLibrary)
  * Data Access Layer (DAL - SystemClassLibrary)
  
  
**There should be two different class libraries:**
  * The BLL and the DAL should be seperate folders under a class library called '....system'
  * The other should be one with the classes for each table in the database
  
**In the BLL Folder, there should be a Controller class**
  * This Controller.cs file will help us with CRUD maintenance of our database
**Make sure that the namespace you are using FOR BLL are:**
* The other class library
* the DAL folder
* the any other folders in the same class library.
**In the DAL Folder, make sure to use the other class library namespace**

