
### Distinguish between Authentication and Authorization
- Authentication 
    - Are you who you say you are?
    - Windows Authentication
    - Forms Authentication - **ASP.NET Identity**
    - OAuth (Open Authentication)
        - 3rd Party
        - JWT - (JSON Web Token)
    - Password Salt (Combining the password the user inputs with a "salt" value)
        - Proccessing the password salt into an encryption
        - If the hash(what comes out of the encryption) is the same with with what matches with a user, then confirms the authorization
- Authorization 
    - What are you able to do/discuss?
    - Always application specific
    - Assigning User to Roles
    - Assigning **User** to **Roles** where **UserRoles** are a 1:M cardinality
    - (1 User can have many UserRoles, 1 role can have many UserRoles)

- User/Role Entities (Entities)
- User Manager (BLL)
- Role Manager (BLL)


