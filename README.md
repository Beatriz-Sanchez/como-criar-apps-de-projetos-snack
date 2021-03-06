# Como criar um app usando seu projeto Expo Snack
<br>

1. baixar e descompactar os arquivos do projeto
2. abrir para testar se está funcionando e instalar qualquer pacote que ficou faltando:
  - entrar na pasta do seu projeto pelo terminal e executar `expo install .`, para instalar todas as dependencias que seu projeto precisa
  - executar `expo start`
  <br>*** se tiver dificuldades com estes comandos, verifique a opção alternativa ao fim do texto
  - abrir o app para testar (para abrir no celular, use o qrCode mostrado na tela ou conecte o celular ao computador com um cabo USB e digite `a`; para abrir na web, digite `w`)
  - aperte **ctrl+c** (ou **command+c**) para parar o servidor
3. alterar o arquivo `app.json` para atualizar o nome do app e do pacote, assim:
  
  ```json
  "ios": {
    "bundleIdentifier": "com.suaempresa.nomedoapp",
    "buildNumber": "1.0.0"
  },
  "android": {
     "package": "com.suaempresa.nomedoapp",
     "versionCode": 1
  }
  ```
  
4. usar o comando `expo build:android` ou `expo build:ios` para criar arquivos apk e ipk
  <br>***Para fazer um build de app iOS é preciso de uma conta de desenvolvedor, que é paga
5. se houverem escolhas a serem feitas, escolher a primeira opção em todas
6. Vai demorar. Será gerada uma url para você acompanhar seu processo de build, você pode entrar nela para checar quando está pronto, ou só olhar seu terminal de vez em quando
7. quando estiver pronto, aparecerá um link no terminal (ou um botão de download no site da expo). Se o link do terminal for colado no navegador, seu apk/api será carregado. 
<br>

Você pode mandar abrir este mesmo link no celular executá-lo para instalar seu app

## Opção alternativa

- Se der erro ao tentar executar o passo **2**, você pode tentar usar o ***yarn*** como alternativa:
  - instale o yarn com `npm install -g yarn` e use o comando `yarn add expo`, e então `expo start`
  <br>*** Se você já tiver instalado o yarn antes, é só usar o comando `yarn add expo`, e então `expo start`
  - o resto dos passos podem ser executados igualmente
