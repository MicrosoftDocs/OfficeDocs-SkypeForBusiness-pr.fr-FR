---
title: 'Lync Server 2013 : rôles d’utilisateur dans un serveur Chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771eac8e5c8ff1c72bfb2ce64d9b6c04853b30a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Rôles d’utilisateur dans un serveur Chat permanent de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-03-19_

Le serveur Chat permanent fournit le concept de membre autorisé/refusé, qui s’applique aux catégories et aux contrôles persistants qui peuvent accéder aux salles d’une catégorie spécifique.

<div>


> [!IMPORTANT]  
> Les membres autorisés/refusés d’une catégorie ne sont pas les mêmes que ceux <STRONG>d’une salle</STRONG> de conversation permanente.<BR>Les résultats de la recherche s’affichent dans la liste des membres autorisés/refusés par l’utilisateur dans la liste des salles de conversation ouvertes et fermées. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance.



</div>

Le principal raisonnement pour le concept de membres autorisés/refusés est le mur d’éthique. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Avec cette contrainte est conçue dans le système interdit l’ajout d’un utilisateur en tant que membre de la salle, si la catégorie parent l’empêche.

Vous trouverez ci-après les quatre rôles d’utilisateur de chat permanent :

  - **Creator :** Utilisateurs qui ont l’autorisation de créer des salles de conversation. Ces utilisateurs se trouvent dans la liste de créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie, et ils peuvent également affecter des appartenances en fonction de la catégorie et affecter des responsables pour gérer la salle de conversation. L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que gestionnaire de la salle.
    
    <div>
    

    > [!NOTE]  
    > Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés.

    
    </div>
    
    Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.

  - **Manager :** Utilisateurs qui gèrent les propriétés d’une salle de conversation. Les gestionnaires de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et modifier la liste des gestionnaires de salle de conversation (ajout et suppression de gestionnaires). Les gestionnaires de salle de conversation peuvent s’ajouter eux-mêmes à la liste membres ou présentateurs (pour les salles d’Auditorium) pour pouvoir participer à la salle de conversation. Les gestionnaires de salle de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent rechercher des salles de conversation désactivées et pouvoir les supprimer définitivement). Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation. Seul l’administrateur de chat permanent peut changer la catégorie après la création de la salle de conversation.
    
    <div>
    

    > [!IMPORTANT]  
    > Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles.

    
    </div>

  - **Membre :** Utilisateurs membres d’une salle de conversation. Ces utilisateurs peuvent voir les salles de conversation dans l’annuaire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées, telles que les messages non lus, les filtres figure et les filtres par Mots clés) et participer à la salle de conversation (peut publier, sauf si la salle est une salle d’Auditorium dans laquelle seuls les présentateurs peuvent publier, obtenir du contenu et effectuer une recherche. Les utilisateurs qui ne sont pas membres de la salle de conversation peuvent rechercher une salle de conversation s’ils figurent dans la liste des membres autorisés de la catégorie, mais doivent demander l’accès pour joindre ces salles de conversation et accéder au contenu. (Il n’y a pas d’accès ou d’approbations de requête intégré au système ; ces opérations sont effectuées en externe par e-mail, par téléphone ou d’autres types de contacts.)

  - **Présentateur :** Utilisateurs pouvant publier des billets dans une salle d’Auditorium.

<div>


> [!NOTE]  
> Serveur Chat permanent permet aux utilisateurs de créer et de gérer des salles de conversation pour un site spécifique. Toutefois, les utilisateurs ne peuvent pas créer ou gérer des salles de conversation sur d’autres sites au sein de la même topologie. Veillez à spécifier des créateurs et des gestionnaires de salle de conversation pour tous les sites de votre organisation.



</div>

Les rôles suivants sont des rôles d’administrateur pour le serveur Chat permanent :

  - **Administrateur de chat permanent (CsPersistentChatAdministrator) :** Il s’agit d’un nouveau rôle de contrôle d’accès basé sur un rôle (RBAC) permettant d’administrer et de gérer le serveur de chat permanent. Les utilisateurs ou groupes de sécurité désignés comme CsPersistentChatAdministrator peuvent administrer le serveur Chat permanent en utilisant des applets de commande Windows PowerShell à distance (à partir d’un ordinateur autre que le serveur de chat permanent). Le serveur de chat permanent vérifie que l’administrateur de chat permanent est membre du groupe local de l’administrateur local RTC sur le serveur frontal de chat permanent du serveur.
    
    Le rôle CsPersistentChatAdministrator peut gérer des salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories, marquer des salles comme désactivées), et créer et gérer des catégories de salle de conversation qui définissent les personnes autorisées à créer des salles de conversation. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Les administrateurs peuvent également modifier et gérer la configuration de chat permanent (propriétés du pool, paramètres globaux et configuration de la conformité) et peut également planifier et implémenter une migration à partir d’un ancien déploiement serveur Chat Server vers Lync Server 2013 persistent. Serveurs.

  - **Administrateur Lync :** Administrateur général d’entreprise pour Lync Server 2013 responsable du déploiement.

  - **Operations Manager :** Utilisateur responsable de la gestion des opérations quotidiennes.

  - **Développeurs et fournisseurs tiers :** Les développeurs tiers étendent le système, en particulier, en fournissant une solution de paroi éthique pour les conversations de groupe, le support technique et les outils, les clients Web/mobiles et l’infrastructure de développement des bot.

</div>

<span> </span>

</div>

</div>

</div>

