# O projeto "node-react-chatgpt-clone" no GitHub é um clone fullstack do ChatGPT, utilizando uma integração com o algoritmo do OpenAI. Ele é dividido em duas partes principais: o **Back-end** e o **Front-end**.

### **Back-End**:
- **Tecnologias usadas**: Node.js, Express, JavaScript, CORS.
- O servidor recebe as requisições do front-end, faz a comunicação com a API do OpenAI para obter as respostas do ChatGPT e retorna essas respostas para o cliente.

### **Front-End**:
- **Tecnologias usadas**: React, JavaScript.
- A interface do usuário é construída com React, onde o usuário pode interagir com o ChatGPT, enviando perguntas e recebendo respostas.

### **Execução**:
- **Back-End**: Navegar até a pasta `server`, instalar as dependências com `npm install`, e iniciar o servidor com `npm start` (funciona na porta 5000).
- **Front-End**: Navegar até a pasta `web`, instalar as dependências com `npm install`, e iniciar o servidor com `npm start`.

O objetivo deste projeto é criar uma interface simples e funcional para interagir com a inteligência artificial do ChatGPT, utilizando uma arquitetura fullstack.

Para continuar a explicação detalhada do projeto **node-react-chatgpt-clone**, organizaremos as informações em um formato de arquivo `README.md`, adequado para iniciantes em desenvolvimento **Fullstack**.

---

# 📌 Node-React ChatGPT Clone

## 📖 Sobre o Projeto
Este projeto é um clone simplificado do ChatGPT, criado com **Node.js** e **React**, que permite aos usuários interagir com a API do OpenAI. Ele implementa uma **arquitetura fullstack**, onde o **Back-end** gerencia as requisições para a API, e o **Front-end** fornece uma interface amigável para o usuário.

---

## 🚀 Tecnologias Utilizadas

### **Back-End (Server)**
- **Node.js**: Ambiente de execução JavaScript no servidor.
- **Express.js**: Framework para gerenciar as rotas e requisições HTTP.
- **Dotenv**: Gerenciamento de variáveis de ambiente (ex.: chave da API OpenAI).
- **CORS**: Permite a comunicação entre o front-end e o back-end.

### **Front-End (Web)**
- **React.js**: Biblioteca JavaScript para criar interfaces interativas.
- **Axios**: Cliente HTTP para fazer requisições ao servidor.
- **CSS**: Para estilização da interface.

---

## 📂 Estrutura do Projeto

```
node-react-chatgpt-clone/
│── server/            # Código do Back-end (Node.js)
│   ├── index.js       # Configuração do servidor Express
│   ├── .env           # Variáveis de ambiente (API Key)
│   ├── package.json   # Dependências do Node.js
│── web/               # Código do Front-end (React.js)
│   ├── src/
│   │   ├── App.js     # Componente principal do React
│   │   ├── api.js     # Comunicação com o servidor
│   │   ├── index.css  # Estilização
│   ├── package.json   # Dependências do React.js
```

---

## 🖥️ Configuração e Execução

### 🔹 **1. Configurando o Back-End**
1. Acesse a pasta `server`:
   ```sh
   cd server
   ```
2. Instale as dependências:
   ```sh
   npm install
   ```
3. Configure a API Key do OpenAI no arquivo `.env`:
   ```env
   OPENAI_API_KEY=SUA_CHAVE_AQUI
   ```
4. Inicie o servidor:
   ```sh
   npm start
   ```
   - O servidor será iniciado na porta **5000**.

### 🔹 **2. Configurando o Front-End**
1. Acesse a pasta `web`:
   ```sh
   cd web
   ```
2. Instale as dependências:
   ```sh
   npm install
   ```
3. Inicie o front-end:
   ```sh
   npm start
   ```
   - O aplicativo estará disponível em **http://localhost:3000**.

---

## ⚙️ Funcionamento do Código

### **📌 Back-End (Node.js + Express)**
- O `index.js` configura um **servidor Express** que recebe requisições `POST` do front-end.
- Ele envia a mensagem do usuário para a **API do OpenAI** e retorna a resposta gerada pelo modelo.
- O **CORS** é ativado para permitir requisições do React.

#### 🔍 **Exemplo de Rota no Back-End**
```js
app.post("/chat", async (req, res) => {
    const { message } = req.body;

    const response = await openai.createCompletion({
        model: "text-davinci-003",
        prompt: message,
        max_tokens: 100
    });

    res.json({ response: response.data.choices[0].text });
});
```

### **📌 Front-End (React.js)**
- O `App.js` contém um campo de entrada onde o usuário digita a mensagem.
- O `api.js` gerencia as requisições ao servidor usando **Axios**.
- A resposta do ChatGPT é exibida dinamicamente na tela.

#### 🔍 **Exemplo de Chamada da API no Front-End**
```js
const sendMessage = async (message) => {
    const response = await axios.post("http://localhost:5000/chat", { message });
    setChatHistory([...chatHistory, { user: message, bot: response.data.response }]);
};
```

---

## 🎯 Objetivos do Projeto
✅ Demonstrar o uso de **Node.js** e **React** para criar uma aplicação fullstack.  
✅ Ensinar como **consumir APIs externas** (como a OpenAI API).  
✅ Criar um **chat interativo** usando **React** e **Express**.  
✅ Mostrar como organizar um projeto **cliente-servidor**.  

---

## 📌 Conclusão
Este projeto é uma ótima introdução para desenvolvedores **Fullstack**, combinando **Back-end (Node.js)** e **Front-end (React.js)** para construir um chat com **OpenAI API**. Ele pode ser expandido com autenticação, banco de dados e mais funcionalidades!

---

Caso tenha dúvidas, consulte a [documentação oficial do OpenAI](https://beta.openai.com/docs/) e explore mais sobre **React** e **Node.js**. 🚀

