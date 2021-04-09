# Gridview Usage References

- Programmatically - Here you set the ```.DataSource``` property, then you call ```.DataBind()```
  - Caveats - When you take programmatic control, then you are responsible for keeping it populated if the underlying data changes. If you are using paging then you will need to do the following to keep it up todte
  - In the ```.aspx```, you will need to create an event handler for the ```OnPageIndexChanging``` event.
  - In that handler, you will use the second parameter, the ```GridViewPageEventArgs``` object to get the ```.NewPageIndex```. Set the GridView's ```.PageIndex``` to that value, then re-populate the control. For Example: 
  
```C#
protected void CourseResultList_PageIndexChanging(object sender, GridViewPageEventArgs e)
{
    // set the new page index on the Gridview
    CourseResultList.PageIndex = e.NewPageIndex;

    //refresh the GridView from its data source
    ToolsController systemmgr = new ToolsController();
    List<Course> courseInfo = systemmgr.GetCourses();
    CourseResultList.DataSource = courseInfo;
    CourseResultList.DataBind();
}
```
  - ```<asp:ObJectDataSource>``` **Control** - Here, you can have the GridView's ```DataSourceID``` property set to the ID of an ```<asp:ObjectDataSource>``` control.
    - Make sure your BLL class has the ```[DataObject]``` attribute
    - Use the ```[DataObjectMethod]``` on your method that returns data. The "type" should be for ```Selecting``` data.
    - If you are using paging, then you **do NOT** want to use code-behind to refresh the GridView's contents. The ```ObjectDataSource``` will do that for you.
    
# Customizing the GridView
Details can be found here: https://dmit-2018.github.io/topics/aspNet/databound/gridviewCustomization.html
    
In general, you want to:
  - Use a ```<TemplateField```> with an ```<ItemTemplateField>```
  - Inside the ```<ItemTemplate>```, put whatever controls you want to use, DropDownList ect. 
  - Example:
  
```C#
<asp:TemplateField HeaderText="Supplier">
    <ItemTemplate>
        <asp:DropDownLIst ID="SupplierDropDown" runat=server
        SelectedValue="<%# Item.SupplierID %>"
        DataSourceID="SupplierDataSource">
        </asp:DropDownList>
    </ItemTemplate>
</asp:TemplateField>
```
  - The DropDown's ```SelectedValue``` is set to the GridView data object property that acts as the foreign key.
  - The DropDown's content can come from an ObjectDataSource
  
  
### References
- GridView Control
  - https://dmit-2018.github.io/topics/aspNet/databound/gridviewOverview.html
- Customizing GridView
  - https://dmit-2018.github.io/topics/aspNet/databound/gridviewCustomization.html
