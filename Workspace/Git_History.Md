# Git

#GitHub indice

[Saber a história do Git](#History)
[Como configurar o Git e seus comandos básicos](#Comandos)
[Como trabalhar com diferentes branches num projeto](#Branches)
[Como trabalhar com repositórios remotos no Github](#Repositorios)


#History

Uma Breve História do Git
Como muitas coisas na vida, o Git começou com um pouco de destruição criativa e uma ardente controvérsia.

O núcleo (kernel) do Linux é um projeto de código aberto com um escopo bastante grande. A maior parte da vida da manutenção do núcleo o Linux (1991-2002), as mudanças no código eram compartilhadas como correções e arquivos. Em 2002, o projeto do núcleo do Linux começou usar uma DVCS proprietária chamada BitKeeper.

Em 2005, a relação entre a comunidade que desenvolveu o núcleo do Linux e a empresa que desenvolveu BitKeeper quebrou em pedaços, e a ferramenta passou a ser paga. Isto alertou a comunidade que desenvolvia o Linux (e especialmente Linux Torvalds, o criador do Linux) a desenvolver a sua própria ferramenta baseada em lições aprendidas ao usar o BitKeeper. Algumas metas do novo sistema era os seguintes:

- Velocidade

- Projeto simples

- Forte suporte para desenvolvimento não-linear (milhares de ramos paralelos)

- Completamente distribuído

Capaz de lidar com projetos grandes como o núcleo o Linux com eficiência (velocidade e tamanho dos dados)

Desde seu nascimento em 2005, Git evoluiu e amadureceu para ser fácil de usar e ainda reter essas qualidades iniciais. Ele é incrivelmente rápido, é muito eficiente com projetos grandes, e ele tem um incrível sistema de ramos para desenvolvimento não linear (Veja [ch03-git-branching]).

#Comandos


Setar usuário

...
git config --global user.name "Leonardo Comelli"
...

Setar email

...
git config --global user.email leonardo@software-ltda.com.br
...

Setar editor

...
git config --global core.editor vim
...

Setar ferramenta de merge

...
git config --global merge.tool vimdiff
...

Setar arquivos a serem ignorados

...
git config --global core.excludesfile ~/.gitignore
...

Listar configurações

...
git config --list
...

## Repositório Local
Criar novo repositório
...
git init
...
Verificar estado dos arquivos/diretórios
...
git status
...
## Adicionar arquivo/diretório (staged area)
Adicionar um arquivo em específico
...
git add meu_arquivo.txt
...
Adicionar um diretório em específico
...
git add meu_diretorio
...
Adicionar todos os arquivos/diretórios
...
git add .	
...
Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)
...
git add -f arquivo_no_gitignore.txt
...
## Comitar arquivo/diretório
Comitar um arquivo
...
git commit meu_arquivo.txt
...
Comitar vários arquivos
...
git commit meu_arquivo.txt meu_outro_arquivo.txt
...
Comitar informando mensagem
...
git commit meuarquivo.txt -m "minha mensagem de commit"
...
## Remover arquivo/diretório
Remover arquivo
...
git rm meu_arquivo.txt
...
Remover diretório
...
git rm -r diretorio
...
## Visualizar histórico
Exibir histórico
...
git log
...
Exibir histórico com diff das duas últimas alterações
...
git log -p -2
...
Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))
...
git log --stat
...
Exibir informações resumidas em uma linha (hash completa e comentário)
...
git log --pretty=oneline
...
Exibir histórico com formatação específica (hash abreviada, autor, data e comentário)
...
git log --pretty=format:"%h - %an, %ar : %s"
...

#Branches

O master é o branch principal do GIT.

O HEAD é um ponteiro especial que indica qual é o branch atual. Por padrão, o HEAD aponta para o branch principal, o master.

Criando um novo branch
...
git branch bug-123
...
Trocando para um branch existente
...
git checkout bug-123
...
Neste caso, o ponteiro principal HEAD esta apontando para o branch chamado bug-123.

Criar um novo branch e trocar
...
git checkout -b bug-456
...

Voltar para o branch principal (master)
...
git checkout master
...
Resolver merge entre os branches
...
git merge bug-123
...
Para realizar o merge, é necessário estar no branch que deverá receber as alterações. O merge pode automático ou manual. O merge automático será feito em arquivos textos que não sofreram alterações nas mesmas linhas, já o merge manual será feito em arquivos textos que sofreram alterações nas mesmas linhas.

A mensagem indicando um merge manual será:
...
Automerging meu_arquivo.txt
CONFLICT (content): Merge conflict in meu_arquivo.txt
Automatic merge failed; fix conflicts and then commit the result.
...

Apagando um branch
...
git branch -d bug-123
...
## Listar branches

Listar branches
...
git branch
...
Listar branches com informações dos últimos commits
...
git branch -v
...
Listar branches que já foram fundidos (merged) com o master
...
git branch --merged
...
Listar branches que não foram fundidos (merged) com o master
...
git branch --no-merged
...
## Criando branches no repositório remoto

Criando um branch remoto com o mesmo nome
...
git push origin bug-123
...
Criando um branch remoto com nome diferente
...
git push origin bug-123:new-branch
...
Baixar um branch remoto para edição
...
git checkout -b bug-123 origin/bug-123
...
Apagar branch remoto
...
git push origin:bug-123
...

#Repositorios

Obtendo um Repositório Git
Tu normalmente obtens um repositório Git de duas maneiras:

Tu podes pegar num diretório local que atualmente não está sob controle da versão, e transformá-lo num repositório Git, ou

Tu podes clonas um repositório Git existente em qualquer outro local.

Em ambos os casos, acabas com um repositório Git na tua máquina local, pronto para o trabalho.

Inicializando um Repositório num Diretório Existente
Se tens um diretório de projeto que atualmente não está sob o controle da versão e desejas começar a controlá-lo com o Git, primeiro precisas de ir para o diretório deste projeto Se nunca fizeste isto, parece um pouco diferente, dependendo do sistema que tu estás a executar:

- para o Windows:

...
$ cd /c/user/my_project
...
e digita:
...
$ git init
...
Isto cria um novo subdiretório chamado .git que contém todos os teus arquivos de repositório necessários — um esqueleto de depósito Git. Neste ponto, nada no teu projeto ainda é rastreado. (Vê Internos do Git para obter mais informações sobre quais os arquivos que exatamente se encontram contidos no diretório .git que tu acabaste de criar.)

Se tu quiseres iniciar a versão - controlando os arquivos existentes (em oposição a um diretório vazio), provavelmente tu deverás começar a rastrear estes arquivos e fazer um commit inicial. Podes conseguir isto com alguns comandos git add que especificam os arquivos que desejas acompanhar, seguidos de git commit:
...
$ git add *.c
$ git add LICENSE
$ git commit -m 'initial project version'
...
Examinaremos o que estes comandos fazem em apenas um minuto. Neste ponto, tens um repositório Git com arquivos rastreados e um commit inicial.

### Clonar um Repositório Existente

Se tu quiseres obter uma cópia de um repositório Git existente - por exemplo, um projeto ao qual tu gostarias de contribuir - o comando que precisas é git clone. Se tu estiveres familiarizado com outros sistemas VCS, como o Subversion, notarás que o comando é o "clone" e não o "checkout". Esta é uma distinção importante — em vez de obteres apenas uma cópia de trabalho, o Git recebe uma cópia completa de quase todos os dados que o servidor possui. A versão muito completa de cada arquivo para o histórico do projeto é puxada para baixo por padrão quando executas o `clipe git '. De fato, se o teu disco do servidor estiver corrompido, podes usar quase qualquer um dos clones em qualquer cliente para configurar o servidor de volta ao estado em que se encontrava quando foi clonado (podes perder alguns ganchos do lado do servidor e tal, mas Todos os dados versionados estarão lá — vê Getting Git on a Server para mais detalhes).

Tu clonas um repositório com git clone <url>. Por exemplo, se tu quiseres clonar a biblioteca Git vinculável chamada libgit2, podes fazê-lo assim:
...
$ git clone https://github.com/libgit2/libgit2
...
Isto cria um diretório chamado libgit2, inicializa um diretório '.git` dentro dele, retira todos os dados deste repositório e verifica uma cópia de trabalho da versão mais recente. Se tu entrares no novo diretório libgit2 que acabou de ser criado, verás os arquivos do projeto lá, prontos para serem trabalhados ou usados.

Se tu quiseres clonar o repositório num diretório chamado algo diferente de libgit2, podes especificar isto como a próxima opção da linha de comando:

...
$ git clone https://github.com/libgit2/libgit2 mylibgit
...
Este comando faz o mesmo que o anterior, mas o diretório de destino é chamado mylibgit.

O Git possui vários protocolos de transferência diferentes que tu podes usar. O exemplo anterior usa o protocolo https://, mas tu também podes ver git:// ou user@server:path/to/repo.git, que usa o protocolo de transferência SSH. Getting Git on a Server apresentará todas as opções disponíveis que o servidor pode configurar para aceder ao teu repositório Git e os prós e contras de cada um.

