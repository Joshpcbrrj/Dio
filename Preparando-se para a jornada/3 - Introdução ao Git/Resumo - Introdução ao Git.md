# Introdução ao Git

## Entenda a importância do Git

> [Git](https://en.wikipedia.org/wiki/Git) foi criado por Linus Torvalds também inventor do Kernel Linux.
> 
- Video do Linus em palestra na Google
    
    [https://www.youtube.com/watch?v=vKRZKau-8MY](https://www.youtube.com/watch?v=vKRZKau-8MY)
    

---

## Navegação via command line interface e instalação

Documentação do Git:
[Documentation](https://git-scm.com/doc)

Instalador do GitHub desktop
[GitHub Desktop](https://desktop.github.com/)

### Cli vs Gui

CLI
Command line interface → interação por linha de comando (terminal)
Ex: Git

Gui
Graphic user interface → Interação por interface gráfica
Ex: GitHub

## Comandos básicos de terminal (Windows shell  vs Unix bash)

<aside>
💡 OBS: A partir do windows 10 temos o PowerShell, que acaba sendo um hibrido e roda ambos os comandos (tanto de shell quanto de bash)

</aside>

Para listar diretórios

```bash
# No shell faremos 
dir 
```

```bash
# No bash faremos 
ls
```

Para mudar de diretórios (Comando igual para todos os terminais)

```powershell
# Em ambos os casos vamos usar o comando:
cd 

# O  cd pode subir um nivel
cd /

#o cd pode ir para uma pasta especifica
cd nome_da_pasta_que_quero_ir

#Para retroceder um nivel vamos usar
cd ..
```

Para limpar o terminal 

```bash
# No Shell vamos fazer :
cls
```

```bash
# No Bash vamos fazer :
clear 

# OBS: No bash temos o atalho"control + l" para limpar.
```

Para criar uma pasta (Comando igual para ambos os terminais)

```powershell
# Em ambos vamos fazer:
mkdir nome_da_pasta_que_queremos_criar
```

Para criar um arquivo de texto simples

```bash
# No shell vamos fazer :
echo hello > hello.txt

#OBS
# Aqui fizemos um truque ja que o "echo" mostra texto no terminal O ">" pegaa saida e
# Usamos a saida paracriar um novo txt 
```

```bash
# No bash faremos :
touch hello.txt

#ou
echo hello > hello.txt
```

Para deletar arquivos 

```bash
# Para deletar arquivos (Não vai funcionar em diretórios)
del nome_do_arquivo

# Para remover diretórios vazios:
rmdir nome_da_pasta

# Para remover diretórios com tudo que tem dentro dele:
rmdir nome_da_pasta /s /q
```

```bash
# No bash faremos (Não funciona em diretórios) :
rm nome_do_arquivo

# Ou pararemoção forçada (Não funciona em diretórios)  :
rm -f nome_do_arquivo

# Para deletar diretórios com tudo que tem dentro dele
rm -rf nome_da_pasta
```

<aside>
💡 Lembrando :

Se ao executar um comando o terminal não der retorno (erro) a instrução foi feita. Podemos chamar de “Silence on success”.

</aside>

---

## Entendendo como o Git funciona

Sha1 ([Secure hash algorithm](https://en.wikipedia.org/wiki/SHA-1))

- Se trata de um algoritmo de encriptação. Esse conjunto criptográfico foi criado pela NSA (agencia de segurança nacional americana).
- A encriptação gera um conjunto identificador de 40 dígitos.

### Encriptando arquivo com SHA1

```bash
# Vamos abrir o git bash na pasta onde esta o arquivo de texto e fazer:
openssl sha1 nome_do_arquivo_de_texto

#Obs
#Após a execução do comando o terminal irá retornar a chave criptografica do arquivo.
#Essa chave será modificada cada vez que o arquivo sofrer alguma modificação.
```

<aside>
💡 **OBS**: Essa é a forma que o Git usa para verificar se um arquivo foi modificado.

</aside>

---

### Objetos internos do Git

Organizando

![1.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/1.jpg)

Blob

![blob.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/blob.jpg)

Trees

![trees.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/trees.jpg)

Commits

![commit.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/commit.jpg)

Fluxo do git

![1.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/1%201.jpg)

---

## Chaves SSH e token

Chave SSH

Forma de estabelecer uma conexão segura entre 2 máquinas.

### Como gerar chave SSH no meu pc para usar no GitHub ? (Reps privados)

```bash
# Gerando a chave com a criptografia correta (Lembrando de por o mesmo e-mail do github).
# Depois de fazer o comando vamos dar um "enter" e por a senha para nossa segurança
ssh-keygen -t ed25519 -C "seu_email_aqui" 

# A chave que usaremos no GitHub é a publica, e pode ser acessada indo para o diretório que salvamos
# Vamos navegar até o diretório padrão com o comando: 
cd diretório_onde_esta_a_chave

# Agora vamos abrir o conteúdo da chave para pegar os caracteres e por no Github.
# Podemos usar o comando abaixo (Lembrando que vamos usar só a chave pública :
cat nome_do_arquivo.pub  

# Agora vamos habilitar o "agent alien", responsavel por lidar com as chaves de acesso.
# Após digitar o comando abaixo, receberemos a informação do "agent pid" processo que rodará no pc 
eval $(ssh-agent -s)

# Agora vamos passar a chave privada para o agent usar (descriptografará a pública com ela)
# Se estivermos dentro do diretório onde a chave esta só vamos passar o nome.
# Se não estivermos no diretório onde ela esta, temos que navegar até ele
ssh-add nome_da_chave_privada #Lembrando que ela não possui pub no final.
```

<aside>
💡 OBS: Como configuramos a chave SSH, qualquer clonagem de repositório só poderá ser feita através do caminho SSH (Escolher na aba code do repositório WEB)

</aside>

Documentação

[Generating a new SSH key and adding it to the ssh-agent - GitHub Docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

### Como gerar token (Reps privados)

Só ir no caminho abaixo logado na sua conta GitHub.

[https://github.com/settings/tokens](https://github.com/settings/tokens)

![1.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/1%202.jpg)

Documentação

[Creating a personal access token - GitHub Enterprise Server 3.3 Docs](https://docs.github.com/en/enterprise-server@3.3/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

<aside>
💡 **OBS**: Atualizara versão do git no windows

```bash
git update-git-for-windows -y
```

</aside>

---

### Iniciando o Git e criando commit

Documentação de comandos git web

[Git - git Documentation](https://git-scm.com/docs/git)

Comandos uteis de ajuda com o git

```bash
# Manual com todos os comandos do Git
man git 

# Comandos principais e suas funcionalidades de forma reduzida
git help
```

Iniciar versionamento do código a partir de uma pasta.

```bash
#Git criará uma pasta vazia com instruções de versionamento.
git init

#Para ver a pasta oculta do git vamos fazer
ls -a

#Para criar nossa primeira branch vamos fazer 
git branch -M main

#Pra ver as branchs do repositório vamos usar:
git branch

#OBS:
# Devemos nos certificar se temos uma branch no repositório
# A ausencia de branch vai gerar erros no envio do código local p/ GitHub
```

Configurar nick name e e-mail (Atrelar autoria ao código).

```bash
# Fazer configurações globais para email
git config --global user.email "seu_email_entre_aspas"

# Para configurar o nome
git config --global user.name "seu_nome_entre_aspas"

# Para ver as configurações
git config --list 

# Para remover alguma configuração para alterar futuramente vamos fazer:
git config --global --unset configuração_que_queremos_apagar
```

Agora vamos criar um arquivo markdown na nossa pasta para testar o versionamento.

```bash
# O arquivo markdown é uma forma mais humanizada de escrever HTML
# A extensão do arquivo é ".md"
touch strogonoff.md
```

Vamos editar nosso arquivo no nosso editor de texto

- Emoji para markdown
    
    [Complete list of github markdown emoji markup](https://gist.github.com/rxaviers/7360908)
    
- Formatações do markdown
    
    [Markdown Guide](https://www.markdownguide.org/)
    
    [Formatação de texto com Markdown](https://support.zendesk.com/hc/pt-br/articles/4408846544922-Formata%C3%A7%C3%A3o-de-texto-com-Markdown#topic_xqx_mvc_43__line_break)
    

```markdown
#Strogonoff de frango :chicken:
###ingredientes
* 1 Quilo de frango sem pele
* 1 Tablete de caldo de galinha
* 3 Colheres de sopa de óleo
* 2 Latas de creme de leite sem soro
* 2 Colheres de sopa de molho de tomate
* 2 Colheres de sopa de ketchup
* 2 Colheres de sopa de mostarda
* Champignon
* Batata palha e arroz branco para acompanhar

###Modo de preparo
1. Em uma panela de fogo médio, acrescente o óleo e o caldo de galinha e, 
sissolva o caldo. Logoem seguida coloque ofrango picado emcubos na panela e deixe cozinhar, 
sempre dando uma olhada pra não queimar.
   
2. Assim que o frango estiver bem cozido, acrescente o molho de tomate, 
o molho de tomate, oketchup, amostarda e o champignon a gosto.

3. Abaixe o fogo e coloque o creme de leite e mexa bem 
até se tornar uma mistura homogênea.

4. Esta pronto para servir.

>Receitinha massa, familia ! Testei e deu bom aqui.
```

Agora vamos fazer o versionamento do nosso arquivo markdown com o Git

```bash
# Adicionando as modificações em staged
git add nome_do_arquivo 

#Ou, se quisermos versionar mais de um arquivo 
git add *
```

```bash
# Adicionando uma mensagem na modificação feita
git commit -m "mensagem_entre_aspas"
```

---

## Ciclo de vida de arquivos no Git

Git init

Cria repositório dentro da pasta alvo.

### Esquema de ciclo de arquivos do Git

![1.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/1%203.jpg)

Untracked

- O Git não conhece o arquivo

Staged (Quando rodamos o Git add)

- O arquivo espera para entrar no palco (analogia boa).

Unmodified (Sha1 base)

- O arquivo ainda não sofreu modificações.

Modified (O Sha1 sofreu modificações)

- O Git percebe novas inclusões no arquivo
- Um novo git add aqui vai jogar o arquivo para staged e espera o commit e retorna para unmodified.

<aside>
💡 **Lembrando** :

Unmodified/ modified/ staged são os ciclos normais dos arquivos Git

![1.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/1%204.jpg)

</aside>

Para monitorar o arquivo e ver o estado atual dele vamos:

```bash
# Comando importante para saber o que faremos a seguir com o arquivo.
git status
```

Agora vamos criar outra pasta e mover o nosso arquivo criado na aula anterior para dentro dela.

```bash
# Criando a pasta "receitas"
mkdir receitas

# Movendo o arquivo "strogonoff" para dentro da nova pasta
mv strogonoff ./receitas
```

Como movemos  o arquivo, veremos o status que o arquivo “strogonoff” foi deletado e que temos um  arquivo não trackeado, que é o diretório criado no passo anterior “receitas” (Como no print)

![Screenshot_1.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/Screenshot_1.jpg)

Vamos criar um novo snapshot dos nossos arquivos. Agora jogaremos as novas modificações para “Staged”

```bash
# Lembrando que vamos adicionar o arquivo e a nova pasta separando por espaço
git add strogonoff.md receitas/
```

O novo status ficará aguardando o commit :

![Screenshot_2.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/Screenshot_2.jpg)

<aside>
💡 **OBS**: O Git também expõe que podemos remover as modificações “git add” com o comando :

```bash
#Usando o comando de restore vamos voltar os arquivos para unstaged
git restore --staged nome_do_arquivo
```

</aside>

Depois de por o arquivo em “staged” temos que comentar a mudança usando o “commit”

```bash
# Comentando as novas modificações
git commit -m "comentario_entre_aspas"
```

Após o commit receberemos algo como: 

![1.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/1%205.jpg)

Para visualizar os commits feitos vamos usar o :

```bash
git log 
```

![2.jpg](Introduc%CC%A7a%CC%83o%20ao%20Git%20d4675c03192e46dd96bf60bbb4caeaaf/2.jpg)

Aqui vamos ter 3 formas diferentes de reset:

1. Reset soft (Podemos fazer **commit** de novo).
    
    ```bash
    #Volta po arquivo para fase de staged
    git reset --soft  nome_do_commit_anterior
    ```
    
2. Reset mixed (Podemos fazer novo **git add**).
    
    ```bash
    #Volta o arquivo para fase de modified
    git reset --mixed  nome_do_commit_anterior
    
    #Podemos fazer a diff da modificação com o conteúdo anterior 
    #Antes de fazer o "git add"
    ```
    
3. Reset hard (Desfaz tudo e volta ao estado do commit anterior).
    
    ```bash
    #Vai desfazer qualquer mudança realizada desde o commit anterior.
    git reset --hard  nome_do_commit_anterior
    ```
    

Agora vamos criar um arquivo readme para por um atalho para nossas receitas futuramente

```bash
# Vamos criar o arquivo de outra forma
echo > README.md
```

Editando arquivo README.md

```markdown
# Livro de receitas :man_cook:

Saudações !!! Bem vindo ao livro das receitas, chefe(a) :v:.

* Strogonoff de frango
```

---

## Trabalhando com GitHub

Após criar o repositório no site do GitHub ou app vamos associar com o nosso repositório local 

```bash
# Vamos por um "alias" (nome) nesse repositório. Por padrão é usado "origin".
git remote add origin link_http_do_repositório_dado_no_GitHub

# Para verificar se esta incluso vamos usar o comando:
git remote -v
```

Agora vamos enviar o nosso código do repositório local Git para o repositório do GitHub

```bash
# No comando informaremos o repositório que vai receber e depois a branch que vamos enviar
git push origin main
```

---

## Resolvendo conflitos

Para atualizar nosso repositório local comparando com o original

```bash
# Em caso de conflito, o git vai pedir para que fassamos um:
git push

# Após o push, ele irá marcar os arquivos em conflito. 
# Teremos que resolver esses conflitos e fazer um push, 
# que irá gerar outro commit informando o conclito no final.
```

Diferença entre download do código e clonagem

No download → Pegaremos o repositório e o código.

No clone → Pegaremos o código com o versionador git dentro dele.