# Boilerplate MVC em Node.js com PostgreSQL

Este projeto é um boilerplate básico para uma aplicação Node.js seguindo o padrão MVC (Model-View-Controller), utilizando PostgreSQL como banco de dados.

## Requisitos

- Node.js (versão X.X.X)
- PostgreSQL (versão X.X.X)

## Instalação

1. **Clonar o repositório:**

```bash
   git clone https://github.com/seu-usuario/seu-projeto.git
   cd seu-projeto
```

2. **Instalar as dependências:**
    
```bash
npm install
```
    
3. **Configurar o arquivo `.env`:**
    
Renomeie o arquivo `.env.example` para `.env` e configure as variáveis de ambiente necessárias, como as configurações do banco de dados PostgreSQL.
    

Configuração do Banco de Dados
------------------------------

1. **Criar banco de dados:**
    
    Crie um banco de dados PostgreSQL com o nome especificado no seu arquivo `.env`.
    
2. **Executar o script SQL de inicialização:**
    
```bash
npm run init-db
```
    
Isso criará a tabela `users` no seu banco de dados PostgreSQL com UUID como chave primária e inserirá alguns registros de exemplo.
    

Funcionalidades
---------------

* **Padrão MVC:** Estrutura organizada em Model, View e Controller.
* **PostgreSQL:** Banco de dados relacional utilizado para persistência dos dados.
* **UUID:** Utilização de UUID como chave primária na tabela `users`.
* **Scripts com `nodemon`:** Utilização do `nodemon` para reiniciar automaticamente o servidor após alterações no código.
* **Testes:** Inclui estrutura básica para testes automatizados.

Scripts Disponíveis
-------------------

* `npm start`: Inicia o servidor Node.js.
* `npm run dev`: Inicia o servidor com `nodemon`, reiniciando automaticamente após alterações no código.
* `npm run test`: Executa os testes automatizados.
* `npm run test:coverage`: Executa os testes e gera um relatório de cobertura de código.

Estrutura de Diretórios
-----------------------

* **`config/`**: Configurações do banco de dados e outras configurações do projeto.
* **`controllers/`**: Controladores da aplicação (lógica de negócio).
* **`models/`**: Modelos da aplicação (definições de dados e interações com o banco de dados).
* **`routes/`**: Rotas da aplicação.
* **`tests/`**: Testes automatizados.
* **`views/`**: Views da aplicação (se aplicável).

Contribuição
------------

Contribuições são bem-vindas! Sinta-se à vontade para abrir um issue ou enviar um pull request.

Licença
-------

Este projeto está licenciado sob a Licença MIT.

Este README.md fornece uma visão geral clara do boilerplate, incluindo instruções de instalação, configuração do banco de dados, funcionalidades principais, scripts disponíveis, estrutura de diretórios, como contribuir e informações de licença. Certifique-se de personalizar as seções com detalhes específicos do seu projeto conforme necessário.

## Explique com suas palavras o funcionamento do Models, Controller e fale sobre endpoints no projeto.

O Model é responsável pela lógica de dados da aplicação, representando as entidades do sistema como Alunos, Cursos, etc. Além de definir as estruturas dos dados e também ser o ponto de integração com o banco. O Controller recebe as requisições do usuário e chama os métodos dos Models para acessar ou alterar dados, retornando uma resposta para o cliente, que pode ser uma página (com View). E os endpoints são urls que representam recursos acessíveis na aplicação (como /alunos ou /professores) e são definidos em routes/ e são diretamentes associdos aos métodos do Controller.

## Perguntas para medir aprendizado (responder neste README)

### Explique com suas palavras o papel de cada camada da arquitetura MVC usada neste projeto. Como o Model, o Controller e a View interagem entre si?

Model representa os dados e suas lógicas. É onde definimos as entidades do sistema como alunos, professores e cursos e como elas se relacionam. View é a camada vista pelo usuário no navegador, utilizando os arquivos `.ejs` para gerar listas, tabelas e outras estruturas HTML para exibir as informações enviadas pelos controllers. E o Controller atua como intermediário entre Model e View, recebendo as requisições do usuário e buscando ou alterando dados através do Model, e depois escolhe qual informação será exibida.


### Como ocorre o envio e o recebimento de dados no formato JSON neste projeto? Cite uma rota que responde em JSON e explique seu funcionamento.

Neste projeto, o envio e o recebimento de dados no formato JSON é viabilizado pelo middleware `express.json()` configurado no `server.js` como `app.use(express.json());`. Isso permite que o servidor Express interprete o corpo de requisições enviadas em JSON (como `POST`, `PUT`) e também envie respostas estruturadas no mesmo formato. Um exemplo de rota no projeto é `router.get('/users', userController.getAllUsers);`


### Qual a importância de usar HTML básico com formulários e tabelas para organizar e manipular dados no navegador? Por que esse tipo de estrutura ainda é útil em projetos back-end com Node.js?

HTML básico com formulários e tabelas continua sendo fundamental porque formulários permitem que o usuário envie dados para o servidor e tabelas organizam e exibem dados de forma clara e acessível. Esse tipo de estrutura ainda é útil pois funcionam como uma interface mínima funcional e de desenvolvimento simples. 

