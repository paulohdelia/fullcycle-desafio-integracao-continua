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

![](http://drive.google.com/uc?export=view&id=15KfRKD7DcnO0Pz_bz3G4z0uT4t0uF8D0)

Configurações mostradas no GIF
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

Após ter finalizado a configuração de CI, parti para criar uma nova regra para as branchs

Regras que usei:
  * Não pode commitar direto na master
  * Exigir que todo pull-request passe nos testes definidos com o Github Actions
  * Os administradores também estão sujeitos aos testes

![](http://drive.google.com/uc?export=view&id=1ouqQHTCq8JrG0dbh7VEQxIUALdB5_BXi)

Com as regras de branch criada e a CI feita com o Github Actions, o repositório já está pronto e devidamente configurado

Para testar, criei um arquivo novo em uma branch chamada **dev** e fiz pull-request. Como esperado, o pull-request precisou passar primeiro pelos testes para então ser liberado para fazer o merge na master

![](http://drive.google.com/uc?export=view&id=1ZMlN8AkAtNEQVkw_PWAXR-NDKGwS0sNL)

E por último testei a regra de não permitir pushs direto para master. 

Primeiro criei um arquivo novo na master, fiz o commit e tentei dar o push. Logo de cara apareceu uma mensagem de erro dizendo que a branch master é uma branch protegida. Então todas as configurações funcionaram!

![](http://drive.google.com/uc?export=view&id=1lvlPnQgYNolupxbF3V5cTWzxpOdEFZUP)
