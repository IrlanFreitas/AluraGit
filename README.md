
# Git - Controle de Versão Distribuído


**Chaves Git**: C:\Users\Dell-5547\.ssh

**Git** - Trabalhar localmente, depois subir para um servidor.

**Github/Gitlab** - Plataforma online onde pode hospedar códigos com o git.

#### Github

	Depois de criar o repositório, ir nele, e pode baixa-lo
	pegando a url para clonar o projeto (git clone)

#### Fluxo de trabalho que uso no Git

 1. git status; 
 2. git pull (sincronizar com o remoto e resolver
    conflitos);
 3. git add nomeArquivo.extensao;  
 4. git commit -m "comentário";  
 5. git push origin master.

### Comandos 
___
	Necessário lembrar das variações dos comandos

***git tag*** - Visualizar versões dos arquivos.

	Controle geral de versões: 
	Esse comando serve para adicionar um marcador de versão 
	(não sendo somente numerada, como "v1.0a","v1.0b"), 
	para que tenhamos controle da evolução do projeto. 
	Com isso é permitido

	adicionar um marcador ao projeto que é chamado de tag, 
	o comando permitime visualizar todas as tags do projeto

***git checkout*** - Baixar todo o projeto por versão, com git checkout v1.0a por exemplo.

	git checkout design (branch criada) - O comando checkout também 
	é utilizado para modificar a branch que estamos trabalhando, da 
	master(principal) para a design(branch).

	git checkout -b design - Que indica que você quer mudar para a 
	branch design, mas ao mesmo tempo criá-la com a opção -b que 
	representa nova branch porem, sem fazer a ligação entre branch 
	remota e branch local.

***git diff*** - Visualizar o que foi alterado entre arquivos e nas versões do projeto. Exemplo: 

	git diff v1.0a v1.0b: Exibe todas as diferenças entre suas versões seleciondas;
	
	git diff: Exibe todas as diferenças entre sua cópia local e o índice sincronizado;
	
	git diff –cached: Exibe todas as diferenças entre o índice sincronizado e o último  *commit*;
	
	git diff HEAD: Exibe todas as diferenças entre sua cópia local e o último commit  realizado;

***git blame*** - Capacidade de mostrar alteração linha a linha do arquivo, e quem alterou, quando foi alterado.  Exemplo:
	
	git blame index.html

***git clone URL.git*** - Para baixar o projeto na máquina localmente e desenvolver, por padrão coloca numa pasta com o mesmo nome do repositório(URL).

***git init*** - Transformar sua pasta em repositório controlado pelo git, *se estiver vazia a pasta continua com aparência normal porem, já é um repositório git com uma pasta *.git* .

***git ls-files*** - Para saber dentro do projeto quais arquivos o git está controlando.

***git status*** - Mostra o estado atual do repositório local pro git. Caso aparecam arquivos UNTRACKTED quer dizer que o arquivo(s) não é controlado pelo git.

***git add*** - Adiciona os arquivos (novos) não gerenciados pelo git ao repositório e modificações de arquivos já gerenciados. 
Sendo que é necessário do nome do arquivo como - 

	git add index.html: Adiciona somente o arquivo selecionado
	
	git add . (ponto): Adiciona todos os arquivos não rastreados (tracked). 
	
	git add -i: Forma interetiva de adicionar arquivos.

***git commit*** - Salva as alterações dos arquivos monitorados no repositório localmente.
Exemplo:
	
	git commit -m "comentário"

git config user.name ""

git config user.email "" - Configurando quem é o usuário que está fazendo o commit, para conseguir rastrear.

***git remote add URL.git*** - Ligação entre o Git e Github (Repositório remoto)

***git log*** - Exibe o histórico dos usuários que fizerem commit, com data, versão, apertando q ele saí da "tela" de log.

	git log -p: Exibe cada umas das alterações dos commits linha a linha.

	git log --pretty: Configurando a forma de visualizar os logs.

	git log --stat: Forma resumida de exibir os logs.

	git log --graph: Mostra de forma mais visual os caminhos percorridos pelo repositório.

***git whatchanged*** - Consegue visualizar além da mensagem do commit, quais os arquivos que foram alterados.

	Porem, se utilizar o comando git whatchanged -p (flag),
	consegue visualizar cada linha que foi alterada e 
	em cada arquivo.

***git remote*** - Mostra quais repositórios remotos o repositório local tem.

	git remote add origin URL.git: Adiciona um repositório remoto 
	com o nome de origin ao seu repositório local

