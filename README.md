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

<img src="https://cdn.discordapp.com/attachments/719925704208416798/958465403070341190/unknown.png" />

Dica: o comando `git log` vai te mostrar todos os commits dados na branch.

## Branch

 Uma Branch é como versões do seu código, por exemplo, há uma branch chamada 1.0 e outra 2.0, uma vez que você seleciona a branch 2.0, todas alterações que você fizer serão salvas apenas na branch 2.0, não afetando a 1.0.
 
* Quando você cria um repositório a branch vai se chamar `master` por padrão.

* Quando uma nova branch é criada, todos arquivos já viram salvos, então você não precisa começar do zero.

* Para criar uma nova branch, dê o comando `git branch nomedabranch`, para criar você deve dar pelo menos um commit antes.

* Para mudar de branches, utiliza-se o comando `git checkout nomedabranch`, isso vai fazer com que você mude de branch e as alterações feitas serão salvas na branch selecionada.

* Caso você queria `deletar` sua branch localemnte, dê o comando `git branch -D nomedabranch`, onde primeiro você deve mudar para outra branch antes de deletar.

* No caso de excluir a branch remotamente(*logo em seguida irei mostrar como conectar o repositório local com o remoto*), o comando é: `git push origin :nomedabranch`, note que há um `:` antes do nome da branch que irá ser deletada, e o `origin` é o nome do repositório, podendo ser diferente.

## Deletar e Reverter Modificações

Para você deletar um commit, primeiramente você deve saber que irá ser deletado todos os commits depois do commit selecionado. Há três tipos de reset que você pode dar:
* `--soft` vai voltar para o commit sem deletar nenhuma modificação feita (não precisa dar o `git add` depois do reset).
* `--mixed` é igual ao soft, porém tem que dar o `git add` antes de commitar.
* `--hard` vai deletar tudo e voltar para o commit selecionado

*Para selecionar um commit, use `git log` e copie a hash inteira ou apenas os 7 primeiros dígitos.*

* Depois de decidir qual o tipo do reset e em qual commit quer voltar, é só usar: `git reset tipodoreset hashdocommit`

Caso você queira reverter alguma modificação sem deletar nenhum commit, use o `git revert --no-edit hashdocommit"`. Este comando irá deletar tudo o que você fez somente no commit selecionado e não irá afetar os outros commits.

## Criar repositório no Github

Para criar um repositório, você deve ter uma conta. Depois de criar sua conta vá em `Criar nono repositório`

Você vai colocar todas as informações do projeto que está pedindo

<img src="https://cdn.discordapp.com/attachments/719925704208416798/958479652282834974/unknown.png" />

Depois de criar o repositório remoto, vai aparecer uma tela com um link

<img src="https://cdn.discordapp.com/attachments/719925704208416798/958480150004129822/unknown.png" />

* Para conectar o repositório local ao remoto, copie o link que aparece e utilize o comando: `git remote add origin linkcopiado` (*normalmente utiliza-se `origin` para o nome do repositório remoto, porém você pode mudar*)


* Se você quiser verificar se foi adicionado, dê `git remote`, irá mostrar o nome do repositório que está ativo.

Agora podemos enviar nossos arquivos do repositório local ao remoto

* Com o seguinte comando: `git push -u origin master` vocÊ vai enviar seus arquivos para o repositório remoto, onde o `origin` é o nome do repositório e o `master` é o nome da branch que você quer enviar, podendo ser alterados os dois items.(*se não está configurado o email e senha do github, irá pedir para colocar, então coloque e será enviado os arquivos logo depois*)

* Agora que os dois repositórios estão conectados, podemos enviar nossas alterações para o repositório remoto usando o comando: `git push origin main`(*sem o -u*), depois claro de ter dado o commit nas alterações.

* Se tiver algum arquivo que você não queira enviar, crie um arquivo chamado `.gitignore` na pasta e dentro dele coloque quais arquivos você quer que não seja enviado
<img src="https://cdn.discordapp.com/attachments/719925704208416798/958485814373933096/unknown.png" />

## Pull, Clonar e Fork

No repositório podemos ter várias pessoas trabalhando em um projeto, ou no Github temos a opção de contribuir com outros projetos, para puxar essas alterações feitas por outras pessoas, damos o nome de pull.

* Para dar um pull, use o comando: `git pull origin master`, isso irá puxar todos os arquivos e commits para seu repositório local.

Agora temos a opção de clonar, que vamos pegar um repositório remoto, qualquer um que seja e copiar os arquivos para nosso PC.

* Para clonar, pegue a `URL do repositório`, e dê o comando: `git clone linkdorepositorio`, isso irá fazer uma cópia dos arquivos onde o `CMD` está, então certifique-se de verificar se está onde você quer que seja copiado os arquivos.

<img src="https://cdn.discordapp.com/attachments/719925704208416798/958488664374140998/unknown.png" />

*Ou pegue na própria URL do Giithub*

Para contribuir com um projeto, primeiros temos que dar um Fork, depois clonar, enviar as alterações e mandar para o dono do repositório para ele ver se aceita ou não a contribuição enviada.

* Para dar um Fork, vá em um repositório que quer contribuir, no canto superior direito irá ter um botão `Fork`, quando clicado, vai criar um repositório idêntico ao original, mas só que em seu perfil.

<img src="https://cdn.discordapp.com/attachments/719925704208416798/958490811350278214/unknown.png" />

* Agora, clone o repositório criado em seu perfil, modifique o que quiser modificar, dê commits, depois envie para o repositório com o push, porém as alterações não vão afetar o repositório original, o `Pull Request` vai enviar as alterações para o criador do repositório original.

* Para dar um Pull Request, vá no repositório criado em seu perfil, clique em Pull Requests > New pull request > Create pull request.

<img src="https://cdn.discordapp.com/attachments/719925704208416798/958496375576883201/unknown.png" />

Você irá colocar um nome intuitivo, que mostre as alterações feitas e também é bom criar uma boa descrição do que alterou, não somente explicando o que é, mas ensinando ao dono do repositório original a forma como ele poderá testar também

Depois disso, basta esperar para que o dono da branch original aceite o seu pull request

## Final

O Git/Github abrange diversas funcionalidades, porém com essas que descrevi, vocês irão conseguir criar projetos bem legais e aproveitar das funcionalidades de se ter um repositório.

Recomendo que se vocês tiverem alguma dúvida, passarem na <a href="https://git-scm.com/doc">documentação oficial do Git</a> e procurar a resposta lá, caso queira criar um pull request para acrescentar ou alterar informações neste repositório que criei, fique à vontade😄.

Até mais.
