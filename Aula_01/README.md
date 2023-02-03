![Class Image](https://gitlab.com/LeonardoRaiz/aulas-script/-/raw/main/Variados/Aula.png)

[![Node.js CI](https://github.com/LeonardoRaiz/aulas-script/actions/workflows/node.js.yml/badge.svg)](https://github.com/LeonardoRaiz/aulas-script/actions/workflows/node.js.yml)

![gitLab](https://gitlab.com/LeonardoRaiz/aulas-script/badges/main/pipeline.svg)


# Primeira API

---

Utilizando o primeiro recurso do NODE.JS 

## Inicializando o pacote JSON (package.json)

O que é e para que serve npm?

O npm **é uma ferramenta de linha de comando que ajuda a interagir com plataformas online, como navegadores e servidores**. Essa utilidade auxilia na instalação e desinstalação de pacotes, gerenciamento da versões e gerenciamento de dependências necessárias para executar um projeto.

```bash
npm init -y
```

Com este código bash será gerado um arquivo chamado package.json e nele haverá o seguinte código:

 

```json
{
  "name": "aula-01",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

## Criando a dependência do servidor

Express **é o framework Node mais popular e a biblioteca subjacente para uma série de outros frameworks do Node**. O Express oferece soluções para: Gerenciar requisições de diferentes verbos HTTP em diferentes URLs. Integrar "view engines" para inserir dados nos templates.

```bash
npm i express
```

Através da instalação da dependência express, será gerado uma pasta chamada node_modules, um arquivo package-lock.json e uma atualização do arquivo package.json.

```json
{
  "name": "aula-01",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^4.18.2"
  }
}
```

Após criar as dependências agora é a hora de criar nosso arquivo principal index.js 

```jsx
//Criar a biblioteca express
const express = require("express");

//armazenar na váriavel app as funções da biblioteca express
const app = express();

//chamar a função listen para "escutar a porta em que vamos utilizar"
app.listen(8080);
```

Parabéns!!! Você acabou de criar seu primeiro servidor **😍**

## Criando as rotas

Para fazer um teste de “verdade”, vamos desenvolver um caminha de acesso do servidor. Chamamos este caminho de rota.

Uma rota em uma API **é um “caminho” que será “chamado” por uma aplicação ou cliente e responderá alguma informação**. Cada rota pode ter uma ou mais funções, e ela deve ser única na API, ao receber uma chamada ela faz todo o processamento necessário para retornar os dados que foi solicitado.

Será adicionado no arquivo index.js o seguinte codigo:

```jsx
//Criando um rota de teste

app.get('/teste', () => {
    console.log('Nosso servidor está ativo na porta 8080');
})
```
Existe também criar na arrow function requisições e respostas para o acesso à rota, como:

 

```jsx
//Criando uma rota de teste com HTML
app.get("/testeComHTML", (req, res) => {
  res.send("<h1>Server ativo</h1>");
});
```