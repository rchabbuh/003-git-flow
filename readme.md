# GIT / GIT HUB
# O Flow completo de operação  
# _The complete operational Flow_

⚙️ PT - O processo completo para que possamos entender como funciona o GIT e o GIThub em conjunto trabalhando em equipe.

⚙️ EN - The complete process so that we can understand how GIT and GIThub work together as a team.


## 🔹Fluxo 1: O Caminho "Do Zero Local para a Nuvem"🔹
## _🔹Flow 1: The Path "From Local Zero to the Cloud"🔹_

Cenário: Você criou uma pasta no seu computador, escreveu códigos e agora decidiu que isso precisa ir para o GitHub e o repositório remoto ainda não existe.

_Scenario: You created a folder on your computer, wrote code, and now you've decided it needs to go to GitHub, but the remote repository doesn't exist yet._

### ⚡Passo 1: Preparar o Terreno Local (No seu PC)
### _⚡Step 1: Prepare the Local Terrain (On your PC)_

1.1 Navegue até a pasta pelo bash.  
_1.1 Navigate to the folder using bash._

1.2 Inicie o Git, (Cria a pasta oculta .git)  
_1.2 Initialize Git (Creates the hidden .git folder)_

```python
git init
```

1.3 Renomeie a branch principal (Padrão Moderno): O Git antigo chama a branch principal de master. O GitHub e o mercado usam main. Vamos padronizar agora para evitar problemas futuros:  
_1.3 Rename the main branch (Modern Standard): Old Git calls the main branch master. GitHub and the market use main. Let's standardize now to avoid future problems:_

```python
git branch -M main
```

1.4 Adicione seus arquivos à "Caixa de Envio" (Staging):  
_1.4 Add your files to the "Submission Box" (Staging):_

```python
git add .
```

1.5 Feche o pacote (Commit):  
_1.5 Close the package (Commit):_

```python
git commit -m "Primeiro commit: Estrutura inicial do projeto"
```

1.6 Neste momento, seu código está salvo e versionado, mas apenas no seu computador.  
_1.6 At this point, your code is saved and versioned, but only on your computer._

Você pode parar por ai e versionar apenas na sua máquina se preferir.  
_You can stop there and version only on your machine if you prefer._

### ⚡Passo 2: Criar a "Garagem" na Nuvem (No Site do GitHub)
### _⚡Step 2: Create the "Garage" in the Cloud (On the GitHub Site)_

2.1 Agora precisamos criar o destino. Vá no site github.com e faça login.  
_2.1 Now we need to create the destination. Go to github.com and log in._

2.2 Clique no botão New (ou no sinal de + no canto superior direito -> New repository).  
_2.2 Click the New button (or the + sign in the upper right corner -> New repository)._

2.3 Dê um nome ao repositório (ex: meu-projeto-estudos). Ideal que seja igual a pasta para sua identificação rapida  
_2.3 Give the repository a name (e.g., my-project-studies). Ideally, it should be the same as the folder name for quick identification._

IMPORTANTE: Deixe as opções "Add a README file", ".gitignore" e "License" DESMARCADAS. Por que? Se você marcar isso, o GitHub cria um histórico lá. Como você já tem um histórico no seu PC, tentar juntar os dois agora daria conflito. Queremos o repositório vazio.  
_IMPORTANT: Leave the "Add a README file", ".gitignore", and "License" options UNCHECKED. Why? If you check this, GitHub creates a history there. Since you already have a history on your PC, trying to merge the two now would cause conflicts. We want an empty repository._

2.4 Clique em Create repository, e seu repositório estará criado!  
_2.4 Click Create repository, and your repository will be created!_

### ⚡Passo 3: Conectar e Enviar (O Link)
### _⚡Step 3: Connect and Send (The Link)_

3.1 O GitHub vai te mostrar uma tela cheia de códigos. Procure a seção "…or push an existing repository from the command line".  
_3.1 GitHub will show you a screen full of code. Look for the section "...or push an existing repository from the command line"._

3.2 Crie a ponte (Remote): Copie e cole o comando que o GitHub te deu (parecido com este substituindo SEU-USUARIO e NOME-DO-REPO):  
_3.2 Create the bridge (Remote): Copy and paste the command that GitHub gave you (similar to this, replacing YOUR-USERNAME and REPO-NAME):_

```Python
git remote add origin https://github.com/SEU-USUARIO/NOME-DO-REPO.git
```

