# GITHub

Comandos e anotações sobre o git

## Git - Tipos de Controle de Versão:

### Sistemas Locais:

Disponível somente na minha maquina

- Pontos negativos

Difícil de trabalhar com colaboradores (Outros devs) caso o disco rígido for corrompido você perde tudo

### Sistemas Centralizados:

Ele fica em um único servidor

- Ponto positivo

Controle sobre as atividades dos colaboradores

- Pontos negativos

Caso o servidor saia do ar neste período ninguém pode trabalhar, se o disco rígido do banco de dados for corrompido você pode perder tudo

### Sistemas Distribuídos:

- Git, Mercurial, Bazaar

Duplicar ( Clonar ) localmente o repositório completo
Varias copias do mesmo projeto
vários devs colaborando no mesmo projeto
rede social na mesma plataforma

## O que é o Git

Sistema de controle de versão distribuído e Open-source.

Pontos na historia (Commit)

- Historia de alteração do código
- Voltar para qualquer ponto da historia(commit) 

Controla o fluxo de novas funcionalidades

- Ramificação branch (Universos paralelos)
- Vários devs no mesmo projeto
- analise e resolução de conflitos

### Configurações iniciais:

obs: Todos estes comandos tem quer ser executados no terminal do git

•	usuário

> git config --global user.name "Seu nome de usuario do github"

Se for preciso colocar um nome diferente para um projeto especifico é só colocar o comando sem a opção - -global

•	e-mail
>git config --global user.email meu_email@gmail.com
  o mesmo e-mail cadastrado no github para não ocasionar problemas.

comando para listar as configurações:  
>git config --list

Git Help:
é um comando que lista todos os comandos existentes no git
>git help

Iniciando um repositório:
no terminal acesse a pasta desejada.
exemplo
acessar pasta
>cd /Desktop/GitAula/

Iniciar um Repositório dentro do nosso projeto
>git init
Resposta esperada : Initialized empty Git repository in C:/Users/lari/Desktop/GitAula/.git/

Commit:
Um ponto na historia

preparando os arquivos para fazer o commit
>git add .
 o . significa todos os arquivos que eu tenho no meu diretório local

ou... adicionar um arquivo em especifico

>git add meu_arquivo.txt

fazer o commit
>git commit -m "initial commit"

Git Log:
Com este comando é possível saber todos os pontos da historia ou seja todos os commits
>git log 

ou...
>git log --oneline 

Git Workflow / Fluxo de trabalho do git

>1 - woking diretory /Working Tree
Onde esta todos os nossos arquivos recentes
•	exemplo: eu tenho um novo arquivo na minha pasta chamado exemplo.txt
•	usamos o comando git add . ou o comando git add *
•	Agora o arquivo foi para a stage area

2- Stage Area/Index/stage tree
onde é preparado os arquivos para fazer o commit
•	agora o nosso arquivo exemplo.txt está aqui
•	usamos o comando git commit -m "Nosso primeiro commit"
•	Pronto! foi feito o commit
•	o nosso arquivo foi para o local repository

3- Local Repository
onde esta os nossos pontos na historia(commits)
•	Use o comando git log para ver todos os commits

Obs: PARA SABER MELHOR EM QUAL ETAPA ESTAMOS É SO USAR O COMANDO 

>git status

### Hash Sha-1

Hash sha-1 é o valor dado como nome para cada commit
à cada commit é feito um checksum - converter os dados em números
•	São 40 caracteres
•	vão de A a F
•	Vão de 0 a 9
•	São valores hexadecimais

Dentro deste hash sha-1
•	Snapshot - ou seja uma fotografia de como o meu projeto estava naquele momento

Está fotografia é gerada com dados adicionais como
•	autor do projeto
•	mensagem do commit
•	se ele tem parente ou não (casso seja o primeiro commit ele não tem pai logo o valor é null)
•	o segundo commit tem parente e esse numero de parente é o hash do commit anterior
cada hash é único porem contém os dados das alterações anteriores

Head 

Ele aponta para em que ponto da historia nos estamos(o commit mais recente ).

•	Head significa ponteiro ou seja ele aponta para algum lugar
•	Ele aponta para qual commit estamos

Se ele aponta para Master/Main
•	Significa que estamos na nossa branch principal ou seja na nossa linha do tempo principal o último commit

