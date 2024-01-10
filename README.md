# Gitflow
GitFlow o Modelo de SCM

O SCM (Source Code Management/Sistema de Controle de Versão) Git é um sistema de controle de versão distribuído amplamente utilizado para rastrear as mudanças em arquivos de código-fonte durante o desenvolvimento de software. Foi criado por Linus Torvalds em 2005 para o desenvolvimento do kernel do Linux e desde então se tornou uma das ferramentas mais populares para controle de versão.

## Estrura de Branchs
* **Main Branch:** Este branch é usado para refletir a versão mais recente do software que está em produção. Cada commit nesse branch deve representar uma versão estável e testada do código.

* **Develop Branch:** O branch de desenvolvimento onde todo o trabalho em andamento é consolidado. Os branches de feature são mesclados neste branch assim que estiverem prontos para serem testados em conjunto.

* **Feature Branches:** Branches criados a partir do branch `develop` para desenvolver novas funcionalidades. Cada funcionalidade é desenvolvida em seu próprio branch e, quando concluída, é mesclada de volta no branch `develop`.

* **Release Branches:** Ramificações preparadas para liberar uma versão específica do software. Esses branches são criados a partir do `develop` quando todas as funcionalidades planejadas para a próxima versão estão concluídas. Geralmente são usados para correções finais de bugs, testes e preparação para a versão final.

* **Hotfix Branches:** Branches criados a partir do `main` para corrigir problemas críticos em produção rapidamente. Estes branches visam corrigir bugs urgentes sem interferir no desenvolvimento regular do `develop`.


