---
title: 'Lync Server 2013 : rôles d’utilisateur dans le serveur de conversation permanente'
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
ms.openlocfilehash: 9c91fcb656d936d0fb469cdec4b01824d3fa97d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518851"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Rôles d’utilisateur dans le serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-03-19_

Le serveur de conversation permanente fournit le concept de membres autorisés/refusés, qui s’applique aux catégories et aux contrôles de conversation permanente qui peuvent accéder aux salles d’une catégorie particulière.

<div>


> [!IMPORTANT]  
> Les membres autorisés/refusés d’une catégorie ne sont pas identiques à ceux d’un rôle de <STRONG>membre</STRONG> , qui s’applique à une salle de conversation permanente.<BR>Les recherches affichent toutes les salles de conversation ouvertes et fermées pour lesquelles l’utilisateur effectuant la recherche figure dans la liste des membres autorisés/refusés. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance.



</div>

La logique principale du concept de membres autorisés/refusés passe par des murs éthiques. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Cette contrainte au sein du système interdit l’ajout d’un utilisateur en tant que membre de la salle si la catégorie parente l’en empêche.

Voici les quatre rôles d’utilisateur pour le serveur de conversation permanente :

  - **Creator :** Utilisateurs disposant des autorisations pour créer des salles de conversation. Ces utilisateurs se trouvent dans la liste des créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie, et ils peuvent également attribuer une appartenance en fonction de la catégorie, et affecter des responsables pour gérer la salle de conversation. L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que responsable de la salle.
    
    <div>
    

    > [!NOTE]  
    > Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés.

    
    </div>
    
    Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.

  - **Responsable :** Les utilisateurs qui gèrent les propriétés d’une salle de conversation. Les gestionnaires de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et modifier la liste des responsables de salle de conversation (ajouter et supprimer des gestionnaires). Les gestionnaires de salles de conversation peuvent s’ajouter eux-mêmes à la liste des membres ou des présentateurs (pour les salles Auditorium) afin qu’ils puissent participer à la salle de conversation. Les responsables de salle de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent interroger les salles de conversation désactivées et les supprimer définitivement). Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation. Seul l’administrateur de conversation permanente peut modifier la catégorie une fois que la salle de conversation a été créée.
    
    <div>
    

    > [!IMPORTANT]  
    > Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles.

    
    </div>

  - **Membre :** Utilisateurs membres d’une salle de conversation. Ces utilisateurs peuvent voir les salles de conversation dans l’annuaire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées telles que les messages non lus, les filtres ego et les filtres par Mots-clés) et participer à la salle de conversation (possibilité de publication). Les utilisateurs qui ne sont pas membres de la salle de conversation peuvent rechercher la salle de conversation si elles se trouvent dans la liste des membres autorisés de la catégorie, mais doivent demander l’accès pour rejoindre ces salles de conversation afin d’accéder au contenu. (Il n’y a pas d’accès ou d’approbation de demande intégré au système ; ces opérations sont réalisées en externe par courrier électronique, téléphone ou d’autres formes de contact.)

  - **Présentateur :** Utilisateurs pouvant publier des messages dans une salle de Auditorium.

<div>


> [!NOTE]  
> Le serveur de conversation permanente permet aux utilisateurs de créer et de gérer une salle de conversation pour un site spécifique. Toutefois, les utilisateurs ne peuvent pas créer ou gérer des salles de conversation sur d’autres sites au sein de la même topologie. Veillez à spécifier des créateurs et des responsables de salle de conversation pour tous les sites de votre organisation.



</div>

Les rôles suivants sont les rôles d’administrateur pour le serveur de conversation permanente :

  - **Administrateur de conversation permanente (CsPersistentChatAdministrator) :** Il s’agit d’un nouveau rôle de contrôle d’accès Role-Based (RBAC) permettant d’administrer et de gérer le serveur de conversation permanente. Les utilisateurs ou groupes de sécurité désignés comme CsPersistentChatAdministrator peuvent administrer le serveur de conversation permanente à l’aide des applets de commande Windows PowerShell à distance (c’est-à-dire à partir d’un ordinateur autre que le serveur de conversation permanente). Serveur de conversation permanente vérifie que l’administrateur de conversation permanente est membre du groupe local RTC local Administrator sur le serveur frontal du serveur de conversation permanente.
    
    Le rôle CsPersistentChatAdministrator peut gérer des salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories et désactiver des salles), ainsi que créer et gérer des catégories de salle de conversation qui définissent qui peut créer des salles de conversation et y accéder. Les administrateurs peuvent aussi marquer des salles de conversation comme désactivées et effacer celles qui ne sont plus actives. Les administrateurs ne sont pas soumis aux restrictions des créateurs ou des membres autorisés. Ils peuvent créer toutes sortes de salle de conversation et s’ajouter eux-mêmes en tant que membres de n’importe quelle salle de conversation. Les administrateurs peuvent également modifier et gérer la configuration de la conversation permanente (propriétés du pool, les paramètres globaux et la configuration de la conformité) et également planifier et implémenter la migration à partir d’un ancien déploiement de serveur de conversation de groupe vers le serveur de conversation permanente Lync Server 2013.

  - **Administrateur Lync :** Administrateur général de l’entreprise pour Lync Server 2013 responsable du déploiement.

  - **Operations Manager :** Utilisateur responsable de la gestion des opérations quotidiennes.

  - **Développeurs et partenaires tiers :** Les développeurs tiers étendent le système, en particulier en fournissant une solution murale éthique pour les conversations de groupe, la prise en charge de la conformité et les outils, les clients Web/mobiles et une infrastructure de développement de robots.

</div>

<span> </span>

</div>

</div>

</div>

