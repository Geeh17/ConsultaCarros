# 🚗 DriveControl

**DriveControl** é um sistema completo para o gerenciamento de veículos, com API RESTful em ASP.NET Core e front-end moderno usando Blazor WebAssembly.

---

## 🧩 Estrutura do Projeto

- **Back-End:** ASP.NET Core Web API + Dapper + SQL Server
- **Front-End:** Blazor WebAssembly + Bootstrap + Chart.js

---

## 🚀 Como Executar o Projeto

### 1. Clone o repositório

```bash
git clone https://github.com/Geeh17/ConsultaCarros
cd DriveControl
```

---

### 2. Configurar o Banco de Dados

- Crie o banco:

```sql
CREATE DATABASE DriveControlDB;
GO

USE DriveControlDB;
GO

CREATE TABLE [dbo].[Carros] (
    [Id] INT IDENTITY(1,1) NOT NULL PRIMARY KEY,
    [Modelo] VARCHAR(100) NOT NULL,
    [Preco] DECIMAL(18, 2) NOT NULL
);
```

- Configure a **string de conexão** no `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=DriveControlDB;Trusted_Connection=True;"
}
```

---

### 3. Rodar o Back-End

```bash
cd Carros/Carros
dotnet restore
dotnet run
```

A API estará disponível em: `https://localhost:7192`

---

### 4. Rodar o Front-End

```bash
cd ../../CarrosClient/CarrosClient
dotnet restore
dotnet run
```

O app Blazor estará em: `https://localhost:5001`

---

## 📘 Documentação da API

### `GET /api/carros`

Retorna todos os carros cadastrados.

```bash
curl -X GET "https://localhost:5001/api/carros"
```

### `GET /api/carros/{id}`

Busca um carro específico por ID.

```bash
curl -X GET "https://localhost:5001/api/carros/1"
```

### `POST /api/carros`

Cria um novo carro.

```bash
curl -X POST "https://localhost:5001/api/carros" -H "Content-Type: application/json" -d '{
  "marca": "Toyota",
  "modelo": "Corolla",
  "ano": 2020
}'
```

### `PUT /api/carros/{id}`

Atualiza um carro existente.

```bash
curl -X PUT "https://localhost:5001/api/carros/1" -H "Content-Type: application/json" -d '{
  "marca": "Toyota",
  "modelo": "Corolla",
  "ano": 2021
}'
```

### `DELETE /api/carros/{id}`

Remove um carro do sistema.

```bash
curl -X DELETE "https://localhost:5001/api/carros/1"
```

---

## 📊 Dashboard

A dashboard mostra:

- Total de carros
- Preço médio
- Mais barato / mais caro
- Gráfico interativo via `Chart.js`

---

## 📎 Recursos

- Projeto 100% em C# com Dapper (sem EF Core)
- Blazor com layout moderno e responsivo
- Integração via `JSInterop` para gráficos
- Validações, feedbacks visuais e UX melhorado

---

## 📚 Links Úteis

- [Documentação .NET (C#)](https://learn.microsoft.com/en-us/dotnet/csharp/)
- [Blazor WebAssembly](https://learn.microsoft.com/pt-br/aspnet/core/blazor/?view=aspnetcore-8.0)

---

## 👤 Autor

Desenvolvido por [@Geeh17](https://github.com/Geeh17)  


