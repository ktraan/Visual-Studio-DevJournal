# Useful dotef commands

- Creating first migration
  `dotnet ef migrations add InitialCreate`

  - Use this command if there are updates to the models
  - Same syntax to make any other migrations

- Creating the database & schema
  ` dotnet ef database update`
  - Make sure to have the DB connected
  - Run this command after adding any migration to update