Explicação: Você está dizendo ao Git local: "Adicione um endereço remoto chamado 'origin' que aponta para essa URL".  
_Explanation: You are telling the local Git: "Add a remote address called 'origin' that points to this URL."_

3.3 Envie os arquivos (Push):  
_3.3 Send the files (Push):_

```python
git push -u origin main
```

O -u cria um vínculo permanente. Da próxima vez, basta digitar git push. Pode ser que o Git peça seu usuário e senha (ou token) nesta etapa.  
_The -u creates a permanent link. Next time, just type git push. Git may ask for your username and password (or token) at this stage._

## 🔹Fluxo 2: O Caminho "Da Nuvem para o Local" (Clonar)🔹
## _🔹Flow 2: The Path "From the Cloud to the Local" (Clone)🔹_

Cenário: O projeto já existe no GitHub (pode ser um projeto open source ou um repositório que você criou em outro computador) e você quer trazê-lo para sua máquina para trabalhar.  
_Scenario: The project already exists on GitHub (it can be an open source project or a repository you created on another computer) and you want to bring it to your machine to work on it._

### ⚡Passo 1: Trazer o Projeto (Download Inteligente)
### _⚡Step 1: Bring the Project (Smart Download)_

1.1 Abra o terminal na pasta onde você quer que o projeto seja salvo (ex: cd Desktop).  
_1.1 Open the terminal in the folder where you want the project to be saved (e.g., cd Desktop)._

1.2 No site do GitHub, na página do projeto, clique no botão verde <> Code  
_1.2 On the GitHub site, on the project page, click the green <> Code button._

1.3 Copie a URL (HTTPS)  
_1.3 Copy the URL (HTTPS)_

1.4 No terminal, digite:  
_1.4 In the terminal, type:_

```python
git clone https://github.com/SEU-USUARIO/NOME-DO-REPO.git
```

O Git vai criar uma pasta com o nome do repositório e baixar tudo dentro dela. A conexão remota (origin) já vem configurada automaticamente!  
_Git will create a folder with the name of the repository and download everything inside it. The remote connection (origin) is already configured automatically!_

### ⚡Passo 2: Entrar no Escritório (Crucial!)
### _⚡Step 2: Enter the Office (Crucial!)_

2.1 Entre na pasta que acabou de ser criada: Muitos iniciantes esquecem este passo e dão comandos na pasta errada.  
_2.1 Enter the folder that was just created: Many beginners forget this step and give commands in the wrong folder._

```python
cd nome-do-repo
```

### ⚡Passo 3: O Ciclo de Trabalho (Editar e Enviar)
### _⚡Step 3: The Work Cycle (Edit and Send)_

Agora que está conectado, o fluxo é cíclico. Trabalhe: Crie arquivos, edite códigos no VS Code.
__Now that you're connected, the flow is cyclical. Work: Create files, edit code in VS Code._

3.1 Verifique:  
_3.1 Check:_

```python
git status
```

3.2 Prepare:  
_3.2 Prepare:_

```python
git add .
```

3.3 Salve Localmente:  
_3.3 Save Locally:_

```python
git commit -m "Adicionada funcionalidade de login"
```

3.4 Envie para a Nuvem: Como você clonou, o Git já sabe para onde enviar.  
_3.4 Send to the Cloud: Since you cloned, Git already knows where to send._

```python
git push
```

3.5 Receba Atualizações (Opcional, mas recomendado): Se você trabalha em equipe ou em dois computadores, sempre antes de começar a trabalhar, garanta que seu local está atualizado com o que está na nuvem:  
_3.5 Receive Updates (Optional, but recommended): If you work in a team or on two computers, always before starting to work, make sure your local is updated with what's in the cloud:_

```python
git pull
```

## 🔹Fluxo 3 - Melhor prática de projetos novos e estrutura do inicio🔹
## _🔹Flow 3 - Best practice for new projects and initial structure🔹_

### ⚡Passo 1: Criar o destino.
### _⚡Step 1: Create the destination._

1.1 Vá no site github.com e faça login.  
_1.1 Go to the github.com site and log in._

1.2 Clique no botão New (ou no sinal de + no canto superior direito -> New repository).  
_1.2 Click the New button (or the + sign in the upper right corner -> New repository)._

