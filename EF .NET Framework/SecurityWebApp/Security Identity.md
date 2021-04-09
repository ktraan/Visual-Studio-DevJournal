- Using a BLL controller creates a more secure connection from the Presentation Layer to the Business Logic Layer
- Add ``internal`` to a class will add another layer of security



## Creating Security Class

### The following will prevent us from hardcoding values in our code:

- This will be in the web.config above the connectionString
```csharp
  <appSettings>
    <add key="adminRole" value="Administrators"/>
    <add key="userRole" value="Register Users"/>
  </appSettings>
```

- This will be in the Settings class
```csharp
namespace WebApp.Admin.Security
{
    /// <summary>
    /// A collection of application-wide settings that provide values for 
    /// security roels which have been set in the web.config's <appSettings /> section
    /// </summary>
    public static class Settings
    {
        public static string AdminRole => ConfigurationManager.AppSettings["adminRole"];
        /* The above is the same as typing:
         * public static string AdminRole
         * {
         *      get { return ConfigurationManager.AppSettings["adminRole"] }
         * }
         * 
         */
         public static string UserRole => ConfigurationManager.AppSettings["userRole"];
    }
}
```