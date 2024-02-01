# GitFlow usando a extensão de comando git

A extensão Git é geralmente usada para estender os comandos básicos do Gitflow e não apenas uma estrutura de branchs.  O SCM, ou Sistema de Controle de Código Fonte (do inglês Source Code Management) usando em grandes projetos, diferete do artigo anterior sobre [GitHub Flow](https://github.com/lsmatias/githubflow) Flow, um modelo mais simples de controle de versão. O GitFlow é mais completo e supre complexidades em projetos de software maiores.

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

## Inicialização do Git Flow

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

# Nova Release

## Criar uma nova Release
`git flow release start 1.0.0`

<img width="569" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/2c64c26e-a532-4533-a701-50b185b86cdd">

## Concluir uma Release

`git flow release finish 1.0.0`

Este comando mescla a branch de release na branch develop e master, cria uma tag para a versão e a exclui após a conclusão.

<img width="588" alt="image" src="https://github.com/lsmatias/gitflow/assets/28391885/9594a0ef-ae24-45e5-ab57-ad7894ed4826">

# Hotfix