Git remove
remover um arquivo do working diretory
git rm nome_do_arquivo
você também pode remover manualmente

Mover Arquivos
Mover um arquivo de uma pasta para a outra
>git mv nome_do_arquivo_que_vai_ser_movido.txt pasta/qual_vai_ser_o_nome_do_arquivo_nesta_pasta.txt

Desfazendo Modificações
Descartar alterações
>git restore nome_do_arquivo

Trazendo de volta do staged area
Tirando um arquivo especifico do staged area
>git restore --staged nome_do_arquivo.txt

Tirando todos os arquivos do staged area
>git restore --staged .

Revertendo um commit
Para ser usado o working tree ou seja o git status tem que estar limpo
voltando para um ponto da historia(commit)

-voltar para o commit -1
>git revert HEAD~1

-Voltar para o commit que tem uma hash especifica
>git revert 79790b3

obs1: para pegar a hash é so usar git log --oneline e escolher commit e copiar a hash dele
obs2: a head vai apontar para este commit

Comando git

--- dir ----- Comando para listar, mostrar as pastas
--- cd ---- Comando para entrar em alguma pasta, põem o cd logo em seguida nome da pasta ex: cd windons , cd users.
--- cd .. --- esse comando ele volta uma pasta.
--- cd / --- Esse comando retorna para a raiz.
--- cls --- comando para limpar o terminal a tela.
--- Tab --- depois de dar o comando cd colocar a inicial de uma pasta e aperta Tab ela auto completa sem precisar escrever o nome todo da pasta
--- mkdir ---- comando para criar uma pasta dar este comando logo em seguida põem o nome da pasta que deseja ser criada.
--- echo-- comando para printar algo na tela, dar echo logo em seguida escreve o que desejar que e dar enter para aparecer na tela
--- echo > nomeTexto.txt --- para criar um arquivo, nesse caso foi criado um arquivo de tipo txt.
--- del --- comando para deletar algo no caso colocar o comando del depois o nome da pasta ou arquivo para ser deletado, este comando deleta só os arquivos, mantendo as pastas.
--- rmdir --- comando para deletar a pasta e tudo dento dela, ou seja rmdir nomeDaPasta /S /Q enter, fazendo isso a pasta será deletada.
--- openssl sha1 nomeDoArquivo.txt --- Este comando sha1 ele é uma parte que encriptografa o codigo em uma string de 40 caracteres, é o que o git usa para identificar se a versão do código foi alterada ou não, toda vez que o código muda este valor tb muda, se o código voltar para como estava o valor do sha1 tb volta para onde estava dessa forma mantem o versionamento do código.
--- ls -a --- mostra arquivos ocultos dentro das pastas no guit bash
----------------------------------------

configurações iniciais do git bash:

>git config --global user.email "Poem seu email aqui" --- 
>git config --global user.name "poem seu nome aqui"
>git init --- inicia uma pasta do git vazia com tudo que ele vai precisar, criando o repositório
>git add * ou git add . --- adiciona os arquivos modificados a pasta do git
>git commit -m"escreve o que desejar" --- junta os arquivos e põem nele um comentário que desejar
>git config --list --- traz toda configuração do seu git
>git config --global --unset user.email --- para retirar o nome de e-mail que esta atrelado ao git
>git config --global --unset user.name
>git remote add origin https:///github.com/... --- aqui vc cria um caminho da sua maquina para o seu guit passando a chave https que esa no servidor do 
>git clone https:///github.com/... -- aqui vc vai clonar o repositório da origin para a sua maquina
>git remote -v --- mostrar as lista de que tenho cadastrado, vai mostrar a origin que a pasta esta apontando do github
>git push origin master --- vai fazer o push para a master ou seja o que esta no seu computador vai para a origin
>git pull origin master --- esse comando vai pegar as coisas que estão na origin pra a sua maquina

Recentemente tenho observado uma série de perguntas nos fóruns com relação ao seguinte comando:

>git push origin master

Ao entrar com esse comando, o terminal não devolve o controle ao usuário, forçando-o a interromper o processo.

Uma das soluções é entrar com o seguinte comando:

>git config --global credential.provider generic

...e prosseguir com o 'push' normalmente.

Para maiores informações, confiram a seguinte publicação:

>git-credential-manager-core hangs on get · Issue #364 · microsoft/Git-Credential-Manager-Core (github.com)
