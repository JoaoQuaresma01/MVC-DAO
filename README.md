# Projeto Java MVC com DAO e SQL Server no NetBeans

Este projeto é uma aplicação Java com arquitetura MVC e DAO que se conecta a um banco de dados SQL Server utilizando autenticação da Microsoft (Windows Authentication).

##  Estrutura do Projeto

- **MVC (Model-View-Controller)**:
  - `Model`: Classes que representam os dados e a lógica de negócio.
  - `View`: Interface com o usuário (pode ser via console ou GUI, como Swing/JavaFX).
  - `Controller`: Faz a ponte entre a View e o Model.

- **DAO (Data Access Object)**:
  - Camada responsável por fazer as operações com o banco de dados (SELECT, INSERT, UPDATE, DELETE).

## 🛠 Requisitos

- [NetBeans IDE](https://netbeans.apache.org/) (recomendado 15+)
- [JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) (versão 11 ou superior)
- [SQL Server](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads) instalado e em execução
- [Driver JDBC para SQL Server](https://learn.microsoft.com/pt-br/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server) (`mssql-jdbc`)
- Conta do Windows com permissão para acessar o SQL Server (Windows Authentication)

##  Conectando ao SQL Server com Autenticação Microsoft

Certifique-se de que o banco está configurado para **"Windows Authentication"** (Autenticação do Windows) e o usuário atual tem permissão de acesso.

### Exemplo de string de conexão:
```java
String url = "jdbc:sqlserver://localhost:1433;databaseName=NomeDoBanco;integratedSecurity=true;";
```
Importante:
O integratedSecurity=true é o que ativa a autenticação via Windows.

O driver JDBC precisa do arquivo sqljdbc_auth.dll que deve estar:

No caminho do sistema (C:/Windows/System32)

Ou adicionado como parâmetro de VM no NetBeans:

-Djava.library.path="caminho/do/sqljdbc_auth.dll"

▶ Executando o Projeto
Certifique-se de que o SQL Server está em execução

Execute o projeto no NetBeans (F6 ou botão verde "Run")

A aplicação irá se conectar automaticamente ao banco usando a autenticação do Windows

