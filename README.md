# aspnetcore-mvc-identity-postgres

Este projeto é uma aplicação ASP.NET Core MVC que utiliza o Identity para autenticação e o Entity Framework Core com PostgreSQL como banco de dados. A aplicação é containerizada usando Docker e Docker Compose.

## Estrutura do Projeto

```
aspnetcore-mvc-identity-postgres
├── src
│   └── WebApp
│       ├── WebApp.csproj
│       ├── Program.cs
│       ├── appsettings.json
│       ├── appsettings.Development.json
│       ├── Dockerfile
│       ├── Controllers
│       │   └── HomeController.cs
│       ├── Areas
│       │   └── Identity
│       │       ├── IdentityHostingStartup.cs
│       │       └── Pages
│       │           └── Account
│       │               └── Login.cshtml
│       ├── Data
│       │   ├── ApplicationDbContext.cs
│       │   └── Migrations
│       │       └── (EF Core migrations)
│       ├── Models
│       │   └── ApplicationUser.cs
│       ├── Services
│       │   └── IEmailSender.cs
│       ├── Views
│       │   ├── Home
│       │   │   └── Index.cshtml
│       │   └── Shared
│       │       └── _Layout.cshtml
│       └── wwwroot
│           ├── css
│           │   └── site.css
│           └── js
│               └── site.js
├── docker-compose.yml
├── docker-compose.override.yml
├── .dockerignore
├── scripts
│   └── init-db.sql
├── WebApp.sln
└── README.md
```

## Comandos para Executar

- Para restaurar as dependências:
  ```
  dotnet restore
  ```

- Para compilar o projeto:
  ```
  dotnet build
  ```

- Para iniciar os containers:
  ```
  docker compose up -d
  ```

- Para executar a aplicação:
  ```
  dotnet run
  ```
