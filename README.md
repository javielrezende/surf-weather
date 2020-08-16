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

* C01P02
- yarn add -D @typescript-eslint/eslint-plugin eslint @typescript-eslint/parser
Usa-se eslint porque ts lint foi depreciado.
Colocado dois comandos de lint no scritp, pois o que nao contem fix, é utilizado para ci/cd.

* C01P03
- yarn add -D ts-node-dev
Sem o ts-node quando startamos o servidor o node compila o codigo para js e roda em cima desses arquivos compilados, 
dentro da pasta dist. Com o ts-node o node roda em cima dos arquivos ts. Muito mais rapido para subir o servidor
para desenvolvimento. E neste pacote especifico para dev o watch ja eh integrado.

* C01P04
- yarn add -D jest ts-jest @types/jest
- yarn add -D supertest @types/supertest
RunInBand colocado dentro do script de rodar o teste serve para rodar o teste em ordem, sem isso o jest roda o teste em paralelo.
Bom para ser configurado assim para testes que manipulam o banco de dados, podendo um teste inflluenciar no outro. Testes de unidade
isso não é necessario.

* C01P05
- yarn add express body-parser @overnightjs/core
- yarn add -D @types/express
No teste e no setup do jest inserimos um elemento global para o ts. ->global.testRequest - O lint fica reclamando e com razao, o ts nao tem esse tipo global. Para isso precisamos usar um tipo ja existente do global e compor com esse tipo, informando a existencia dele. Para fazer isso
sobrescrevemos algumas coisas que ficaram no arquivo globals.d.ts, dentro da pasta teste. Os imports precisam ser inline para o arquivo ser
tratado como global. Se os imports ficarem como nos demais arquivos, ou seja, nas primeiras linhas do arquivo, o arquivo globals será
visto como um arquivo local, e nao global, por isso os imports inline.