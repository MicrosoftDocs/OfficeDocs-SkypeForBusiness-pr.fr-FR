---
title: 'Lync Server 2013 : administration du système'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f128196f1d541e8a7f8ffd3b48bac8f34de85b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Administration système dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-18_

L’administration du système comprend les tâches d’administration quotidiennes, planifiées et à la demande, qui sont requises pour maintenir un système informatique sans problème. En règle générale, les tâches d’administration du système sont traitées par des procédures écrites. Ces procédures permettent de s’assurer que les mêmes outils et méthodes standard sont utilisés par tous les employés du support technique.

Dans un environnement Lync, les tâches d’administration système classiques incluent la sauvegarde et l’archivage des pools, la surveillance des journaux, la création et la gestion des utilisateurs, ainsi que la mise à jour d’un logiciel antivirus.

<div>

## <a name="system-troubleshooting"></a>Dépannage du système

Une organisation doit être prête à traiter des problèmes inattendus et doit disposer d’une procédure pour gérer les problèmes à partir du point auquel ils sont signalés jusqu’à leur résolution. Informations sur la façon dont le personnel de support a diagnostiqué un problème doit être enregistré et utilisé à l’avenir pour éviter un travail terminé inutilement répétitif.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Processus de résolution des problèmes système

Le diagramme suivant illustre le processus de résolution des problèmes et les interactions avec les autres rôles d’opération.

**Organigramme de résolution des problèmes système**

![Organigramme de résolution des problèmes système](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Organigramme de résolution des problèmes système")

  - **Classer et**   classer par ordre de priorité cette tâche est généralement effectuée par le service d’assistance. Par exemple, un problème peut être regroupé sous la forme d’un problème logiciel ou d’un problème matériel. Le problème est ensuite acheminé vers l’équipe de support appropriée pour l’enquête. Les règles permettant de déterminer la priorité d’un problème, ainsi que le temps de réponse et le temps à résoudre, sont généralement définies dans le contrat SLA.

  - **Examinez et diagnostiquez**   l’équipe de support technique appropriée pour diagnostiquer le problème et propose des modifications pour résoudre le problème. Si la solution est simple et ne nécessite pas de contrôle des modifications, la solution peut être appliquée immédiatement. Si la solution n’est pas facile, une demande de modification doit être générée et le travail proposé doit être géré par le processus de gestion des modifications, souvent sous la forme d’une procédure « Fast-Track ». Les modifications apportées doivent être enregistrées à l’aide du processus de gestion de la configuration.

  - **Fermer et enregistrer**   après avoir testé la résolution, le problème doit être fermé. S’il existe des leçons à apprendre à partir du problème, une entrée doit être créée dans la base de connaissances.

  - **Examen et analyse**   des tendances les révisions périodiques des problèmes récents doivent être effectuées pour identifier les tendances des problèmes. Par exemple, si les utilisateurs rencontrent des problèmes fréquents avec des connexions lentes sur leurs sites Lync, les problèmes de bande passante réseau peuvent être à l’origine du problème. Les temps de résolution des problèmes et l’effet de toutes les pannes de disponibilité du système doivent être examinés et comparés avec le contrat SLA. La personne qui assure la communication avec le client sur les problèmes de service, comme un responsable de compte, doit être informée des problèmes importants.

</div>

<div>

## <a name="issue-management-tools"></a>Outils de gestion des problèmes

Les outils du service d’assistance permettent aux employés d’enregistrer, de classer et de classer par priorité les nouveaux problèmes. Les outils fournissent ensuite les processus de flux de travail pour gérer la demande de service de problème par le biais d’une enquête et d’un diagnostic, souvent par plusieurs équipes de support technique. Les outils, qui fournissent fréquemment des rapports sur les temps de résolution et les tendances historiques, peuvent également inclure une base de données de la base de connaissances, qui peut être utilisée pour effectuer des recherches dans les problèmes précédents.

La base de connaissances Microsoft est un enregistrement utile des problèmes de support rencontrés par Microsoft. Pour plus d’informations, consultez le site Web du<https://go.microsoft.com/fwlink/?linkid=14898>support Microsoft ().

Les logiciels tiers nécessitent généralement une personnalisation pour répondre aux besoins de l’organisation, tels que l’Organisation des équipes, les exigences en matière de création de rapports et les mesures requises par le contrat SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Administration centralisée et administration décentralisée

Les rôles et les responsabilités liés à l’exécution de tâches d’administration système varient selon que l’organisation suit ou non un modèle centralisé, un modèle décentralisé ou une combinaison des deux.

  - **Modèle centralisé dans**   un modèle centralisé, un ou plusieurs groupes d’administration conservent un contrôle total de l’ensemble de l’environnement Lync Server. Ce modèle d’administration ressemble à un centre de données où toutes les tâches d’administration sont réalisées par un groupe informatique unique. Les rôles et les responsabilités au sein de l’équipe doivent être définis en fonction de l’expérience et de l’expertise.

  - **Modèle**   décentralisé les organisations décentralisées se trouvent dans plusieurs emplacements géographiques et ont des serveurs Lync Server et des équipes d’administrateurs à des emplacements différents. Par exemple, il peut y avoir un personnel d’administration local et un ou plusieurs serveurs exécutant Lync Server 2013 pour chaque pays/région. Ou, il peut y avoir un pool de serveurs qui exécutent Lync Server 2013 et une équipe administrative pour l’Amérique du Nord et une autre pour l’Europe. Parfois, vous pouvez souhaiter que les administrateurs soient uniquement responsables de leur propre zone géographique et restreignent les autorisations pour administrer les ressources dans d’autres domaines.

Lync Server vous permet également de déléguer des tâches d’administration spécifiques à des personnes ou des groupes spécifiques à l’aide du contrôle d’accès basé sur un rôle (RBAC). RBAC permet aux administrateurs de déléguer des droits et des autorisations d’utilisateur spécifiques à d’autres administrateurs afin d’effectuer un sous-ensemble des tâches administratives possibles. À l’aide de RBAC, la capacité de l’utilisateur à effectuer des tâches d’administration spécifiques dépend des rôles RBAC attribués à l’utilisateur. RBAC fournit une liste des cmdlets que l’utilisateur peut exécuter en fonction des rôles RBAC dont l’utilisateur est membre.

</div>

</div>

<span> </span>

</div>

</div>

</div>

