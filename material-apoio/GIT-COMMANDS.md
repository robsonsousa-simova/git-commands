# COMANDOS GIT

Iniciar um repositório git (executar o comando abaixo na raiz do projeto) \
**git init**

Criar um arquivo \
**touch nome_do_arquivo** \
Exemplo: touch GIT-COMMANDS.md

Criar um arquivo gitignore (executar o comando na raiz do projeto) \
**touch .gitignore**

Editar um arquivo .gitignore. Na raiz do projeto digite: \
**editor .gitignore**\
Exemplo 1: vi .gitignore \
Exemplo 2: nano .gitignore \
Exemplo 3: navegar até o diretório onde se encontra o arquivo (raíz do projeto) e abrir com o editor de sua preferência. Exemplo: notepad++ ou notepad.

**Observações:** o arquivo **".gitignore"** pode conter diversos arquivos que não serão rastreados (not tracked). Portanto, esses arquivos não deverão estar presentes no repositório remoto do projeto.

\
Alguns exemplos: arquivos específicos da ferramenta de desenvolvimento como Eclipse, Netbeans, Intellij, etc. Afinal, as configurações da IDE da sua preferência é algo pessoal e que não deve impactar
na execução do projeto. Assim, se o Programador1 utiliza o Eclipse e o Programador2 utiliza o Intellij não faz diferença, ou ao menos não deveria fazer ;).

Exemplo: dentro do arquivo '.gitignore' adicionar a seguinte linha: .idea/* \
Assim todos os arquivos do Intellij não estarão presentes quando for realizado o commit.

Exibir o status do git \
**git status**

Exibir o log \
**git log**

Exibir o log em uma linha \
**git log --pretty=oneline**

Exibir o log resumido \
**git shortlog**

Exibir um log que ainda não sei oque é. \
**git reflog**

Mostrar diferença da qual você está prestes a fazer commit. \
**git diff --staged**

Listar os repositórios remotos \
**git remote -v**

Clonar um repositório (SSH ou HTTPS) \
**git clone git@domain:username/repository.git** \
Exemplo1: git clone https://github.com/robsoncartes/projeto-javalin.git \
Exemplo2: git clone git@github.com:robsoncartes/projeto-javalin.git

Editar a URL do repositório remoto (SSH ou HTTPS) \
**git remote set-url origin git@domain:username/repository.git** \
Exemplo 1: git remote set-url origin https://github.com/robsoncartes/projeto-javalin.git \
Exemplo 2: git remote set-url origin git@github.com:robsoncartes/projeto-javalin.git

Adicionar a URL do repositório remoto ao projeto criado localmente. \
Quando é necessário? Quando você cria um projeto remoto vazio, e localmente você criou um projeto já estruturado. Por exemplo, um projeto Maven. \
Então se você quer que o seu projeto local aponte para o endereço do repositório remoto do projeto recém criado.\
Exemplo: git remote add origin https://github.com/usuario-qualquer/repositorio-qualquer.git

Adicionar arquivos a área de Stage (arquivos prontos para serem comitados). \
Exemplo 1: Adicionar todos arquivos modificados a área de Stage \
**git add .**

Exemplo 2: Adicionar todos os arquivos modificados de uma terminada extensão. \
**git add** ***.java**

Exemplo 3: Adicionar um arquivo específico a área de Stage \
git add nome_do_arquivo \
**git add .gitignore**

Salvar (**commit**) as alterações realizadas no projeto local. \
**git commit -m** "Meu primeiro commit."

**Obs.:** Lembre-se: antes de fazer o commit você deve adicionar os arquivos quais deseja que sejam comitados a uma área denominada Stage.

Onde o parâmetro “**-m**” indica que você deve fornecer uma descrição para o comit que esta sendo feito.

**Importante:** evite commits com nomes que não descritivos. Por exemplo: git commit -m "Atualização". Mas, atualização do quê? \
Nomes de commits devem descrever o que foi feito. Isso ajuda os Stakeholders a indentificarem o que foi feito em um determinado commit. \
Exemplo 1: git commit -am “Criação do Controlador 'FuncionarioController'.” \
Exemplo 2: git commit -m “Configuração do banco de dados em memória (H2).” \
Exemolo 3: git commit -m "Correção do método buscarPagina da classe de serviço 'ClienteService'." \
Fez uma pequena melhoria (significativa) no código? Funciona? Então, faça um commit.

Rastrear as branchs remotas \
**git fetch -a**

Rastrear as branchs locais \
**git branch -a**

Exibir as branchs remotas \
**git branch -r**

Exibir as branchs locais (apenas) \
**git branch**

Criar uma nova branch \
**git branch nome_da_branch_criada** \
Exemplo: git branch developer

Trocar de branch \
**git checkout nome_da_branch_que se deseja mudar.** \
Exemplo: suponha que existem duas branchs: master e developer \
Suponha você esteja na branch master \
Para utilizar a branch developer \
**git checkout developer**

Criar e utilizar uma nova branch \
**git checkout -b nova_branch**

Resetar um commit \
**git reset --hard commit commit_id** \
Exemplo: git reset --hard cedc856

Para voltar ao um determinado número de commits atrás. \
**git reset --hard HEAD~numero_de_commits_deletados** \
Exemplo: git reset --hard HEAD~1

**git reset --soft HEAD~numero_de_commits_deletados** \
Exemplo: git reset --soft HEAD~2

Forçar um commit (sobrepõe os commits atuais) \
**git push --force origin main** \
**Obs.:** evitar esse comando a menos que seja realmente necessário.

Pesquisar e entender melhor esse comando. \
**git cherry-pick nome_commit**

Pesquisar e entender melhor esse comando. \
**git revert --strategy resolve <commit>**

Limpar o cache \
**git rm -r --cached .** \
**git add .** \
**git commit -m "fixed untracked files"**

Limpar o cache de arquivos específicos \
**git rm -r --cached diretorio/arquivo** \
Exemplo: git rm -r --cached superlists/__pycache__


## ALIAS
**Apelidos para comandos ou conjunto de instruções**

Alias ou apelidos para execução de comandos e podem ser bastante úteis, especialmente quando executamos um determinado comando ínúmeras vezes. Como por
exemplo, o comando **git status**. Não seria melhor ter um apelido para ele? Veja como é simples criar alias para GIT e para o terminal Bash. \
**alias gs="git status"**

Depois de criar o alias de nome **gs**" basta digita-lo para obter o mesmo efeito do comando **git status**. Contudo, é importante saber que há pelo menos duas formas de criar alias:

### **Aliás temporários:**

Alias temporários serão perdidos toda vez que você encerrar (fechar) o terminal do GIT BASH. Para criá-los é bastante simples. A seguir alguns exemplos.
Lembre-se que, depois você poderá criar os que achar conveniente.

Limpa a tela do terminal \
**alias cls="clear"**

Exibir histórico dos últimos comandos digitados no terminal bash. \
**alias h="history"**

Navegar para um determinado diretório do sistema \
**alias documentos="cd /c/Users/usuario/Documments"** \
Exemplo: alias documentos="cd /c/Users/robson/Documents"

Enviar as utilizações para a branch main no repositório remoto \
**alias mmain="git push -u origin main"**

Exibir um log formatado e personalizado \
**alias llog="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"**;

Nesse último exemplo foi criado um alias de nome **llog** qual exibe um log resumido e colorido. Muito útil nos casos de existirem muitos commits.

### **alias permanentes:**

Para criar **alias** permanentes no caso de você estar utilizando sistemas Windows. \
Abra o terminal do GIT BASH em modo Administrador, assim, o alias (apelido) poderá ser executados por qualquer
usuário do sistema (caso queira). Além de que, o arquivo que precisamos editar em modo de escrita só pode ser feito em modo Administrador;

Para isto, abra o arquivo **.bash.bashrc** localizado em **/etc** com um editor da sua escolha, por exemplo: vi, nano ou notepad. Em qualquer lugar desse arquivo (*.bash.bashrc*)
de preferência no início, adicione os comandos alias descritos no exemplos dos alias temporários. Caso você edite o arquivo de modo errado, basta **não salvá-lo**. \
Tanto **alias temporário**, quanto **alias permanentes** tem a mesma sintaxe. Observe que o alias abaixo pode ser feito de tanto de forma permanente, quanto foi feito acima, de forma temporária.

