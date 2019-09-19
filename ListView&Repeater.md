# ListView
- Is another way to list data instead of a GridView
- Can use ObjectDataSource to populate the ListView by the wizard
- Should have ``<LayoutTemplate></LayoutTemplate>``


``<asp:ListView ID="SupplierListView" runat="server" ItemType="WestWindSystem.Entities.Supplier" DataSourceID="SuppliersDataSource">
    <LayoutTemplate>
        <table class="table table-hover table-condensed">
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Comapny</th>
                    <th>Contact</th>
                    <th>Contact Title</th>
                    <th>Address</th>
                    <th>Phone</th>
                    <th>Fax</th>
                </tr>
            </thead>
            <tbody>
                <tr runat="server" id="itemPlaceholder"></tr>
            </tbody>
        </table>
    </LayoutTemplate>
</asp:ListView>``