**Sintaxe completa: git remote add [nome_do_repositorio] [uri_do_repositorio]**

	Ao executarmos o comando, nenhuma saída é mostrada no prompt.

	git remote -v - Visualiza os repositórios remotos com a url.

***git push*** - Envia as alterações do que está salvo localmente para o repositório remoto.

*Interessante de fazer no primeiro push, a opção -u ou --set-upstream. Ela atrela a branch remota à local, fazendo com que não seja mais necessário passar como parâmetros a origem e a branch no comando push, que fica então assim: git push.*

***Exemplos:***

	git push origin(remote) master(branch): Envia as alterações pro 
	repositório remoto demominado origin com os dados da branch 
	chamada master, seria do master pra o origin

	git push -u origin(remota) design(branch): Com o -u, o git 
	associa a branch a master e não ocorrerá erros quando executar 
	o comando git pull, pois ele saberá que a master está 
	atualizada.

	git push -d origin(remota) design(branch): Este comando remove 
	a branch remota design.

	git pull origin(remote) master(branch): Atualiza o repositório 	
	local com as modificações do repositório remoto, 
	para lidar com os conflitos.

***git clone URL.git*** - Clona (Baixa) um repositório que está a url.git para a máquina, onde é criado uma pasta com o nome do repositório, isso pode ser modificado com mais um argumento no comando, que é:

	git clone https://github.com/[usuario_do_dono_do_repositorio]/curso-git.git 
	meuprojeto <- Nome modificado. Não é recomendado mudar por conta de conflitos com o nome da pasta

*Ao clonar um repositório, não precisamos adicionar o repositório remoto através do comando git remote add, pois tudo já é feito pelo comando git clone, dando um alias "origin" para o repositório.*

***git branch*** - Exibi todas as branches do repositório. E um astérico(*) indica a branch atual do repositório, a que estamos trabalhando no momento.

	git branch nomeBranch - Cria uma nova branch para poder 
	trabalhar, como git branch design, que inicialmente é um ponto 
	de partida a partir da master, quer dizer, que tudo o que tem 
	lá é clonado para a branch.

	git branch -r - Exibe as branches criadas no repositório 
	remoto, ainda não atualizado.

	git branch -a - Exibe as branches locais e remotas.

	git branch -d nomeBranch - Remove uma branch local se estiver 
	sincronizada com outra é necessario utilizar o paramentro -D.

	git branch -t design origin/design - Cria uma branch local 
	baseada(trackeada) na branch criada remotamente, pois o pull só 
	adiciona os arquivos que estão na master.


***git fetch origin<remote repository>*** - Este comando verifica todas as atualizações que foram realizadas no repositório de atalho origin. Traz as alterações do repositório remoto sem colocadas no projeto. Apenas realizará o download das novas alterações que não temos ainda em nosso repositório, mas não vai aplicá-las ainda.

***git merge nomeBranch*** - Traz os commits da branch local para a branch master, mais especificamente da branch que está no comando git merge <branch> para a branch que está no momento, nesse caso é necessário fazer o git checkout master para obter os commits , que é a branch sempre ligada ao repositório.

Move os commits de uma determinada branch para outra branch.

Git 

***git rebase master(base) desenvolvimento(branch que será atualizada)*** - Atualiza um branch com base em outra, para evitar os commits de merge e conflitos muito grandes.

	git rebase --continue - Caso se tenha atualizado a master com 
	git pull, e depois disso se tenha que atualizar a branch com 
	git rebase master branch e ocorra um conflito. Nesse momento, o 
	Git nos deixa resolver o conflito existente no rebase, de forma manual. 
	
	Para isso, o próprio Git nos coloca em um "ambiente 
	temporário", no caso, uma branch temporária, só para 
	resolvermos o conflito. Nesse momento, se fosse executado o 
	comando git branch, teríamos o seguinte resultado:

* (no branch)

* desenvolvimento

* master

Por fim, caso queiramos resolver o conflito, seja para ficar com nossa alteração, ou seja para fazer alguma outra modificação, é necessário permanecer nessa branch temporária, e corrigir os arquivos conflitados. O primeiro passo para descobrir quais arquivos devem ser mexidos é executar o comando git status

, depois de resolvido, isso quer dizer ir no editor ou ide que se está utilizando e tirar os comentários colocados pelo git, para continuar o processo é necessário o comando git rebase -- continue.

### Atributos do rebase
___

**--continue** : deve ser utilizado após a resolução manual de conflitos; 
**--skip** : faz com que suas alterações sejam descartadas; 
**--abort** : volta atrás em todo o processo de rebase
___

