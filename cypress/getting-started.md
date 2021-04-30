## Getting Started with Cypress

1 - Cria um novo diretório na raiz do projeto

2 - Dentro do diretório rode o comando:

```npm init -y```

3 - Instale o Cypress

```npm install cypres```

4 - Execute o seguinte comando:

```npx cypress open```

5 - Escreva seus testes dentro de cypress > integration. Nomeie o arquivo com a extensão `.spec.js`

6 - Na primeira linha do arquivo insira:

`/// <reference types="cypress" />`

Isso vai fazer com que o VS Code instale um autocomplete para ajudar na escrita.

7 - Comece a escrever seus testes!

Obs: se quiser evitar rodar os testes toda vez que um arquivo for salvo, escreva no arquivo `cypress.json`:

```json
{
  "watchForFilesChanges": false
}
```