1.3 Dê um nome ao repositório (ex: meu-projeto-estudos). Ideal que seja igual a pasta para sua identificação rapida  
_1.3 Give the repository a name (e.g., my-project-studies). Ideally, it should be the same as the folder name for quick identification._

IMPORTANTE: Deixe as opções "Add a README file", ".gitignore" e "License" DESMARCADAS.
Por que? Se você marcar isso, o GitHub cria um histórico lá. Como você já tem um histórico no seu PC, tentar juntar os dois agora daria conflito. Queremos o repositório vazio.  
_IMPORTANT: Leave the "Add a README file", ".gitignore", and "License" options UNCHECKED. Why? If you check this, GitHub creates a history there. Since you already have a history on your PC, trying to merge the two now would cause conflicts. We want an empty repository._

1.4 Clique em Create repository.  
_1.4 Click Create repository._

Quando você cria o repositório diretamente no GitHub, ele já vem com: ✔ estrutura limpa / ✔ branch main criada / ✔ repositório remoto configurado / ✔ painel de commits e configurações prontos. Isso evita erros comuns como: origin errado / conflitos com main / ter que configurar remoto na mão / repositório local divergente do remoto  
_When you create the repository directly on GitHub, it already comes with: ✔ clean structure / ✔ main branch created / ✔ remote repository configured / ✔ commit panel and settings ready. This avoids common errors such as: wrong origin / conflicts with main / having to configure remote manually / local repository diverging from remote_

### ⚡Passo 2: Conectar com o reposotório local
### _⚡Step 2: Connect with the local repository_

2.1 Navegue pelo bash até o repositório que você ira criar tudo e confira o local  
_2.1 Navigate through bash to the repository where you will create everything and check the location_

Resultado > C:\Users\Reinaldo\Desktop\meu-projeto\  
Result > C:\Users\Reinaldo\Desktop\my-project\

2.2 Confira o caminho com o comando:  
_2.2 Check the path with the command:_

```python
pwd
```
2.3 Depois clone o repositório vazio que você criou no GitHub:  
_2.3 Then clone the empty repository you created on GitHub:_

```python
git clone https://github.com/usuario/repo.git
```
O Git automaticamente:  
_The Git automatically:_

✔ Cria uma pasta local  
✔ Já vem com o diretório .git configurado  
✔ Já define o remoto origin  
✔ Já coloca você na branch main  
✔ Já conecta sua máquina com o GitHub corretamente  

_✔ Creates a local folder  
✔ Comes with the .git directory configured  
✔ Defines the remote origin  
✔ Puts you on the main branch  
✔ Connects your machine to GitHub correctly_  

### ⚡Passo 3: preparar o terreno para iniciar o desenvolvimento
### _⚡Step 3: prepare the ground to start development_

3.1 Entrar na pasta clonada  
_3.1 Enter the cloned folder_

```python
cd meu-projeto
```

3.2 Criar sua branch de desenvolvimento. Geralmente a branch main é a de produção e outras branchs são para desenvolvimento de features, correções, testes, etc.  
_3.2 Create your development branch. Usually, the main branch is the production one, and other branches are for feature development, fixes, tests, etc._

```python
git checkout -b dev
```

### ⚡Passo 4: O Ciclo de Trabalho (Editar e Enviar)
### _⚡Step 4: The Work Cycle (Edit and Send)_

Agora que está conectado, o fluxo é cíclico. Trabalhe: Crie arquivos, edite códigos no VS Code.  
_Now that you're connected, the flow is cyclical. Work: Create files, edit code in VS Code._

4.1 Verifique:
_4.1 Check:_

```python
git status
```

4.2 Prepare:  
_4.2 Prepare:_


```python
git add .
```

4.3 Salve Localmente:  
_4.3 Save Locally:_

```python
git commit -m "Adicionada funcionalidade de login"
```

4.4 Envie para a Nuvem: Como você clonou, o Git já sabe para onde enviar.  
_4.4 Send to the Cloud: Since you cloned, Git already knows where to send._

```python
git push
```

4.5 Receba Atualizações (Opcional, mas recomendado): Se você trabalha em equipe ou em dois computadores, sempre antes de começar a trabalhar, garanta que seu local está atualizado com o que está na nuvem:  
_4.5 Receive Updates (Optional, but recommended): If you work in a team or on two computers, always before starting to work, make sure your local is updated with what's in the cloud:_

```python
git pull
```

Espero te ajudado !  
_I hope I helped!_