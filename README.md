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

## Passo a Passo para Criar o Projeto

1. **Criar a Estrutura do Projeto**
   - No terminal, navegue até o diretório desejado e crie a estrutura do projeto:
     ```
     mkdir -p aspnetcore-mvc-identity-postgres/src/WebApp
     cd aspnetcore-mvc-identity-postgres/src/WebApp
     dotnet new mvc -n WebApp
     ```

2. **Adicionar Pacotes Necessários**
   - Adicione os pacotes do Entity Framework Core e do PostgreSQL:
     ```
     dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL
     dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore
     ```

3. **Criar o `ApplicationDbContext`**
   - Crie o arquivo `ApplicationDbContext.cs` em `src/WebApp/Data`.

4. **Configurar o `Program.cs`**
   - Altere o `Program.cs` para registrar o DbContext e o Identity.

5. **Configurar o `appsettings.json`**
   - Adicione a string de conexão ao `appsettings.json`.

6. **Criar o `Dockerfile`**
   - Crie o `Dockerfile` em `src/WebApp`.

7. **Criar o `docker-compose.yml`**
   - Crie o `docker-compose.yml` na raiz do projeto.

8. **Criar o `init-db.sql`**
   - Crie o arquivo `init-db.sql` em `scripts` para inicializar o banco de dados.

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

## Problemas Comuns

- Se o Docker Desktop não estiver rodando, inicie-o.
- Se a porta 5000 estiver ocupada, altere a porta no `docker-compose.yml`.
- Se o volume já estiver inicializado, você pode removê-lo com:
  ```
  docker volume rm aspnetcore-mvc-identity-postgres_pgdata
  ```

## Contribuições

Sinta-se à vontade para contribuir com melhorias ou correções.