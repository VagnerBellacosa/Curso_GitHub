# 20 dicas poderosas de Git e Github para organizar sua vida

GUILHERME MAIO 21, 2020 [BACK-END](https://blog.dankicode.com/category/programacao/back-end/), [FRONT-END](https://blog.dankicode.com/category/programacao/front-end/), [FULL-STACK](https://blog.dankicode.com/category/programacao/full-stack/), [PROGRAMAÇÃO](https://blog.dankicode.com/category/programacao/)

![20 dicas poderosas de Git e Github para organizar sua vida](https://blog.dankicode.com/wp-content/uploads/2020/05/dicas-de-git-e-github.jpg)

- 
-  

- 
-  

- 
-  

- 
-  

- 

TEMPO DE LEITURA: 7 MINUTOS

Olá dev, tudo bem com você? Se não está vai ficar, pois com as dicas de git e github que vou te passar nesse artigo você será capaz de organizar muito bem sua vida de programador.

E se tratando de programação, organização é um fator crucial para você continuar evoluindo em seu projeto, e nada melhor que o Git + Github para nos ajudar nesse processo.

Se você ainda não tem familiaridade sobre Git e Github lhe convido a acessar o nosso [guia introdutório de Git e Github clicando aqui](https://blog.dankicode.com/introducao-ao-git-e-github/), pois lá nós vamos lhe dar o passo a passo para você começar a utilizar a ferramenta da melhor forma possível.

Tudo pronto para aprender as dicas de git e github?

[// 1. Você sabe a diferença entre git e GitHub?](https://blog.dankicode.com/dicas-de-git-e-github/#git-github)

[// 2. Como saber o que você fez?](https://blog.dankicode.com/dicas-de-git-e-github/#saber)

[// 3. Como adicionar mais algum arquivo depois de ter dado commit?](https://blog.dankicode.com/dicas-de-git-e-github/#adicionar)

[// 4. Criei vários commit, mas não quero mais, e também não quero perder as mudanças feitas](https://blog.dankicode.com/dicas-de-git-e-github/#varios-commit)

[// 5. Como apagar tudo (commits e mudanças) que fiz e deixar minha branch igual a um commit específico ou branch?](https://blog.dankicode.com/dicas-de-git-e-github/#apagar)

[// 6. Como commitar só uma parte das mudanças sendo que mexi em vários arquivos?](https://blog.dankicode.com/dicas-de-git-e-github/#commitar)

[// 7. Como ver o diff inteiro de código do que foi feito nos últimos commits?](https://blog.dankicode.com/dicas-de-git-e-github/#diff)

[// 8. Como não subir arquivos indesejados em um projeto novo?](https://blog.dankicode.com/dicas-de-git-e-github/#subir)

[// 9. Como fechar uma issue automaticamente?](https://blog.dankicode.com/dicas-de-git-e-github/#issue)

[// 10. Se você usa o VS Code, recomendo fortemente o plugin Git Lens](https://blog.dankicode.com/dicas-de-git-e-github/#vs-code)

[// 11. Como acompanhar o fork de um projeto?](https://blog.dankicode.com/dicas-de-git-e-github/#fork)

[// 12. Como não correr o risco de perder o que já foi feito mesmo que você ainda não tenha concluído?](https://blog.dankicode.com/dicas-de-git-e-github/#perder)

[// 13. Escreva mensagens de commit concisas e específicas.](https://blog.dankicode.com/dicas-de-git-e-github/#escreva)

[// 14. Quanto mais commits melhor](https://blog.dankicode.com/dicas-de-git-e-github/#mais-commits)

[// 15. Mais sobre WIP: essa dica irá servir quando você estiver numa branch separada](https://blog.dankicode.com/dicas-de-git-e-github/#wip)

[// 16. Como fazer alguma modificação em um commit do passado que não seja o último?](https://blog.dankicode.com/dicas-de-git-e-github/#modifica)

[// 17. Criou uma branch com o nome errado e só percebeu depois, na hora de dar push?](https://blog.dankicode.com/dicas-de-git-e-github/#branch)

[// 18. Tem dificuldade com vim ou outro editor de linha de comando?](https://blog.dankicode.com/dicas-de-git-e-github/#dificuldade)

[// 19. É entediante ter de adicionar arquivo por arquivo?](https://blog.dankicode.com/dicas-de-git-e-github/#arquivo)

[// 20. Use git stash pra guardar temporariamente os arquivos modificados que ainda não foram commitados](https://blog.dankicode.com/dicas-de-git-e-github/#git-stash)



## 1. Você sabe a diferença entre git e GitHub?

Git é o software de controle de versão, GitHub é uma plataforma para hospedar projetos que usam git. Fora o GitHub existem outras soluções como BitBucket e GitLab, e por ser open source você pode ter seu próprio servidor de git.



## 2. Como saber o que você fez?

```
git reflog
```

Esse comando fornecerá um histórico completo do que você fez.



## 3. Como adicionar mais algum arquivo depois de ter dado commit?

```
1) git add
2) git commit --amend
```

O amend irá modificar o commit anterior, então você pode utilizá-lo para remover arquivos do commit, mudar a mensagem, trocar autor, ou seja, fazer o que quiser!



## 4. Criei vários commit, mas não quero mais, e também não quero perder as mudanças feitas:

git reset –soft

As mudanças estarão staged, prontas para serem commitadas novamente.



## 5. Como apagar tudo (commits e mudanças) que fiz e deixar minha branch igual a um commit específico ou branch?

git reset –hard

Para deixar igual a uma branch remota, o comando é: git reset –hard origin/branch



## 6. Como commitar só uma parte das mudanças sendo que mexi em vários arquivos?

git add -p

Você irá ver parte por parte do que modificou e uma pergunta sobre o que deseja colocar em stage



## 7. Como ver o diff inteiro de código do que foi feito nos últimos commits?

git log -p



## 8. Como não subir arquivos indesejados em um projeto novo?

Basta configurar o arquivo .gitignore. Será mais fácil se você fizer isso no início do projeto ao invés de ter que remover depois.

Vou deixar abaixo uma lista de templates para você copiar:

github/gitignore – A collection of useful .gitignore templates. Contribute to github/gitignore development by creating an account on GitHub.



## 9. Como fechar uma issue automaticamente?

No GitHub, escreva na mensagem do commit “closed”, “closes”, “close”, “fixed” ou “fixes” seguido de hashtag + número da issue (exemplo: “Fixes #1234”) , a issue será fechada imediatamente.



## 10. Se você usa o VS Code, recomendo fortemente o plugin Git Lens.

Ele irá te mostrar de forma visual todo o histórico de commits do arquivo, quem fez e quando foi feito, muito útil:

[GitLens — Git supercharged – Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)



## 11. Como acompanhar o fork de um projeto?

```
git remote add <https://url-do-fork.git>
```

Para ver todos os remotes do repo que você tem localmente:

```
git remote -v
```

Para usar, é só trocar origin pelo nome que você deu ao remote:

```
git pull , git checkout nome-fork/branch…
```



## 12. Como não correr o risco de perder o que já foi feito mesmo que você ainda não tenha concluído?

Basta você commitar e adicionar na mensagem “WIP” antes, que significa Work in Progress.

Quando estiver tudo pronto é só dar commit –amend e tirar o WIP da mensagem.



## 13. Escreva mensagens de commit concisas e específicas.

Quanto mais detalhada for a descrição do commit, melhor será futuramente, principalmente se seu código não for muito comentado.



## 14. Quanto mais commits melhor.

A função funcionou? commita. O teste passou? commita.

Essa tática vai te ajudar bastante no futuro caso precise desfazer algo, buscar bugs ou reaproveitar seu código.

Mesmo que ainda não esteja 100%, commita com “WIP” na frente.



## 15. Mais sobre WIP: essa dica irá servir quando você estiver numa branch separada.

Se tiver trabalhando com alguém na mesma branch, é bom avisar para não correr o risco de mandar código quebrado pro seu parceiro.

Evite mandar WIP pra master, já que devemos sempre evitar modificar o passado dessa branch



## 16. Como fazer alguma modificação em um commit do passado que não seja o último?

Por exemplo para tirar um commit WIP, usamos o git rebase -i, que é o rebase interativo.



## 17. Criou uma branch com o nome errado e só percebeu depois, na hora de dar push?

Calma, não é o fim:

```
git branch -m nome-velho nome-novo
```



## 18. Tem dificuldade com vim ou outro editor de linha de comando?

Você pode muito bem trocar o editor padrão que o git usa para escrever as mensagens de commit ou resolver conflitos:

```
git config --global core.editor "seu-editor"
```



## 19. É entediante ter de adicionar arquivo por arquivo?

Ao invés de dar *git add .* e vez ou outra subir o que não deve, use git add -u que ele vai adicionar só os arquivos que já foram trackeados pelo git. Ou seja, nunca use git add .



## 20. Use git stash pra guardar temporariamente os arquivos modificados que ainda não foram commitados.

Útil quando precisa trocar de branch, por ex: testar o código sem suas mudanças, ou testar em outra branch. Pra “pegar” as mudanças de volta git stash pop.

### Deseja saber mais sobre como usar o Git e o GitHub, confira os recursos nos seguintes links:

[git-scm.com](https://git-scm.com/) – O site principal e a documentação do Git

[help.github.com](https://help.github.com/) – Documentação de ajuda do GitHub

## Conclusão das dicas de Git e Github

![desenvolva projetos](https://blog.dankicode.com/wp-content/uploads/2020/05/desenvolva-projetos.png)

Gostou das dicas de Git e Github? Esse é só o começo!

E se você pudesse aprender mais e mais sobre [desenvolvimento](https://programadoresdepre.com.br/) Web e se aprofundar nas mais incríveis tecnologias do mercado?

**Conheça o Pacote Full Stack que já mudou a vida de milhares de pessoas e pode mudar a sua também!**

**[>> Acesse aqui o Pacote Full-Stack e entenda o motivo de nosso treinamento ser o mais requisitado do país.](https://pacotefullstack.com/completo/)**