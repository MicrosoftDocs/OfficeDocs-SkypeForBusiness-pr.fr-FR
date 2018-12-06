---
title: 'Lync Server 2013 : Configuration du groupe Response Group'
TOCTitle: Configuration du groupe Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205249(v=OCS.15)
ms:contentKeyID: 49298805
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du groupe Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Response Group est une fonctionnalité Voix Entreprise qui achemine et place en file d’attente les appels entrants vers des groupes de personnes, appelés *agents* , par exemple, un support technique ou un service clientèle.

Les composants nécessaires à Response Group sont installés et activés automatiquement sur le serveur frontal ou le serveur Standard Edition quand vous déployez Voix Entreprise. Pour rendre Response Group accessible aux utilisateurs, vous devez configurer des groupes d’agents, des files d’attente, puis des flux de travail. Un administrateur Response Group peut aussi déléguer la configuration d’un flux de travail existant à un gestionnaire Response Group qui peut ensuite modifier et reconfigurer le flux avec ses files d’attente et groupes d’agents associés.

Cette section vous guide tout au long de la configuration de Response GroupLync Server 2013. Nous partons du principe que vous avez déjà lu les sections de planification concernant Response Group et que vous avez déployé un serveur Enterprise Edition ou Standard Edition server avec Voix Entreprise.

> [!TIP]  
> Pour plus d’informations sur la création d’un Response Group à l’aide de Lync Server Management Shell, y compris un exemple de script, reportez-vous à « Création de votre premier groupe de réponse à l’aide de Lync Server Management Shell » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</a>.

## Dans cette section

  - [Autorisations et conditions prérequises pour la configuration de Response Group dans Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Processus de déploiement de Response Group dans Lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Création des groupes d’agents Response Group Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Création des files d’attente Response Group dans Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [(Facultatif) Définition des heures ouvrées des groupes Response Group dans Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [(Facultatif) Définition des groupes de congés des groupes Response Group dans Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Création des flux de travail Response Group dans Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [(Facultatif) Vérification du déploiement de Response Group](lync-server-2013-optional-verify-response-group-deployment.md)

## Voir aussi

#### Autres ressources

[Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