git checkout --(Dois hífens) nomeArquivo - Comando que coloca o arquivo(s) como estava no ultimo commit antes do git add, quer dizer no estado de Working Directory, então o arquivo ficará no estado HEAD da branch atual. Caso se possua um arquivo como o mesmo nome da branch utilizar o parametro de --(Dois hífens) para indica que daqui pra frente só serão passados arquivos.

git reset HEAD<estado> proposta_1.html<arquivo ou . para mais de um arquivo> - Coloca o arquivo prospota_1, mesmo depois de estar preparado para o commit com o add, para como era antes do estado de HEAD ou qualquer outro somente utilizar o hash do commit. Isso quando o arquivo(s) já estão em estado de Index.

git reset 92b1c7363f6046df8bf16107f46517cca8529087<identificador do commit> - Voltar ao estado do commit anterior ou fazer uma alteração no commit anterior.

git revert 92b1c7363f6046df8bf16107f46517cca8529087<identificador do commit> - Defazer as alterações de um commit.

git stash - Repositório criado temporariamente para salvar as alterações, para que depois se retorne a continuar de onde foi salvo nesse repositório temporario.

git stash list - Exibe se há algo guardado no stash para ser retomado.

git stash pop - Traz o ultimo stash da lista

git stash apply/pop stats@{0}<código do stash> - Aplica o stash ao repositório, o qual foi indicado pelo código.

git stash drop - Apaga as alterações temporárias guardadas no stash.

git stash clear - Apaga TODA a pilha salva no stash guardado.

git bisect start - Entrar em modo de bisect para procurando commits que tenham alterações que a gente quer.

é necessário que informe ao bisect qual commit é ruim, não tem as alterações que você procura e qual o commit que é bom.

git bisect bad HEAD - Indicando que o estado de HEAD do git é o commit ruim.

git bisect good 92b1c7363f6046df8bf16107f46517cca8529087<identificador do commit> - Indicando qual o commit é o bom para procurar as alterações.

git show 92b1c7363f6046df8bf16107f46517cca8529087<identificador do commit> - Exibe quais alterações foram feitas nesse commit

git show <.(ponto) ou nomeArquivo.ext> - Exibe quais alterações foram em todos os arquivos com o ponto e no arquivo especifíco como nomeArquivo.ext isso no estado de Working Directory ou em outros estados.

git cherry-pick <hash commit> - Traz somente commits colocados no hash para a branch que se está, como exemplo:

Desenvolver funcionalidades em uma branch chamada dev, depois de corrigido bugs, como ainda se está fazendo as novas features, seleciona o commit com os ajustes, traz para master com o cherry-pick e continua a desenvolver na branch dev.

Perigos do Cherry Pick:

Com cherry-pick, temos a liberdade de escolher quais commits queremos trazer para a nossa branch. Mas veja que isso pode ser perigoso: às vezes, trazer um commit isolado, sem os commits ao redor, pode gerar problemas de merge ou até mesmo problemas no código.

O cherry-pick dificilmente será usado quando as alterações todas ficam aglomeradas em um grande commit.

git-cola - Ferramenta gráfica para utilizar o git. Antes de utilizar é necessário baixa-lo e instalar. http://git-cola.github.io/downloads.html

## Chaves de Segurança (SSH)

Agora que temos o Git instalado, podemos utilizar os serviços do Github. Primeiro precisamos criar uma conta. Para isso acessamos a página https://github.com/plans, escolhemos o tipo de conta que queremos criar e prosseguimos preenchendo os formulários pedidos.

Depois de criada nossa conta, precisamos gerar uma senha (chave de segurança) que será responsável por identificar nossa máquina quando fizermos as interações entre nosso projeto e o serviço do Github. Caso não exista essa configuração entre nossa máquina e a conta do Github, o acesso ao serviço pelos comandos do Git será negado.

O processo de criação da chave de segurança é similar em todos os sistemas operacionais: basta abrir o prompt de comando (no caso do Windows, é necessário abrir o Git Bash) e inserir o seguinte comando:

ssh-keygen -t rsa -C "seu_email@provedor.com"

Lembre-se de substituir seu_email@provedor.com pelo seu endereço real de email. A resposta do terminal vai perguntar em qual local do seu disco você quer salvar sua chave de segurança. Para evitar problemas, mantenha a opção padrão. Em algumas versões, pode ser necessário incluir também a opção -b 2048 ou -b 4096 para indicar o tamanho da chave a ser gerada.

