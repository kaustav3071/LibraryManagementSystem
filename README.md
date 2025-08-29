# Library Management System

A simple Library Management System built with ASP.NET Core MVC, Entity Framework Core, and SQL Server using Visual Studio 2022. This application allows users to manage books, members, and borrowing records with basic CRUD operations.

## Features

- **Books Management**: Create, read, update, and delete books with details like title, author, ISBN, and availability.
- **Members Management**: Manage library members with name, email, and join date.
- **Borrowing Records**: Track book borrowing and return, updating book availability automatically.
- **Responsive UI**: Basic styling with Bootstrap and custom CSS for a clean interface.

## Prerequisites

- Visual Studio 2022 with the ASP.NET and web development workload.
- SQL Server Express (or another SQL Server instance).
- .NET 8.0 SDK (or the version matching your project).
- Basic knowledge of C#, ASP.NET Core, and MVC.

## Setup Instructions

1. **Clone or Create the Project**  
   - If cloning, use:  
     ```bash
     git clone <repository-url>
     ```
   - Alternatively, follow the project creation steps in Visual Studio 2022 (ASP.NET Core Web App MVC template).

2. **Install NuGet Packages**  
   Open the project in Visual Studio 2022. In the Package Manager Console, run:  
   ```powershell
   Install-Package Microsoft.EntityFrameworkCore.SqlServer
   Install-Package Microsoft.EntityFrameworkCore.Design
   Install-Package Microsoft.EntityFrameworkCore.Tools
   ```

3. **Configure the Database**  
   Update the connection string in `appsettings.json` to match your SQL Server instance:
   ```json
   "ConnectionStrings": {
     "DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;Database=LibraryDb;Trusted_Connection=True;MultipleActiveResultSets=true"
   }
   ```

4. **Run Migrations**  
   In the Package Manager Console, run:  
   ```powershell
   Add-Migration InitialCreate
   Update-Database
   ```

5. **Run the Application**  
   Press F5 in Visual Studio to build and run the application.  
   The app will open in your default browser at https://localhost:<port>.

## Usage

- **Home Page**: Access links to manage Books, Members, and Borrow Records.  
- **Books**: Add, edit, delete, or view books. Set availability status.  
- **Members**: Manage member details like name, email, and join date.  
- **Borrow Records**: Create borrowing records to track book loans and returns. Book availability updates automatically when a book is borrowed or returned.  
- Navigate using the top menu to access different sections.

## Project Structure

```
Controllers/            - Contains `BooksController`, `MembersController`, and `BorrowRecordsController` for CRUD operations.
Models/                 - Defines `Book`, `Member`, and `BorrowRecord` classes.
Views/                  - Razor views for each model under `Views/Books`, `Views/Members`, and `Views/BorrowRecords`.
Data/                   - Includes `LibraryDbContext` for Entity Framework Core.
wwwroot/                - Static files (CSS, JS) for styling and client-side functionality.
```

## Deployment

1. **Publish the Application**  
   - Right-click the project > Publish > Choose Folder or a cloud platform like Azure.  
   - Publish to a local folder or server.

2. **Database Setup**  
   - Ensure SQL Server is accessible on the deployment server.  
   - Update the connection string in `appsettings.json`.  
   - Apply migrations:  
     ```bash
     dotnet ef database update
     ```

3. **Host**  
   Use IIS, Azure App Service, or another hosting platform.

## Future Enhancements

- Add user authentication with ASP.NET Core Identity.
- Implement search and filter functionality for books and members.
- Enhance UI with advanced styling (e.g., Tailwind CSS).
- Add validation for ISBN and email formats.

## Troubleshooting

- **Database Errors**: Ensure SQL Server Express is running and the connection string is correct.
- **Migration Issues**: Check the Package Manager Console output for errors and verify EF Core Tools are installed.
- **Build Errors**: Confirm all NuGet packages are restored (`dotnet restore`).

## License

This project is licensed under the MIT License.

Thank You
