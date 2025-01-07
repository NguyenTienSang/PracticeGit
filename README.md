run file docker-compose.yml: docker-compose up -d

Step 1: add command to add migration PersistedGrant: 
`dotnet ef migrations add InitialPersistedGrantMigration -c PersistedGrantDbContext -o Persistence/Migrations/IdentityServer/PersistedGrantDb`
or
`add-migration InitialPersistedGrantMigration -c PersistedGrantDbContext -o Persistence/Migrations/IdentityServer/PersistedGrantDb`

Step 2: add command to add migration Configuration: 
`dotnet ef migrations add InitialConfigurationMigration -c ConfigurationDbContext -o Persistence/Migrations/IdentityServer/ConfigurationDB`
or
`add-migration InitialConfigurationMigration -c ConfigurationDbContext -o Persistence/Migrations/IdentityServer/ConfigurationDB`


Step 3: `dotnet ef migrations add Init_Identity -c EcommerceIdentityContext -o Persistence/Migrations`
or
`add-migration Init_Identity -c EcommerceIdentityContext -o Persistence/Migrations`

Step 4: run command to update database 
`dotnet ef database update-context PersistedGrantDbContext`
`dotnet ef database update-context ConfigurationDbContext`
`dotnet ef database update-context EcommerceIdentityContext`
or
`update-database -context PersistedGrantDbContext`
`update-database -context ConfigurationDbContext`
`update-database -context EcommerceIdentityContext`


