# DataBound Controls

- .DataSource - Programmatically give the control it's data
- .DataSourceID - Hook up the control to another control which will supply the data (ObjectDataSource)

**You only choose one of the DataSource or DataSourceID**
- .Databind() - Tell the control to extract or display the data

**The data can be sent back to:**
- Gridview
- DropDownList
  - CheckBoxList
  - RadioButtonList
- ListView (Can operate all CRUD functionallity)
- Repeater

# To Connect the BLL To ObjectDataSource

- Go to your desired BLL Controller
- **Before** the class and after the namespace, Type in `[DataObject]` and CTRL + .
- **After** the class, type in `[DataObjectMethod(DataObjectMethodType.Select)]`
- Go back to the .aspx page and click the little arrow underneath the ObjectDataSource/GridView and Choose Data Source
