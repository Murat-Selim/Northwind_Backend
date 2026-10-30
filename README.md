# Northwind Backend

A layered C# learning API built around the Northwind product catalog. It includes product/category operations and authentication-related code.

Related client: [Northwind Frontend](https://github.com/Murat-Selim/Northwind_Frontend).

## Structure

- `WebAPI/`: ASP.NET Core HTTP endpoints.
- `Business/`: services, validation, and dependency injection.
- `DataAccess/`: Entity Framework persistence, including `NorthwindContext`.
- `Entities/`: domain models.
- `Core/`: shared infrastructure.
- `ConsoleUI/`: console examples.

## Requirements and configuration

The application targets .NET Core 3.1 and uses SQL Server. This legacy target should be migrated before production use.

Prepare your own development Northwind database. Review the connection configuration in `DataAccess/Concrete/EntityFramework/NorthwindContext.cs` and the settings under `WebAPI/`; machine-specific connection values must be adapted locally. Do not publish database passwords or token signing secrets.

```sh
git clone https://github.com/Murat-Selim/Northwind_Backend.git
cd Northwind_Backend
dotnet restore MyFinalProject.sln
dotnet build MyFinalProject.sln
dotnet run --project WebAPI/WebAPI.csproj
```

The `WebAPI` launch profile lists `https://localhost:5001` and `http://localhost:5000`; IIS Express uses a different port. Use the actual URL printed at startup and align the frontend service URLs accordingly. Controller routes are in `WebAPI/Controllers/`.

## Validation

No dedicated automated test project is included. Build the solution, start it against a development database, and exercise the affected endpoint. Successful compilation alone does not verify database connectivity or authentication.

## License and attribution

No repository-wide license file is currently declared. This is a course-style learning repository; preserve applicable third-party notices.
