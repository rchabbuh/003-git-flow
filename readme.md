# GIT / GIT HUB
# O flow completo de operação / The complete operational flow

⚙️ PT - O processo completo para que possamos entender como funciona o GIT e o GIThub em conjunto trabalhando em equipe

⚙️ EN - The complete process so that we can understand how GIT and GIThub work together as a team.

## Fluxo 1: O Caminho "Do Zero Local para a Nuvem"
Cenário: Você criou uma pasta no seu computador, escreveu códigos e agora decidiu que isso precisa ir para o GitHub. O repositório remoto ainda não existe.

### Passo 1: Preparar o Terreno Local (No seu PC)
Navegue até a pasta pelo bash. Inicie o Git, (Cria a pasta oculta .git)
git init
Renomeie a branch principal (Padrão Moderno): O Git antigo chama a branch principal de master. O GitHub e o mercado usam main. Vamos padronizar agora para evitar problemas futuros:
git branch -M main
Adicione seus arquivos à "Caixa de Envio" (Staging):
git add .
Feche o pacote (Commit):
git commit -m "Primeiro commit: Estrutura inicial do projeto"
Neste momento, seu código está salvo e versionado, mas apenas no seu computador.
Você pode parar por ai e versionar apenas na sua máquina se preferir.

### Passo 2: Criar a "Garagem" na Nuvem (No Site do GitHub) - Agora precisamos criar o destino.
Vá no site github.com e faça login.
Clique no botão New (ou no sinal de + no canto superior direito -> New repository).
Dê um nome ao repositório (ex: meu-projeto-estudos). Ideal que seja igual a pasta para sua identificação rapida
IMPORTANTE: Deixe as opções "Add a README file", ".gitignore" e "License" DESMARCADAS.
Por que? Se você marcar isso, o GitHub cria um histórico lá. Como você já tem um histórico no seu PC, tentar juntar os dois agora daria conflito. Queremos o repositório vazio.
Clique em Create repository.

### Passo 3: Conectar e Enviar (O Link) - O GitHub vai te mostrar uma tela cheia de códigos. Procure a seção "…or push an existing repository from the command line".
Crie a ponte (Remote): Copie e cole o comando que o GitHub te deu (parecido com este):
git remote add origin https://github.com/SEU-USUARIO/NOME-DO-REPO.git
Explicação: Você está dizendo ao Git local: "Adicione um endereço remoto chamado 'origin' que aponta para essa URL".
Envie os arquivos (Push):
git push -u origin main
O -u cria um vínculo permanente. Da próxima vez, basta digitar git push.
Pode ser que o Git peça seu usuário e senha (ou token) nesta etapa.

## Fluxo 2: O Caminho "Da Nuvem para o Local" (Clonar)
Cenário: O projeto já existe no GitHub (pode ser um projeto open source ou um repositório que você criou em outro computador) e você quer trazê-lo para sua máquina para trabalhar.

### Passo 1: Trazer o Projeto (Download Inteligente)
Abra o terminal na pasta onde você quer que o projeto seja salvo (ex: cd Desktop).
No site do GitHub, na página do projeto, clique no botão verde <> Code
Copie a URL (HTTPS)
No terminal, digite:
git clone https://github.com/USUARIO/NOME-DO-REPO.git
O Git vai criar uma pasta com o nome do repositório e baixar tudo dentro dela. A conexão remota (origin) já vem configurada automaticamente!

### Passo 2: Entrar no Escritório (Crucial!)
Entre na pasta que acabou de ser criada: Muitos iniciantes esquecem este passo e dão comandos na pasta errada.
cd nome-do-repo

### Passo 3: O Ciclo de Trabalho (Editar e Enviar)
Agora que está conectado, o fluxo é cíclico:
Trabalhe: Crie arquivos, edite códigos no VS Code.
Verifique:
git status
Prepare:
git add .
Salve Localmente:
git commit -m "Adicionada funcionalidade de login"
Envie para a Nuvem: Como você clonou, o Git já sabe para onde enviar.
git push
Receba Atualizações (Opcional, mas recomendado): Se você trabalha em equipe ou em dois computadores, sempre antes de começar a trabalhar, garanta que seu local está atualizado com o que está na nuvem:
git pull

## Fluxo Chabbuh - Melhor prática de projetos novos e estrutura

Passo 1: Criar o destino.
Vá no site github.com e faça login.
Clique no botão New (ou no sinal de + no canto superior direito -> New repository).
Dê um nome ao repositório (ex: meu-projeto-estudos). Ideal que seja igual a pasta para sua identificação rapida
IMPORTANTE: Deixe as opções "Add a README file", ".gitignore" e "License" DESMARCADAS.
Por que? Se você marcar isso, o GitHub cria um histórico lá. Como você já tem um histórico no seu PC, tentar juntar os dois agora daria conflito. Queremos o repositório vazio.
Clique em Create repository.
Quando você cria o repositório diretamente no GitHub, ele já vem com: ✔ estrutura limpa / ✔ branch main criada / ✔ repositório remoto configurado / ✔ painel de commits e configurações prontos
Isso evita erros comuns como: origin errado / conflitos com main / ter que configurar remoto na mão / repositório local divergente do remoto

Passo 2: Conectar com o reposotório local
Navegue pelo bash até o repositório que você ira criar tudo e confira o local
Resultado > C:\Users\Reinaldo\Desktop\meu-projeto\
pwd
Depois clone o repo
git clone https://github.com/usuario/repo.git
O Git automaticamente: ✔ cria uma pasta local / ✔ já vem com o diretório .git configurado / ✔ já define o remoto origin / ✔ já coloca você na branch main / ✔ já conecta sua máquina com o GitHub corretamente

Passo 3: preparar o terreno para iniciar o desenvolvimento
Entrar na pasta clonada
cd meu-projeto
Criar sua branch de desenvolvimento
git checkout -b dev

Passo 4: O Ciclo de Trabalho (Editar e Enviar)
Agora que está conectado, o fluxo é cíclico:
Trabalhe: Crie arquivos, edite códigos no VS Code.
Verifique:
git status
Prepare:
git add .
Salve Localmente:
git commit -m "Adicionada funcionalidade de login"
Envie para a Nuvem: Como você clonou, o Git já sabe para onde enviar.
git push
Receba Atualizações (Opcional, mas recomendado): Se você trabalha em equipe ou em dois computadores, sempre antes de começar a trabalhar, garanta que seu local está atualizado com o que está na nuvem:
git pull




