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