A seguir, será solicitada a entrada de uma senha para a chave de segurança. Caso o computador seja público ou compartilhado, é recomendado que sua chave esteja protegida por uma senha. Caso contrário, recomendamos que a senha seja ignorada, bastando pressionar Enter ao ser solicitada a senha e a confirmação de senha.

Agora será necessário realizar o login no http://github.com e seguir para as configurações do seu perfil. Siga "Settings", "SSH and GPG keys" e "New SSH key".

Insira na caixa de texto o conteúdo do seu arquivo id_rsa.pub. O local exato do arquivo foi informado na saída do processo de criação da chave. Cole-o exatamente como ele está, sem adição de espaços ou quebras de linha.

Estágios do Git:

Criar diretório sem nenhum arquivo a ser rastreado - Working Directory

Depois de adicionar untrackted files ao git com o git add é iniciado um novo estágio - Index ou Staging Area

Depois de satisfeitos com o os conteúdos no Index, podemos dar o proximo passo com o git commit e iniciar um novo estágio o HEAD, é o último estado que o git usa como referência.

*working directory representa o estado atual dos arquivos no repositório. Podemos utilizar o comando git add para adicioná-los ao index, ou staging area, que representa uma visão preliminar das modificações que queremos definir para nosso projeto, comparando essas ao HEAD, o último passo completo do nosso projeto, que serve de referência para comparação do trabalho com o working directory.

Observações:

Sempre utilizado o git status para ter noção de como estão os arquivos no projeto.

Caso haja algum não versionado (Untracked files) utilizar o git add e nome do arquivo ou ponto(.)

E também utilizar o git add para modificações de arquivos.

Depois disso fica permitido realizar o commit com o comado git commit -m "Comentário"

Apesar de demonstrarmos o uso do Git desde o início do projeto, podemos utilizar os mesmos passos em um projeto existente para que ele possa, a partir de um momento, ser controlado pelo Git.

O comando git add pode ser executado de modo interativo com a opção -i. Ao rodar o comando completo, git add -i, o modo interativo inicia um prompt de comando específico, aguardando as decisões do usuário sobre quais as alterações detectadas no working directory devem ser adicionadas ao index.

Num ciclo simples de controle de um projeto com o Git, muitas vezes podemos querer adicionar ao HEAD todas as alterações que foram realizadas no working directory. O comando git commit oferece uma opção para que possamos evitar o passo de adicionar manualmente os arquivos ao index, gerando um commit que já inclui todas as modificações feitas no projeto.

by using the -a switch with the commit command to automatically "add" changes from all known files (i.e. all files that are already listed in the index) and to automatically "rm" files in the index that have been removed from the working tree, and then perform the actual commit;

Projetos locais já existentes:

Dentro da pasta onde está o código, usar o comando abaixo para iniciar o repositório

$ git init

Para adicionar todas os arquivos para o próximo commit, executar o comando abaixo

$ git add .

Para efetuar o primeiro commit para seu repositório local, executar o comando abaixo

$ git commit -m "Primeiro Commit"

Para adicionar um endereço de repositório remoto, executar o comando abaixo

$ git remote add origin endereco_do_repositorio.git

Para enviar o código para o repositório remoto adicionado anteriormente, executar o comando abaixo

$ git push -u origin master

Fonte de informações https://help.github.com/articles/adding-an-existing-project-to-github-using-the- command-line/

Github:

Boas práticas, depois de clonar o repositório que se quer trabalhar, é necessário criar uma branch para trabalhar, pois não é recomendado trabalhar direto na master que deve servir somente de sincronização com o remoto. Depois das alterações feitas na branch criada, git status -> git add . -> git commit -m , é necessário trocar de branch com o git checkout e fazer o git marge branch, pois você já está na master e subi essas alterações.

Fork - Criar um cópia de um projeto/repositório que você não tem permissão para poder commitar na sua conta.

Pull Request - Solicitando ao owner/dono do projeto que você deseja enviar uma modificação que você fez, no seu projeto clonado, mesmo que você não tenha permissão para commitar.

Watch - Permite seguir um repositório e acompanhar seu progresso, sem necessáriamente contribuir. Github te notifica a cada atividade que ocorre no repositório, te permitindo acompanhar praticamente em tempo real o andamento do projeto.

Interessante quando se trabalha com o git, depois do fork, ter dois remotes, um para o seu repositório e outro para o original, nesse caso teria um git remote add origin url_fork.git e outro, git remote add original url_original.git, para sempre manter atualizado. Agora para atualizar é necessário utilizar o nome do repositório corretamente no caso do pull, como git pull ORIGINAL master, que é o repositório onde se está fazendo fork.

