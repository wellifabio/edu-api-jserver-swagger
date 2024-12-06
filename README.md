<h1 align="center">AGROTECH</h1>

<p align="center">🚀 Projeto que utiliza o json-server para mockar uma REST API e Swagger para documentar, também cria um diretório para upload de imagem e utiliza autenticação JWT</p><br>

## Tecnologias

- [VSCode](https://code.visualstudio.com/)
- [Node](https://nodejs.org/en)
- [Git](https://git-scm.com)
- [json-server Authentication ](https://www.npmjs.com/package/json-server-auth)
- [Swagger](https://swagger.io/)

### Descrição
Este projeto utiliza como base o json-server, simulando uma fake API para ser utilizada como base para projetos de estudo WEB e Mobile

### Pré-requisitos e Como utilizar
Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas:
[Git](https://git-scm.com), [Node.js](https://nodejs.org/en/). 
Além disto é bom ter um editor para trabalhar com o código como [VSCode](https://code.visualstudio.com/)

### 👨🏽‍💻 Rodando o Back End (servidor)
#### Clone este repositório, abra com VsCode e em um terminal **bash** ou **cmd**

```bash
# Instale as dependências
$ npm install

# Execute a aplicação 
$ npm start
# O servidor inciará na porta:4000 - acesse <http://localhost:4000/swagger> para ver a documentação
```
- A API possui autenticação JWT, para acessar os endpoints protegidos é necessário passar o token no header da requisição
- Basta criar um usuário na rota /users e fazer login na rota /login para obter o token
- Exemplo de dados para a criação de um usuário:
```json
{
    "nome": "Marcos",
    "email": "marcos@gmailcom",
    "password": "senha123",
    "cpf":"701.511.906-40"
}
```
- Mais instruções sobre a utilização através do SWAGGER
![Swagger](./swagger.png)

## Instruções para implantação em Rede Local
- 1 alterar "localhost" para o IP local e porta no caminho da linha 10 no arquivo swagger.json
```json
    "url": "http://localhost:4000",
```

- 2 Para dispensar a autenticação JWT comentar as linhas a seguir do arquivo server.js
```js
const rules = auth.rewriter({
    "/users*": "/660/users$1",
    "/cursos*": "/660/cursos$1",
    "/matriculas*": "/660/matriculas$1",
    "/atividades*": "/660/atividades$1",
    "/entregas*": "/660/entregas$1"
});
```
```js
const rules = auth.rewriter({
    // "/users*": "/660/users$1",
    // "/cursos*": "/660/cursos$1",
    // "/matriculas*": "/660/matriculas$1",
    // "/atividades*": "/660/atividades$1",
    // "/entregas*": "/660/entregas$1"
});
```
- 3 Executar com os comandos
```bash
npm install
npx nodemon
```
