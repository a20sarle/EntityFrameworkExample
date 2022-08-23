Database using EF Core Code First
# Init

## Requirements for updating database using migrations
- ~~```context.Database.Migrate();``` must be used in the builder / Startup.cs file.~~  Don't use ```context.Database.Migrate();```, fails silently. ```EnsureCreated()``` does not create the database based on the migration history and therefore it doesn't let the database to be updated using migrations [1].
- The database needs to have one table storing all the migrations, the autogenerated file is called "__EFMigrationsHistory".
- Install EF Core command-line tools using `Install-Package Microsoft.EntityFrameworkCore.Tools` in Package Manager Console [2] to manage migrations from CLI [3].

[1]: https://stackoverflow.com/questions/38238043/how-and-where-to-call-database-ensurecreated-and-database-migrate
[2]: https://docs.microsoft.com/en-us/ef/core/cli/powershell
[3]: https://docs.microsoft.com/en-us/ef/core/managing-schemas/migrations/managing?tabs=vs