**alias llog="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"**;

Dessa forma, utilize sua criatividade para criar quantos aliases achar necessário. Mas lembre-se: antes de criar um aliás, verifique se o nome do seu alias não é o nome de um comando
existente. De preferência, utilize nomes que você tem certeza que não existem.

Criar alias permanentes no Linux é basicamente feito da mesma forma, só que deve ser feito em modo sudo ou su (administrador em ambientes Linux)
para os casos em que você queira que os outros usuários possam executá-los. Além disso, independente da distribuição Linux que se utilize, o arquivo está contido geralmente
mesmo diretório **/etc**.
No entanto, o nome desse arquivo pode variar de uma distribuição para outra: por exemplo, no CentOS ou Fedora **/etc/bash.bashrc**. Já no Ubuntu o nome é **/etc/bashrc**.

**Observação:** caso você esqueça o alias que você criou: crie um alias para exibir o conteúdo do arquivo **.bash.bashrc**. Assim: **alias exibirArquivoBash="cat /etc/bash.bashrc"**.


Por fim, é possível criar aliases especificos **SOMENTE para o GIT**. E o processo é mais simples ainda. Mas aqui vou deixar apenas um exemplo. Se você gostar, então você poderá criar outros.

**git config --global alias.logline "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"** \
Criado esse aliás, digite no terminal o seguinte comando: **git logline**

Em resumo: você pode criar alias para executar um simples comando ou um conjunto de intruções, navegar entre diretórios, dar permissões, etc.


