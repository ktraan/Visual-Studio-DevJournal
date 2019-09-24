# ListView
- Is another way to list data instead of a GridView
- Can use ObjectDataSource to populate the ListView by the wizard
- Should have ``<LayoutTemplate></LayoutTemplate>``


``<asp:ListView ID="SupplierListView" runat="server" ItemType="WestWindSystem.Entities.Supplier" DataSourceID="SuppliersDataSource">
    <LayoutTemplate>
    </LayoutTemplate>
</asp:ListView>
``
# Repeater
- Repeaters are another way to display information.
- They are usually only used to display, instead of CRUD.
