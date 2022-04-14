# Módulo 3 v1

### Aula 62 - Aula de Revisão: Publicação do App e Configuração do Ambiente Local

##### Introdução - 5min

- Na aula passada:

  - Resolvemos os seguintes bugs:
    - mestre com nomes de times repetidos
    - horário do computador/celular
    - inativação do botão

- Questões:

  - Como resolvemos o erro em que o nome da equipe aparece repetidamente no app mestre quando o botão é pressionado várias vezes? -> Esvaziando a matriz `teams`

  - A função ``getTime()`` pode ser substituída por... -> `firebase.database.ServerValue.TIMESTAMP`
  
  ***traduziram server value 🤦‍♀️

##### Atividade da professora - configurar ambiente local  - 10 min

*** na verdade o aluno faz esta também

- Primeiro construiremos um app simples de previsão do tempo que obtém dados de clima e temperatura de uma API de clima e os exibe em uma tela inicial. 
  - Você lembra o que é uma API? -> um serviço que nos fornece alguns dados com base em nossa consulta.
  - Usamos ``fetch()`` para obter dados da API em Javascript
- pedir para o aluno abrir um projeto snack do zero
- Primeiro, escreveremos uma função ``getWeather()`` (obter clima) que obterá os dados json da API.

```react
//escrever função assíncrona getWeather()
```

- Agora precisamos mostrar os dados na interface. Na função render, vamos usar um if-else para retornar a mensagem de carregamento ou mostrar a previsão
  - também podemos colocar uma imagem de nuvem para melhor a aparência da interface

```react
//fazer um if-else no render (carregando-resultado)
```

- testar

- Bom trabalho. Agora vamos escrever o código em nossa máquina local. Para isso, precisamos instalar o expo e o node.js.

  - Estaremos seguindo as instruções fornecidas na documentação do Expo em seu site para primeiro instalar o Expo em nossa máquina local: [Installation - Expo Documentation](https://docs.expo.dev/get-started/installation/)

  - passos simples:

    - instalar node.js

    - instalar o expo: `npm install --global expo-cli`

    - criar o primeiro projeto: `expo init weather app`

      ***escolher um template em branco se for pedido: `expo-template-blank`

    - ir até o projeto: `cd weather app`

***Para facilitar na lição de casa, instalar também o yarn, com `npm install -g yarn`

*** Para usuários mac:  

1. instalar o Homebrew com: `sudo /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.c om/Homebrew/install/master/in stall.sh)` 
2. instalar o Node.js com: `sudo brew install node`
3. verificar a instalação com: `node --version.`
4. instalar expo com: `sudo npm install expo-cli --global`
5. seguir resto do processo normalmente

***Para usuários Ubuntu: 

1. instalar o Node.js com: `sudo apt install node`
2. verificar a instalação com: `node --version.` 
3. instalar expo com: `sudo npm install expo-cli --global`
4. seguir resto do processo normalmente

- agora que a pasta do projeto está pronta, vamos abri-la no editor

- vamos escrever o código para o nosso app de clima dentro dela (podemos copiar do snack)

- Agora, vamos testar o resultado. Abra seu terminal novamente:

  - ir até o projeto: `cd weather app`

  - rodar o expo: `expo start` 
  - usar o qr code dado nesse momento para abrir o projeto no celular. Pode demorar um pouco da primeira vez (o computador e o celular têm que estar conectados à mesma rede para funcionar)

##### Atividade do Aluno - gerar arquivo publicável - 20 minutos

- Agora vamos aprender a construir um arquivo publicável (.apk ou .ipk). 
- Antes de construir o apk ou ipa, precisamos adicionar um identificador exclusivo para a Playstore e a Appstore lembrarem do nosso aplicativo. 
  - Isso é feito usando um nome de domínio da web reverso dentro do arquivo app.json — uma vez que o domínio da web de cada usuário será diferente e único. Você pode usar qualquer nome de domínio fictício por enquanto.
- no arquivo, escrever usando o modelo abaixo:

```json
{
   "expo": {
    "name": "Your App Name",
    "icon": "./path/to/your/app-icon.png",
    "version": "1.0.0",
    "slug": "your-app-slug",
       //importantes:
       
    "ios": {
      "bundleIdentifier": "com.yourcompany.yourappname",
      "buildNumber": "1.0.0"
    },
    "android": {
      "package": "com.yourcompany.yourappname",
      "versionCode": 1
    }
   }
 }
```

***Cuidado pra não esquecer as vírgulas

- Pressiona Ctrl + C no mesmo terminal em que você executou o expo start, isso para o Metro Bundler
- na mesma pasta, execute: `sudo expo build: android` para ter um apk ou `sudo expo build:ios` para ter um ipk
  - se houver um erro “"unable to resolve react-native-gesture handler”, executar `npm install react-native-gesture-handler` e executar o comando de build novamente

*** para fazer um ipk, é preciso ter uma conta de desenvolvedor paga, com ID apple e senha em mãos. Também precisa de um icone que não seja transparente

***O Expo constrói o apk em uma máquina de servidor compartilhado. O build irá falhar se uma das máquinas servidor da Expo não estiver disponível para fazer o build

***o expo build android vai parar de funcionar em janeiro/2023. Após isso, instalar eas (`npm install -g eas-cli`) e fazer o build com `eas build -p android`

- O comando build demora um pouco. Você pode visitar o link do build fornecido no terminal para ver o progresso. Assim que o build estiver concluído, você pode baixar o apk diretamente de lá.

- Depois de algum tempo, você pode ver o link do arquivo apk. Você pode clicar nele para fazer o download e instalá-lo.

##### Fechamento - 5 min

- Revisão:
  - configuramos o ambiente local
  - aprendemos a criar arquivos apk ou ipk
- Questões:
  - Qual função é usada para obter os dados JSON da API? -> `fetch()`
  - Todas as bibliotecas que usamos no snack vêm como pacotes Node chamados de? -> `npm`
  - Qual dos seguintes comandos é usado para executar o projeto no Expo? -> `expo start`

##### Projeto - PUBLICAÇÃO DO APP E CONFIGURAÇÃO DO AMBIENTE LOCAL

- publicar outro app

- Tarefas específicas:
  - baixar e descompactar os arquivos do projeto
  - entrar na pasta do seu projeto pelo terminal Node.js e executar o `expo start`
  
  ***Se der erro, instalar o yarn (com `npm install -g yarn`) e usar o comando `yarn add expo`
  
  - alterar o arquivo `app.json` para atualizar o nome do app e do pacote, assim:
  
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
  
  - usar o comando `expo build:android` ou `expo build:ios` para criar arquivos apk e ipk
  
  ***Para fazer um build de app iOS é preciso de uma conta de desenvolvedor, que é paga
  
  - se houverem escolhas a serem feitas, escolher a primeira opção em todas
  - Vai demorar. Será gerada uma url para você acompanhar seu processo de build, você pode entrar nela para checar quando está pronto, ou só olhar seu terminal de vez em quando
  - quando estiver pronto, aparecerá um link no terminal (ou um botão de download no site da expo). Se o link do terminal for colado no navegador, seu apk/api será carregado. 
  - Você pode mandar abrir este mesmo link no celular executá-lo para instalar seu app