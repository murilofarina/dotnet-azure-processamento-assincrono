# Processamento Assíncrono de Notificações

Aplicação full-stack desenvolvida durante a **Infoeste 2026**, com o objetivo de explorar conceitos de processamento assíncrono, arquitetura de software e comunicação entre serviços.

O projeto utiliza **C# e ASP.NET Core** no backend, com uma interface desenvolvida em **React e TypeScript**, permitindo gerenciar e acompanhar o processamento de notificações.

## Tecnologias utilizadas

### Backend
- **C# / .NET** — Desenvolvimento da aplicação
- **ASP.NET Core Web API** — Exposição dos endpoints HTTP
- **Worker Service** — Execução de tarefas em segundo plano
- **Injeção de Dependência** — Gerenciamento de serviços e suas dependências
- **Azure Service Bus** — Componentes de mensageria presentes na estrutura do projeto

### Frontend
- **React** — Construção da interface
- **TypeScript** — Tipagem estática
- **Vite** — Ambiente de desenvolvimento e build
- **CSS** — Estilização da aplicação

## Arquitetura do projeto

A solução está organizada em três projetos principais no backend e uma aplicação frontend independente.

```text
processamento-assincrono/
│
├── BackEnd/
│   ├── API/
│   │   ├── Controllers/
│   │   └── Program.cs
│   │
│   ├── Core/
│   │   ├── Enums/
│   │   ├── Interfaces/
│   │   ├── Models/
│   │   ├── Repositories/
│   │   └── Services/
│   │
│   ├── Worker/
│   │   ├── Program.cs
│   │   └── Worker.cs
│   │
│   └── Infoeste2026_ProcessamentoAssincrono.sln
│
├── FrontEnd/
│   ├── src/
│   │   ├── App.tsx
│   │   ├── App.css
│   │   └── main.tsx
│   ├── package.json
│   └── vite.config.ts
│
└── .gitignore
```

### API

Responsável por receber requisições HTTP, disponibilizar os endpoints de notificações e intermediar a comunicação com os serviços da aplicação.

### Core

Centraliza os modelos, interfaces e serviços relacionados às regras de negócio, buscando manter as responsabilidades organizadas e desacopladas.

### Worker

Serviço responsável por executar tarefas em segundo plano, permitindo que operações de processamento sejam realizadas independentemente do ciclo de requisições HTTP.

### Frontend

Interface desenvolvida em React e TypeScript, responsável pela interação com o usuário e pela comunicação com a API.

## Fluxo de funcionamento

O projeto explora a separação entre o recebimento das solicitações e a execução das tarefas de processamento.

```text
      Frontend (React)
             |
             | HTTP
             v
      ASP.NET Core API
             |
             v
       Serviços (Core)
             |
             v
  Processamento de notificações
             |
             v
       Worker Service
```

Essa abordagem permite estudar conceitos como:

- Processamento assíncrono
- Execução de tarefas em background
- Separação de responsabilidades
- Injeção de dependência
- Comunicação entre aplicações
- Organização de projetos em camadas

## Como executar o projeto

### Pré-requisitos

- .NET SDK compatível com os projetos
- Node.js e npm
- Visual Studio ou Visual Studio Code
- Configurações dos serviços externos, quando utilizados

### 1. Clonar o repositório

```bash
git clone https://github.com/murilofarina/processamento-assincrono.git
cd processamento-assincrono
```

### 2. Executar o backend

Abra a solução no Visual Studio:

```text
BackEnd/Infoeste2026_ProcessamentoAssincrono.sln
```

Configure os arquivos `appsettings.json` conforme os serviços utilizados e execute os projetos API e Worker.

Também é possível executá-los em terminais separados:

```bash
dotnet run --project BackEnd/API
```

```bash
dotnet run --project BackEnd/Worker
```

### 3. Executar o frontend

Acesse a pasta do frontend:

```bash
cd FrontEnd
```

Instale as dependências:

```bash
npm install
```

Inicie o servidor de desenvolvimento:

```bash
npm run dev
```

A aplicação poderá ser acessada pelo endereço local exibido no terminal do Vite.

> **Observação:** para a comunicação entre frontend e backend funcionar, verifique a URL da API utilizada pelo frontend, a configuração de CORS e as portas de execução dos serviços.

## Contexto acadêmico

Projeto desenvolvido a partir das atividades práticas realizadas durante a **Infoeste 2026**, como parte dos estudos de desenvolvimento de software e integração entre aplicações.

O repositório tem finalidade educacional, servindo como material de estudo e base para futuras melhorias e experimentações.

## Autor

**Murilo Farina**

- [GitHub](https://github.com/murilofarina)
- [LinkedIn](https://www.linkedin.com/in/murilofarina/)
