# TutorialGit
Um tutorial básico de Git para me ajudar e ajudar outros :)


Oii gente, sejam bem vindos😃, eu sou Messias Viana e vou fazer este guia com os principais pontos para se conseguir utilizar o Git/Github na prática

## Instalar o Git

<a href="https://git-scm.com/downloads">Link para os downloads</a>

## Configurar o Git

* `git config --global user.name "Seu nome"` - vai alterar o nome de usuario
* `git config --global user.email "Seu email"` - vai alterar o email de usuario
* `git config --global core.editor vscode` - vai mudar qual editor que voce está usando

Para ver todas as configurações que estão sendo utilizadas é só dar um `git config --list`, que irá mostrar seu email, nome, enfim, tudo que você configurou.

## Iniciar um repositório local

Primeiramente você deve ir para a pasta onde quer iniciar o repositório pelo `CMD` (você pode mudar de pasta utilizando o comando `cd`), ou também pode-se utilizar o `Git Bash`, que atualmente já é instalado quando se instala o Git.

* Já na pasta, dê o comando `git init`, que irá criar uma pasta oculta no local, não apague essa página pois é ali que tudo acontece.

Se você der o comando `git init` já em uma pasta com arquivos, ele vai criar a pasta sem alterar nada.

## Commits

Já com seu repositório criado, você já pode criar/alterar arquivos no seu editor, e para salvar as alterações você deve dar um `commit`.
  
Para dar um commit, primeiramente você deve adicionar os arquivos no monitoramento do git

* Para fazer isso basta dar um `git add .`, isso irá adicionar todos os arquivos na pasta ao monitoramento

* Caso você queira adicionar apenas arquivos específicos basta substituir o `.` pelo nome do arquivo. Ex: `git add index.html`

Dica: o comando `git status` vai te mostrar quais arquivos estão sendo monitorados ou não.

Agora sim você pode salvar a alteração

* Depois de adicionar os arquivos, dê o comando `git commit -m "comentário sobre a alteração"`, o comentário serve para descrever as modificações feitas, então lembre-se de escrever apenas o essencial, pois isso irá ajudar você e outros programadores que utilizarem o repositório.

* Depois de dar o commit, irá aparecer em qual branch foi feito o commit, os 7 primeiros digitos da hash que indentifica o commit e depois as alterações que foram feitas.

<img src="https://cdn.discordapp.com/attachments/719925704208416798/958465403070341190/unknown.png">

Dica: o comando `git log` vai te mostrar todos os commits dados na branch.

## Branch

 Uma Branch é como versões do seu código, por exemplo, há uma branch chamada 1.0 e outra 2.0, uma vez que você seleciona a branch 2.0, todas alterações que você fizer serão salvas apenas na branch 2.0, não afetando a 1.0.
 
* Quando você cria um repositório a branch vai se chamar `master` por padrão.

* Quando uma nova branch é criada, todos arquivos já viram salvos, então você não precisa começar do zero.

* Para criar uma nova branch, dê o comando `git branch nomedabranch`, para criar você deve dar pelo menos um commit antes.

* Para mudar de branches, utiliza-se o comando `git checkout nomedabranch`, isso vai fazer com que você mude de branch e as alterações feitas serão salvas na branch selecionada.

* Caso você queria `deletar` sua branch localemnte, dê o comando `git branch -D nomedabranch`, onde primeiro você deve mudar para outra branch antes de deletar.

## Deletar e Reverter Modificações

Para você deletar um commit, primeiramente você deve saber que irá ser deletado todos os commits depois do commit selecionado. Há três tipos de reset que você pode dar:
* `--soft` vai voltar para o commit sem deletar nenhuma modificação feita (não precisa dar o `git add` depois do reset).
* `--mixed` é igual ao soft, porém tem que dar o `git add` antes de commitar.
* `--hard` vai deletar tudo e voltar para o commit selecionado

*Para selecionar um commit, use `git log` e copie a hash inteira ou apenas os 7 primeiros dígitos.*

* Depois de decidir qual o tipo do reset e em qual commit quer voltar, é só usar: `git reset tipodoreset hashdocommit`

Caso você queira reverter alguma modificação sem deletar nenhum commit, use o `git revert --no-edit hashdocommit"`. Este comando irá deletar tudo o que você fez somente no commit selecionado e não irá afetar os outros commits.

