# GIT / GIT HUB
# O Flow completo de operação / The complete operational Flow

⚙️ PT - O processo completo para que possamos entender como funciona o GIT e o GIThub em conjunto trabalhando em equipe.

⚙️ EN - The complete process so that we can understand how GIT and GIThub work together as a team.


## 🔹Fluxo 1: O Caminho "Do Zero Local para a Nuvem"🔹

Cenário: Você criou uma pasta no seu computador, escreveu códigos e agora decidiu que isso precisa ir para o GitHub e o repositório remoto ainda não existe.

### ⚡Passo 1: Preparar o Terreno Local (No seu PC)
1.1 Navegue até a pasta pelo bash.  


1.2 Inicie o Git, (Cria a pasta oculta .git)  
```python
git init
```

1.3 Renomeie a branch principal (Padrão Moderno): O Git antigo chama a branch principal de master. O GitHub e o mercado usam main. Vamos padronizar agora para evitar problemas futuros:  
```python
git branch -M main
```

1.4 Adicione seus arquivos à "Caixa de Envio" (Staging):
```python
git add .
```

1.5 Feche o pacote (Commit):
```python
git commit -m "Primeiro commit: Estrutura inicial do projeto"
```

1.6 Neste momento, seu código está salvo e versionado, mas apenas no seu computador.  
Você pode parar por ai e versionar apenas na sua máquina se preferir.

### ⚡Passo 2: Criar a "Garagem" na Nuvem (No Site do GitHub)

2.1 Agora precisamos criar o destino. Vá no site github.com e faça login.  

2.2 Clique no botão New (ou no sinal de + no canto superior direito -> New repository).  

2.3 Dê um nome ao repositório (ex: meu-projeto-estudos). Ideal que seja igual a pasta para sua identificação rapida

IMPORTANTE: Deixe as opções "Add a README file", ".gitignore" e "License" DESMARCADAS. Por que? Se você marcar isso, o GitHub cria um histórico lá. Como você já tem um histórico no seu PC, tentar juntar os dois agora daria conflito. Queremos o repositório vazio.  

2.4 Clique em Create repository, e seu repositório estará criado!

### ⚡Passo 3: Conectar e Enviar (O Link)

3.1 O GitHub vai te mostrar uma tela cheia de códigos. Procure a seção "…or push an existing repository from the command line".

3.2 Crie a ponte (Remote): Copie e cole o comando que o GitHub te deu (parecido com este substituindo SEU-USUARIO e NOME-DO-REPO):
```Python
git remote add origin https://github.com/SEU-USUARIO/NOME-DO-REPO.git
```
Explicação: Você está dizendo ao Git local: "Adicione um endereço remoto chamado 'origin' que aponta para essa URL".  

3.3 Envie os arquivos (Push):
```python
git push -u origin main
```

O -u cria um vínculo permanente. Da próxima vez, basta digitar git push. Pode ser que o Git peça seu usuário e senha (ou token) nesta etapa.

## 🔹Fluxo 2: O Caminho "Da Nuvem para o Local" (Clonar)🔹

Cenário: O projeto já existe no GitHub (pode ser um projeto open source ou um repositório que você criou em outro computador) e você quer trazê-lo para sua máquina para trabalhar.

### ⚡Passo 1: Trazer o Projeto (Download Inteligente)

1.1 Abra o terminal na pasta onde você quer que o projeto seja salvo (ex: cd Desktop).

1.2 No site do GitHub, na página do projeto, clique no botão verde <> Code

1.3 Copie a URL (HTTPS)

1.4 No terminal, digite:
```python
git clone https://github.com/USUARIO/NOME-DO-REPO.git
```

O Git vai criar uma pasta com o nome do repositório e baixar tudo dentro dela. A conexão remota (origin) já vem configurada automaticamente!

### ⚡Passo 2: Entrar no Escritório (Crucial!)
2.1 Entre na pasta que acabou de ser criada: Muitos iniciantes esquecem este passo e dão comandos na pasta errada.

```python
cd nome-do-repo
```

### ⚡Passo 3: O Ciclo de Trabalho (Editar e Enviar)

Agora que está conectado, o fluxo é cíclico. Trabalhe: Crie arquivos, edite códigos no VS Code.

3.1 Verifique:
```python
git status
```
3.2 Prepare:
```python
git add .
```
3.3 Salve Localmente:
```python
git commit -m "Adicionada funcionalidade de login"
```
3.4 Envie para a Nuvem: Como você clonou, o Git já sabe para onde enviar.
```python
git push
```
3.5 Receba Atualizações (Opcional, mas recomendado): Se você trabalha em equipe ou em dois computadores, sempre antes de começar a trabalhar, garanta que seu local está atualizado com o que está na nuvem:
```python
git pull
```

## 🔹Fluxo 3 - Melhor prática de projetos novos e estrutura do inicio🔹

### ⚡Passo 1: Criar o destino.

1.1 Vá no site github.com e faça login.

1.2 Clique no botão New (ou no sinal de + no canto superior direito -> New repository).

1.3 Dê um nome ao repositório (ex: meu-projeto-estudos). Ideal que seja igual a pasta para sua identificação rapida

IMPORTANTE: Deixe as opções "Add a README file", ".gitignore" e "License" DESMARCADAS.
Por que? Se você marcar isso, o GitHub cria um histórico lá. Como você já tem um histórico no seu PC, tentar juntar os dois agora daria conflito. Queremos o repositório vazio.

1.4 Clique em Create repository.

Quando você cria o repositório diretamente no GitHub, ele já vem com: ✔ estrutura limpa / ✔ branch main criada / ✔ repositório remoto configurado / ✔ painel de commits e configurações prontos. Isso evita erros comuns como: origin errado / conflitos com main / ter que configurar remoto na mão / repositório local divergente do remoto

### ⚡Passo 2: Conectar com o reposotório local

2.1 Navegue pelo bash até o repositório que você ira criar tudo e confira o local

Resultado > C:\Users\Reinaldo\Desktop\meu-projeto\

2.2 Confira o caminho com o comando:
```python
pwd
```
2.3 Depois clone o repositório vazio que você criou no GitHub:

```python
git clone https://github.com/usuario/repo.git
```
O Git automaticamente:

✔ Cria uma pasta local  
✔ Já vem com o diretório .git configurado  
✔ Já define o remoto origin  
✔ Já coloca você na branch main  
✔ Já conecta sua máquina com o GitHub corretamente  

### ⚡Passo 3: preparar o terreno para iniciar o desenvolvimento

3.1 Entrar na pasta clonada
```python
cd meu-projeto
```

3.2 Criar sua branch de desenvolvimento. Geralmente a branch main é a de produção e outras branchs são para desenvolvimento de features, correções, testes, etc.

```python
git checkout -b dev
```

### ⚡Passo 4: O Ciclo de Trabalho (Editar e Enviar)

Agora que está conectado, o fluxo é cíclico. Trabalhe: Crie arquivos, edite códigos no VS Code.

4.1 Verifique:
```python
git status
```
4.2 Prepare:
```python
git add .
```
4.3 Salve Localmente:
```python
git commit -m "Adicionada funcionalidade de login"
```
4.4 Envie para a Nuvem: Como você clonou, o Git já sabe para onde enviar.
```python
git push
```
4.5 Receba Atualizações (Opcional, mas recomendado): Se você trabalha em equipe ou em dois computadores, sempre antes de começar a trabalhar, garanta que seu local está atualizado com o que está na nuvem:
```python
git pull
```

Obrigado!
Thank you!