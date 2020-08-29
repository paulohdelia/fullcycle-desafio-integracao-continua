# Integração contínua e boas práticas com Github

<p>
  <a href="https://www.linkedin.com/in/paulodelia/">
      <img alt="Paulo D'Elia" src="https://img.shields.io/badge/-paulodelia-important?style=flat&logo=Linkedin&logoColor=white" />
   </a>
  <a href="https://github.com/paulohdelia/fullcycle-desafio-integracao-continua/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/paulohdelia/fullcycle-desafio-integracao-continua?color=important">
  </a> 
  <img src="https://img.shields.io/github/languages/count/paulohdelia/fullcycle-desafio-integracao-continua?color=important&style=flat-square">
</p>

Este é o último desafio da semana Full Cycle em que o objetivo é usar o Github Actions para configurar uma pipeline de CI, além de também configurar as regras de branch para não ser aceito pushs direto na master.

## :book: O que aprendi?

Com o GitHub Actions criei uma pipeline que instala todas as depêndencias e depois roda os testes automatizados que vem com o Nest.js

```yml
- name: Install dependencies
  run: npm install

- name: unit tests
  run: npm run test

- name: e2e tests
  run: npm run test:e2e
  
- name: test coverage
  run: npm run test:cov
```

Com os testes funcionando, eu criei uma nova regra para as branchs.

Regras que usei:
  * Não pode commitar direto na master
  * Exigir que todo pull-request passe nos testes definidos com o Github Actions
  * Os administradores também estão sujeitos aos testes


