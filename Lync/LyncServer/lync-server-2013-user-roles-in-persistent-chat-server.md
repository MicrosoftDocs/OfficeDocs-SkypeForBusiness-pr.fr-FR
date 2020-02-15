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
ms.openlocfilehash: 34087f83a53fd1e52c3d67df4ef50411d6517160
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="cc13b-102">Rôles d’utilisateur dans le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc13b-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc13b-103">_**Dernière modification de la rubrique :** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="cc13b-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="cc13b-104">Le serveur de conversation permanente fournit le concept de membres autorisés/refusés, qui s’applique aux catégories et aux contrôles de conversation permanente qui peuvent accéder aux salles d’une catégorie particulière.</span><span class="sxs-lookup"><span data-stu-id="cc13b-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc13b-105">Les membres autorisés/refusés d’une catégorie ne sont pas identiques à ceux d’un rôle de <STRONG>membre</STRONG> , qui s’applique à une salle de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="cc13b-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="cc13b-p101">Les recherches affichent toutes les salles de conversation ouvertes et fermées pour lesquelles l’utilisateur effectuant la recherche figure dans la liste des membres autorisés/refusés. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance.</span><span class="sxs-lookup"><span data-stu-id="cc13b-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="cc13b-p102">La logique principale du concept de membres autorisés/refusés passe par des murs éthiques. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Cette contrainte au sein du système interdit l’ajout d’un utilisateur en tant que membre de la salle si la catégorie parente l’en empêche.</span><span class="sxs-lookup"><span data-stu-id="cc13b-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="cc13b-113">Voici les quatre rôles d’utilisateur pour le serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="cc13b-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="cc13b-114">**Creator :** Utilisateurs disposant des autorisations pour créer des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="cc13b-115">Ces utilisateurs se trouvent dans la liste des créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie, et ils peuvent également attribuer une appartenance en fonction de la catégorie, et affecter des responsables pour gérer la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="cc13b-116">L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que responsable de la salle.</span><span class="sxs-lookup"><span data-stu-id="cc13b-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc13b-p104">Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés.</span><span class="sxs-lookup"><span data-stu-id="cc13b-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="cc13b-119">Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="cc13b-120">**Responsable :** Les utilisateurs qui gèrent les propriétés d’une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="cc13b-121">Les gestionnaires de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et modifier la liste des responsables de salle de conversation (ajouter et supprimer des gestionnaires).</span><span class="sxs-lookup"><span data-stu-id="cc13b-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="cc13b-122">Les gestionnaires de salles de conversation peuvent s’ajouter eux-mêmes à la liste des membres ou des présentateurs (pour les salles Auditorium) afin qu’ils puissent participer à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="cc13b-123">Les responsables de salle de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent interroger les salles de conversation désactivées et les supprimer définitivement).</span><span class="sxs-lookup"><span data-stu-id="cc13b-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="cc13b-124">Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="cc13b-125">Seul l’administrateur de conversation permanente peut modifier la catégorie une fois que la salle de conversation a été créée.</span><span class="sxs-lookup"><span data-stu-id="cc13b-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cc13b-126">Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles.</span><span class="sxs-lookup"><span data-stu-id="cc13b-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="cc13b-127">**Membre :** Utilisateurs membres d’une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="cc13b-128">Ces utilisateurs peuvent voir les salles de conversation dans l’annuaire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées telles que les messages non lus, les filtres ego et les filtres par Mots clés), et participer à la salle de conversation (possibilité de publication, sauf si la salle est une salle de auditorium où seuls les présentateurs peuvent publier, obtenir du contenu et effectuer des recherches).</span><span class="sxs-lookup"><span data-stu-id="cc13b-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="cc13b-129">Les utilisateurs qui ne sont pas membres de la salle de conversation peuvent rechercher la salle de conversation si elles se trouvent dans la liste des membres autorisés de la catégorie, mais doivent demander l’accès pour rejoindre ces salles de conversation afin d’accéder au contenu.</span><span class="sxs-lookup"><span data-stu-id="cc13b-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="cc13b-130">(Il n’y a pas d’accès ou d’approbation de demande intégré au système ; ces opérations sont réalisées en externe par courrier électronique, téléphone ou d’autres formes de contact.)</span><span class="sxs-lookup"><span data-stu-id="cc13b-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="cc13b-131">**Présentateur :** Utilisateurs pouvant publier des messages dans une salle de Auditorium.</span><span class="sxs-lookup"><span data-stu-id="cc13b-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc13b-132">Le serveur de conversation permanente permet aux utilisateurs de créer et de gérer une salle de conversation pour un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="cc13b-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="cc13b-133">Toutefois, les utilisateurs ne peuvent pas créer ou gérer des salles de conversation sur d’autres sites au sein de la même topologie.</span><span class="sxs-lookup"><span data-stu-id="cc13b-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="cc13b-134">Veillez à spécifier des créateurs et des responsables de salle de conversation pour tous les sites de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="cc13b-135">Les rôles suivants sont les rôles d’administrateur pour le serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="cc13b-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="cc13b-136">**Administrateur de conversation permanente (CsPersistentChatAdministrator) :** Il s’agit d’un nouveau rôle de contrôle d’accès basé sur un rôle (RBAC) permettant d’administrer et de gérer le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="cc13b-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="cc13b-137">Les utilisateurs ou groupes de sécurité désignés comme CsPersistentChatAdministrator peuvent administrer le serveur de conversation permanente à l’aide des applets de commande Windows PowerShell à distance (c’est-à-dire à partir d’un ordinateur autre que le serveur de conversation permanente).</span><span class="sxs-lookup"><span data-stu-id="cc13b-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="cc13b-138">Serveur de conversation permanente vérifie que l’administrateur de conversation permanente est membre du groupe local RTC local Administrator sur le serveur frontal du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="cc13b-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="cc13b-139">Le rôle CsPersistentChatAdministrator peut gérer des salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories et désactiver des salles), ainsi que créer et gérer des catégories de salle de conversation qui définissent qui peut créer des salles de conversation et y accéder.</span><span class="sxs-lookup"><span data-stu-id="cc13b-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="cc13b-140">Les administrateurs peuvent aussi marquer des salles de conversation comme désactivées et effacer celles qui ne sont plus actives.</span><span class="sxs-lookup"><span data-stu-id="cc13b-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="cc13b-141">Les administrateurs ne sont pas soumis aux restrictions des créateurs ou des membres autorisés.</span><span class="sxs-lookup"><span data-stu-id="cc13b-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="cc13b-142">Ils peuvent créer toutes sortes de salle de conversation et s’ajouter eux-mêmes en tant que membres de n’importe quelle salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="cc13b-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="cc13b-143">Les administrateurs peuvent également modifier et gérer la configuration de la conversation permanente (propriétés du pool, paramètres globaux et configuration de la conformité) et également planifier et implémenter la migration à partir d’un ancien déploiement de serveur de conversation de groupe vers Lync Server 2013 conversation permanente Serveurs.</span><span class="sxs-lookup"><span data-stu-id="cc13b-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="cc13b-144">**Administrateur Lync :** Administrateur général de l’entreprise pour Lync Server 2013 responsable du déploiement.</span><span class="sxs-lookup"><span data-stu-id="cc13b-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="cc13b-145">**Operations Manager :** Utilisateur responsable de la gestion des opérations quotidiennes.</span><span class="sxs-lookup"><span data-stu-id="cc13b-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="cc13b-146">**Développeurs et partenaires tiers :** Les développeurs tiers étendent le système, en particulier en fournissant une solution murale éthique pour les conversations de groupe, la prise en charge de la conformité et les outils, les clients Web/mobiles et une infrastructure de développement de robots.</span><span class="sxs-lookup"><span data-stu-id="cc13b-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

