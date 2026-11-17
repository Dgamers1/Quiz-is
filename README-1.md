# Quiz Battle — Inglês vs Português

Projeto de quiz multiplayer para dois celulares, hospedado no GitHub Pages e sincronizado pelo Firebase Realtime Database.

## O que está pronto
- Criar sala privada com código de 6 caracteres.
- Entrar na sala pelo segundo celular.
- Duas pessoas respondem à mesma pergunta em seus próprios aparelhos.
- **100 perguntas** (Tag Questions em Inglês + Crase em Português).
- **Tempo limite de 3 minutos por questão** (barra + contagem regressiva).
- Status claro: vê se o adversário já respondeu.
- Placar compartilhado e resultado final.
- Layout adaptado para celular.

## Segurança importante
⚠️ **As chaves do Firebase que estavam no código original foram removidas.**  
Nunca publique `apiKey`, `databaseURL` etc. em repositório público.  
Use sempre placeholders e configure localmente / via variáveis de ambiente se for evoluir o projeto.

## 1. Configurar o Firebase (gratuito para este uso inicial)
1. Acesse https://console.firebase.google.com/ e crie um projeto.
2. No projeto, adicione um aplicativo Web (`</>`).
3. Copie a configuração do Firebase.
4. Abra `index.html` e substitua os valores do objeto `firebaseConfig`:
   - `apiKey`
   - `authDomain`
   - `databaseURL`
   - `projectId`
   - `appId`
5. No Firebase, vá em **Authentication → Sign-in method** e ative **Anonymous**.
6. Vá em **Realtime Database → Create database**.
7. Na aba **Rules**, cole o conteúdo de `firebase-rules.json` e publique.

> Atenção: estas regras são permissivas para facilitar o primeiro teste entre amigos. Qualquer usuário autenticado que conheça um caminho de sala pode alterar os dados. Use apenas para uma brincadeira privada; antes de abrir publicamente, vale endurecer as regras e validar pontuação no servidor.

## 2. Publicar no GitHub Pages
1. Crie um repositório no GitHub, por exemplo `quiz-battle`.
2. Envie `index.html` para a raiz do repositório.
3. Envie também `firebase-rules.json` (só para referência; as regras são publicadas no console Firebase).
4. No GitHub, abra **Settings → Pages**.
5. Em **Build and deployment**, escolha **Deploy from a branch**.
6. Selecione `main` e `/ (root)`, depois **Save**.
7. Aguarde o link do Pages aparecer.

## 3. Jogar
1. Abra o link do GitHub Pages nos dois celulares.
2. Uma pessoa digita o nome e toca em **Criar sala**.
3. Envia o código de 6 caracteres ao amigo.
4. O amigo digita o nome, toca em **Entrar com código** e informa o código.
5. O anfitrião toca em **Começar partida**.
6. Cada questão tem **3 minutos**. Se o tempo acabar, a questão avança automaticamente (quem não respondeu não ganha ponto).

## Observações
- A configuração do Firebase é obrigatória; o site não conecta até preencher `firebaseConfig`.
- Os dois aparelhos precisam de internet.
- O anfitrião precisa permanecer conectado durante a partida.
- Esta é uma versão funcional para dois jogadores, sem cadastro.
- Total de questões: 100 (metade focada em Tag Questions, metade em Crase).
