---
title: 'Lync Server 2013: administration du système'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62526daf43308b4ed38538e5ea16e15b271fc9a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Administration du système dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-08-18_

L’administration du système inclut les tâches d’administration quotidiennes, planifiées et à la demande, qui sont nécessaires pour maintenir le fonctionnement du système informatique en toute transparence. En règle générale, les tâches d’administration système sont couvertes par des procédures écrites. Ces procédures permettent de vérifier que les mêmes outils et méthodes standard sont utilisés par tous les membres du personnel de support technique.

Dans un environnement Lync, les tâches d’administration système typiques incluent la sauvegarde et l’archivage des pools, le suivi des journaux, la création et la gestion des utilisateurs, et la mise à jour d’un logiciel antivirus.

<div>

## <a name="system-troubleshooting"></a>Résolution des problèmes système

Une organisation doit se préparer à traiter les problèmes inattendus et doit avoir une procédure pour gérer les problèmes à partir du moment où elles sont communiquées jusqu’à leur résolution. Des informations sur la manière dont le personnel du support a diagnostiqué un problème doivent être enregistrés et utilisés à l’avenir pour éviter la répétition inutile du fonctionnement.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Processus de résolution des problèmes système

Le diagramme suivant illustre le processus de résolution des problèmes de système et les interactions avec d’autres rôles d’opérations.

**Organigramme de résolution des problèmes système**

![Organigramme de résolution des problèmes système] (images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Organigramme de résolution des problèmes système")

  - **Pour classer et**   définir la priorité de cette tâche, le service d’assistance est généralement exécuté. Par exemple, un problème est susceptible d’être regroupé en tant que problème logiciel ou en cas de problème de matériel. Le problème est ensuite acheminé vers l’équipe de support technique appropriée pour examen. Les règles de détermination de la priorité d’un problème, ainsi que le temps de réponse et le temps de résolution, sont généralement définis dans le contrat SLA.

  - **Recherchez et diagnostiquez**   l’équipe de support technique appropriée pour diagnostiquer le problème et proposer des modifications pour résoudre ce problème. S’il s’agit d’une solution simple et qu’elle n’exige aucun contrôle de modification, la solution peut être appliquée immédiatement. Si la solution n’est pas facile, une demande de modification doit être levée et le processus de gestion des modifications doit être géré par le processus de gestion des modifications, souvent dans le cadre d’une procédure de suivi rapide. Les modifications apportées doivent être enregistrées à l’aide du processus de gestion de la configuration.

  - **Fermez et notez**   après avoir testé la résolution, le problème devrait être clos. S’il existe des leçons à découvrir du problème, une entrée doit être créée dans la base de connaissances.

  - **Réviser et analyse**   des tendances les avis périodiques des problèmes récents doivent être réalisés pour identifier les tendances des problèmes. Par exemple, si les utilisateurs rencontrent des problèmes fréquents de connexion lente à leurs sites Lync, des problèmes de bande passante réseau peuvent en être la cause. Les délais de résolution des problèmes et l’incidence de tout problème de disponibilité du système doivent être examinés et comparés avec le contrat SLA. La personne qui se connecte au client en cas de problème de service, par exemple, un responsable de compte, doit être informée de problèmes importants.

</div>

<div>

## <a name="issue-management-tools"></a>Outils de gestion des problèmes

Les outils de support technique permettent aux membres du personnel d’enregistrer, de classifier et de hiérarchiser les nouveaux problèmes. Les outils fournissent alors les processus de flux de travail de gestion de la demande de service de problème par le biais d’enquêtes et de diagnostics, souvent par plusieurs membres de l’équipe de support technique. Outils, qui fournissent fréquemment des rapports sur les temps de résolution et les tendances historiques, peuvent également inclure une base de données de la base de connaissances, qui peut être utilisée pour effectuer une recherche dans d’anciens problèmes.

La base de connaissances Microsoft est un enregistrement utile des problèmes de support rencontrés par Microsoft. Pour plus d’informations, consultez le site Web du<http://go.microsoft.com/fwlink/?linkid=14898>support Microsoft ().

Le logiciel tiers doit généralement être personnalisé pour répondre aux besoins de l’organisation, par exemple, l’Organisation des équipes, les exigences en matière de création de rapports et les mesures requises par le SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Administration centralisée et décentralisée

Les rôles et les responsabilités liés à l’exécution des tâches d’administration du système varient selon que l’organisation suit ou non un modèle centralisé, un modèle décentralisé ou une combinaison des deux.

  - **Modèle centralisé dans**   un modèle centralisé, un ou plusieurs groupes d’administration conservent le contrôle total de l’ensemble de l’environnement Lync Server. Ce modèle d’administration ressemble à un centre de données dans lequel toutes les tâches d’administration sont effectuées par un groupe de technologies d’information unique. Les rôles et les responsabilités au sein de l’équipe doivent être définis en fonction de l’expérience et de l’expertise.

  - ****   Les organisations décentralisées du modèle décentralisé sont situées dans plusieurs emplacements géographiques et disposent de serveurs Lync Server et de équipes d’administrateurs situés à des emplacements différents. Par exemple, il se peut que le personnel d’administration local et un ou plusieurs serveurs exécutant Lync Server 2013 pour chaque pays/région. Il est possible qu’il y ait un pool de serveurs exécutant Lync Server 2013 et une équipe administrative pour l’Amérique du Nord et une pour l’Europe. Parfois, vous souhaiterez peut-être que les administrateurs puissent être responsables uniquement de leur propre zone géographique et limiter les autorisations d’administration des ressources dans d’autres zones.

Lync Server vous permet également de déléguer des tâches administratives spécifiques à des personnes ou groupes spécifiques à l’aide d’un contrôle d’accès basé sur les rôles (RBAC). Le RBAC permet aux administrateurs de déléguer des droits d’utilisateur et des autorisations à d’autres administrateurs pour effectuer un sous-ensemble de tâches administratives possibles. En utilisant RBAC, la capacité de l’utilisateur à effectuer des tâches d’administration dépend des rôles RBAC attribués à l’utilisateur. Le RBAC fournit une liste des cmdlets que l’utilisateur peut exécuter en fonction des rôles RBAC dont l’utilisateur est membre.

</div>

</div>

<span> </span>

</div>

</div>

</div>

