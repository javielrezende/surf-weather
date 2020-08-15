* C01P01 01
- git init
- Configurado .gitignore
- Criado o projeto com npm init
- yarn add -D typescript
- yarn add -D @types/node 
- yarn add module-alias
- yarn add -D @types/module-alias
Para funcionar os paths que estão configurados no tsconfig, foi necessario instalar a dependencia module-alias e configurá-lo
no arquivo de config module-alias dentro de util.

* C02P02
- yarn add -D @typescript-eslint/eslint-plugin eslint @typescript-eslint/parser
Usa-se eslint porque ts lint foi depreciado.
Colocado dois comandos de lint no scritp, pois o que nao contem fix, é utilizado para ci/cd.

* C02P03
- yarn add -D ts-node-dev
Sem o ts-node quando startamos o servidor o node compila o codigo para js e roda em cima desses arquivos compilados, 
dentro da pasta dist. Com o ts-node o node roda em cima dos arquivos ts. Muito mais rapido para subir o servidor
para desenvolvimento. E neste pacote especifico para dev o watch ja eh integrado.

* C02P04
- yarn add -D jest ts-jest @types/jest
- yarn add -D supertest @types/supertest
RunInBand colocado dentro do script de rodar o teste serve para rodar o teste em ordem, sem isso o jest roda o teste em paralelo.
Bom para ser configurado assim para testes que manipulam o banco de dados, podendo um teste inflluenciar no outro. Testes de unidade
isso não é necessario.