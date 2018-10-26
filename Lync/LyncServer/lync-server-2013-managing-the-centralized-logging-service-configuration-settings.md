---
title: "Gest. des par. de conf. du serv. de journ. centralisée à l’aide de PowerShell"
TOCtitle: "Gest. des par. de conf. du serv. de journ. centralisée à l’aide de PowerShell"
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49891615
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des paramètres de configuration du service de journalisation centralisée à l’aide de PowerShell

 

_**Dernière rubrique modifiée :** 2012-11-01_

Le service de journalisation centralisée est contrôlé et configuré par des paramètres créés et utilisés par le contrôleur service de journalisation centralisée (CLSController) pour envoyer des commandes à l’agent service de journalisation centralisée (CLSAgent) de l’ordinateur. L’agent traite les commandes qui lui sont envoyées et (dans le cas d’une commande de démarrage) utilise la configuration des scénarios, fournisseurs, tailles de journaux, durées des suivis et indicateurs pour commencer la collecter des journaux de suivi selon les informations de configuration fournies.

> [!IMPORTANT]  
> Toutes les cmdlets Windows PowerShell répertoriées pour le service de journalisation centralisée ne sont pas conçues pour être utilisées avec des déploiements de Lync Server 2013 sur sites. Bien qu’elle peuvent sembler fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec les déploiements Lync Server 2013 sur sites :
> <ul>
> <li><p><strong>Cmdlets CsClsRegion :</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsRegion">Get-CsClsRegion</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsRegion">Set-CsClsRegion</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsRegion">New-CsClsRegion</a>, et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsRegion">Remove-CsClsRegion</a>.</p></li>
> <li><p><strong>Cmdlets CsClsSearchTerm :</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSearchTerm">Get-CsClsSearchTerm</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSearchTerm">Set-CsClsSearchTerm</a>.</p></li>
> <li><p><strong>Cmdlets CsClsSecurityGroup :</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSecurityGroup">Get-CsClsSecurityGroup</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSecurityGroup">Set-CsClsSecurityGroup</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsSecurityGroup">New-CsClsSecurityGroup</a>, et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsSecurityGroup">Remove-CsClsSecurityGroup</a>.</p></li></ul>
> Les paramètres définis dans ces cmdlets n’entravera le comportement ou ne provoquera pas de comportement négatif, mais ils sont conçus pour être utilisés avec Microsoft Office 365 et ne rendrons pas les résultats prévus lors de déploiements sur sites. Nous n’affirmons pas que ces cmdlets sont inutiles pour les déploiements sur sites, mais leur utilisation nécessite la consultation d’une rubrique plus détaillée, que cette documentation ne contient pas.


## Dans cette section

Les rubriques de cette section définissent les options de configuration et les paramètres pour le service de journalisation centralisée. Les rubriques suivantes contiennent des informations sur la méthode de configuration de service de journalisation centralisée, la récupération des paramètres de configuration, la création de scénario, la gestion des groupes de sécurité pour service de journalisation centralisée, la recherche et d’autres types d’informations.

  - [Gestion de la configuration du service de journalisation centralisée au niveau d’un ordinateur, d’un site ou au niveau global](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configuration des fournisseurs pour le service de journalisation centralisée](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configuration des scénarios pour le service de journalisation centralisée](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

## Voir aussi

#### Concepts

[Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Applets de commande pour la journalisation centralisée](https://docs.microsoft.com/en-us/powershell/module/skype/)