Clonar:

Pegando um repositório que já existe, para fazer isso é necessário ir no repositório (Github) e obter a url e utilizar o comando git clone URL.git

Adicionar colaboradores:

Para adicionar outros usuários ao seu repositório é necessário no repositório,

Um projeto no Github pode ter diversos colaboradores. Para fazer isso, siga as instruções abaixo:

Abra a página do projeto no Github

Abra a aba Settings

Clique na seção Collaborators, à esquerda

Digite o usuário do colaborador no campo ao lado do botão Add collaborator. Durante a digitação, aparecerão os usuários mais próximos da busca atual.

Branch:

Branch - Ramo, uma separação da linha principal de desenvolvimento

Recomendo criar para desenvolver o códido em uma area especifíca do repositório e depois integrar no repositório principal, na linha de desenvolvimento principal, na master.

Referencia Git.

https://git-scm.com/book/pt-br/v1/Ramifica%C3%A7%C3%A3o-Branching-no-Git-O-que-%C3%A9-um-Branch

Para fazer que uma determinida pasta deixe de ser um repositório é só apagar a pasta .git

Conflitos:

Quando a mesma linha de um mesmo arquivo é alterada por dois desenvolvedores ao mesmo tempo, ocorre um conflito. Neste caso, é necessário que o desenvolvedor que for executar o merge decida como lidar com o conflito, seja escolhendo entre uma das alterações ou escolhendo a ordem em que as duas serão inseridas.

Chamamos esse processo de tratar as diferenças existentes no mesmo arquivo, gerados por diferentes commits, de merge.

Acontece quando se faz um pull <remote> <branch> e o git não consegue resolver automaticamento o conflito

Depois do pull seu arquivo terá anotações como essas:

Anotações do Git:

<<<<< HEAD

//Seu código como está no repositório local

==========

//Código do remote que gerou conflito

>>>>> hashcode

Para fazer o merge é necessário organizar o arquivo, na sua ide/text editor pois o git não oferece forma de fazer isso no terminal ou fora dele, e organizar da forma que deseja, depois disso é necessário um git add .,

indicando ao git que foi finalizado o merge e pode fazer um commit e push.

Lock: Travar um determinado arquivo para que só você possa edita-lo.

Lidando com conflitos, cada desenvolvedor ira trabalhar em uma branch

Merge:

>>>>>

git mergetool --tool-help : mostra no console uma lista de programas possíveis de ser utilizados. Dessa lista, pode-se escolher um, instalar no seu computador e utilizar através do comando git mergetool -t nome_do_programa.

=====

<<<<<

Aliases:

Criando comandos novos para digitar menos os comandos, fazendo isso no arquivo dentro do gitconfig

com

[alias]

st = status

co = checkout

isso dentro do arquivo.

Ferramentas gráficas, Git-Cola,

Desafio:

Problemas com o merge

PRÓXIMA ATIVIDADE

O processo de tratar conflitos é o mais crítico quando se trabalha com controle de versões e também um dos mais complicados de se compreender.

Se em nenhum momento você já precisou realizar o processo de merge quando trabalhou com controle de versões, imagine como seria o processo de corrigir os conflitos feitos por vários desenvolvedores.

Faça o teste! Crie um repositório local e acesse por duas abas diferentes do terminal, em duas branches diferentes. Faça diversas alterações em cada uma, jogue as alterações para a master e veja quais as dificuldades.

Dúvidas:

Como commitar o código de uma branch para outra ?

R: git merge branch - Estando na branch que se quer obter os dados de outra branch.

O que é gitflow ?

Estudar mais os estados do git: Working Directory, Index, HEAD!

Estudar o bisect, cherry pick!

Como ver as alterações de cada commit ?

git show <hash commit>

Estudar mais sobre o git rebase, git merge e o git fecth.

http://www.leandrosales.com.br/2012/09/05/git-merge-git-rebase-e-outras-funcionalidades-do-git/

Como saber quais os arquivos estão no add .(estado de Index)

Referencias:

Primeiros passos com o git:

https://imasters.com.br/desenvolvimento/os-primeiros-passos-com-git/?trace=1519021197&source

Como criar uma page github.io:

https://blog.paulagrangeiro.com.br/hospedando-sites-gratuitamente-com-o-github-pages-284aa643db14

> Written with [StackEdit](https://stackedit.io/).
