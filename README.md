# GitFlow usando a extensão de comandos Git 

A extensão Git é geralmente usada para estender os comandos básicos do Gitflow e não apenas uma estrutura de branchs.  O SCM, ou Sistema de Controle de Código Fonte (do inglês Source Code Management) usando em grandes projetos, diferete do artigo anterior sobre [GitHub Flow](https://github.com/lsmatias/githubflow) Flow, um modelo que aborda de maneira mais simples o controle de versão. O GitFlow é mais completo e supre complexidades em projetos de software maiores.

> [!NOTE]
> Git Flow é uma ferramenta que precisa ser instalada no seu sistema antes de ser utilizada. Certifique-se de ter o Git Flow instalado e configurado corretamente.

# Estrutura do GitFlow com Extensão Git


```
|-- master
|
|-- develop
|   \
|    \-- feature/...
|
|-- release/...
|
 \-- hotfix/...
```

<img width="584" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/f7e7a381-3ffb-45a9-bfc6-3b1a9bda23b1">


* **Master**: A branch master representa a versão mais estável do seu projeto. As releases estáveis são mescladas nesta branch.

* **Develop**: A branch develop é onde o desenvolvimento contínuo ocorre. As features são mescladas nesta branch quando estão prontas para serem testadas.

* **Feature**: Cada nova funcionalidade é desenvolvida em uma branch feature separada, derivada da branch develop.

* **Release**: Quando a branch develop atinge um ponto onde está pronta para ser lançada, uma branch release é criada. É aqui que as últimas correções de bugs podem ser aplicadas antes da release.

* **Hotfix**: Se bugs críticos são encontrados na branch master, uma branch hotfix é criada para corrigir esses problemas.

## :octocat: Inicialização do Git Flow

`git flow init`

Este comando inicializa o repositório para o uso do Git Flow e cria as branches principais (master e develop) e definido por você os padrões de branchs de feature e suporte conforme configuração questionadas no terminal com forme imagem abaixo:

<img width="927" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/6e936a6c-31d6-43da-8304-27817db1f241">

## Criar uma nova Feature

`git flow feature start nome-da-feature`

Este comando cria uma nova branch de **feature** baseada no branch **develop** para implementação de uma nova funcionalidade.

<img width="937" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/b3adbb21-a991-4e66-bf9b-5818eb2bfa85">

## Concluir uma Feature

`git flow feature finish nome-da-feature`

Este comando faz o merge (mescla) o branch de **feature** no branch **develop** e a exclui após a conclusão.

<img width="943" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/24cf48b4-efc3-4c9b-b900-922329ae2872">

Essa fase tem como objetivo garantir que a nova funcionalidade ou alteração atenda aos requisitos especificados e funcione corretamente antes de ser lançada para produção. Aqui estão alguns dos principais aspectos e atividades que geralmente ocorrem durante a validação de uma feature nesses ambientes:

<img width="423" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/0a6dee5f-4534-4402-baa3-0405d589f9f0">

> :mag_right: :shipit: Validação e Testes
> * Testes Funcionais
> * Testes de Integração
> * Testes de Desempenho
> * Testes de Segurança
> * Testes de Usabilidade
> * Testes de Regressão

# Nova Release :godmode: :rocket:

## Criar uma nova Release
`git flow release start 1.0.0`

<img width="569" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/2c64c26e-a532-4533-a701-50b185b86cdd">

## Concluir uma Release

`git flow release finish 1.0.0`

Este comando mescla a branch de release na branch develop e master, cria uma tag para a versão e a exclui após a conclusão.

<img width="588" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/9594a0ef-ae24-45e5-ab57-ad7894ed4826">

# Hotfix :rage1:

## Criar um novo Hotfix

`git flow hotfix start 1.0.1` 

Este comando cria uma nova branch de hotfix baseada na branch master para corrigir bugs críticos em uma versão de produção.

<img width="615" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/5d866ada-277e-48f9-ab4c-bea326b9928f">

## Concluir um Hotfix

Conclusão da hotfix (mescla na branch develop e master, cria tag)

`git flow hotfix finish 1.0.1`

Este comando mescla a branch de hotfix na branch develop e master, cria uma tag para a versão e a exclui após a conclusão.


> [!TIP]
> 
> ## Dica para cada etapa de desenvolvimento no git
> 
> Criação e troca para a branch develop
> 
> ```
> git checkout -b develop
>
> ```
> 
> Criação de uma nova feature
>
> ```
> git checkout -b feature/nova-feature develop
>```
> 
> Trabalho na nova feature e commit
> 
>```
> git commit -m "Implementação da nova feature
>```
> 
> Mesclagem da feature na branch develop
> 
> ```
> git checkout develop
> git merge --no-ff feature/nova-feature
> 
> ```
> Criação de uma release
>
> ```
> git checkout -b release/1.0.0 develop
>```
> Teste e correção de bugs se necessário
>
> ```
> git commit -m "Correção de bugs na release
> ```
>
> Mesclagem da release na branch develop e master
>
> ```
> git checkout develop
>
> git merge --no-ff release/1.0.0
>
> git checkout master
>
> git merge --no-ff release/1.0.0
> 
> ```
> Criação de uma hotfix para a branch master
>
> ```
> git checkout -b hotfix/1.0.1 master
>```
> Correção de bug crítico na hotfix
>```
> git commit -m "Correção de bug crítico
>```
> Mesclagem da hotfix na branch master e develop
>
> ```
> git checkout master
>
> git merge --no-ff hotfix/1.0.1
>
> git checkout develop
>
> git merge --no-ff hotfix/1.0.1
>```
> Lembrando que essa é uma simplificação e cada projeto pode ter variações na implementação do GitFlow.
# Fontes
[Tutorial Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

[Microsoft Learn Git Github](https://learn.microsoft.com/pt-br/training/modules/implement-code-workflow/)

[Edward Thomson | Release Flow](https://devblogs.microsoft.com/devops/release-flow-how-we-do-branching-on-the-vsts-team/)

[Leandro Matias | Gitflow](https://github.com/lsmatias/githubflow)



