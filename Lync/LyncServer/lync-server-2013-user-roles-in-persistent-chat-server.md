---
title: 'Lync Server 2013: rôles d’utilisateur dans un serveur Chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36f84f71ca5253d28d9182acc9279010127ee6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="83a99-102">Rôles d’utilisateur dans un serveur Chat permanent de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83a99-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83a99-103">_**Dernière modification de la rubrique:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="83a99-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="83a99-104">Le serveur Chat permanent fournit le concept de membre autorisé/refusé, qui s’applique aux catégories et aux contrôles persistants qui peuvent accéder aux salles d’une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="83a99-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83a99-105">Les membres autorisés/refusés d’une catégorie ne sont pas les <STRONG></STRONG> mêmes que ceux d’une salle de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="83a99-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="83a99-106">Les résultats de la recherche s’affichent dans la liste des membres autorisés/refusés par l’utilisateur dans la liste des salles de conversation ouvertes et fermées.</span><span class="sxs-lookup"><span data-stu-id="83a99-106">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list.</span></span> <span data-ttu-id="83a99-107">Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre.</span><span class="sxs-lookup"><span data-stu-id="83a99-107">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="83a99-108">L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance.</span><span class="sxs-lookup"><span data-stu-id="83a99-108">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="83a99-109">Le principal raisonnement pour le concept de membres autorisés/refusés est le mur d’éthique.</span><span class="sxs-lookup"><span data-stu-id="83a99-109">The primary rationale for the concept of Allowed/Denied Members is ethical walls.</span></span> <span data-ttu-id="83a99-110">Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions.</span><span class="sxs-lookup"><span data-stu-id="83a99-110">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="83a99-111">Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes.</span><span class="sxs-lookup"><span data-stu-id="83a99-111">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="83a99-112">Avec cette contrainte est conçue dans le système interdit l’ajout d’un utilisateur en tant que membre de la salle, si la catégorie parent l’empêche.</span><span class="sxs-lookup"><span data-stu-id="83a99-112">With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="83a99-113">Vous trouverez ci-après les quatre rôles d’utilisateur de chat permanent:</span><span class="sxs-lookup"><span data-stu-id="83a99-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="83a99-114">**Creator:** Utilisateurs qui ont l’autorisation de créer des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="83a99-115">Ces utilisateurs se trouvent dans la liste de créateurs de certaines catégories: ils peuvent créer des salles de conversation dans cette catégorie, et ils peuvent également affecter des appartenances en fonction de la catégorie et affecter des responsables pour gérer la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="83a99-116">L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que gestionnaire de la salle.</span><span class="sxs-lookup"><span data-stu-id="83a99-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83a99-p104">Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés.</span><span class="sxs-lookup"><span data-stu-id="83a99-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="83a99-119">Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="83a99-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="83a99-120">**Manager:** Utilisateurs qui gèrent les propriétés d’une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="83a99-121">Les gestionnaires de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et modifier la liste des gestionnaires de salle de conversation (ajout et suppression de gestionnaires).</span><span class="sxs-lookup"><span data-stu-id="83a99-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="83a99-122">Les gestionnaires de salle de conversation peuvent s’ajouter eux-mêmes à la liste membres ou présentateurs (pour les salles d’Auditorium) pour pouvoir participer à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="83a99-123">Les gestionnaires de salle de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent rechercher des salles de conversation désactivées et pouvoir les supprimer définitivement).</span><span class="sxs-lookup"><span data-stu-id="83a99-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="83a99-124">Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="83a99-125">Seul l’administrateur de chat permanent peut changer la catégorie après la création de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="83a99-126">Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles.</span><span class="sxs-lookup"><span data-stu-id="83a99-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="83a99-127">**Membre:** Utilisateurs membres d’une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="83a99-128">Ces utilisateurs peuvent voir les salles de conversation dans l’annuaire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées, telles que les messages non lus, les filtres figure et les filtres par Mots clés) et participer à la salle de conversation (peut publier, sauf si la salle est une salle d’Auditorium dans laquelle seuls les présentateurs peuvent publier, obtenir du contenu et effectuer une recherche.</span><span class="sxs-lookup"><span data-stu-id="83a99-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="83a99-129">Les utilisateurs qui ne sont pas membres de la salle de conversation peuvent rechercher une salle de conversation s’ils figurent dans la liste des membres autorisés de la catégorie, mais doivent demander l’accès pour joindre ces salles de conversation et accéder au contenu.</span><span class="sxs-lookup"><span data-stu-id="83a99-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="83a99-130">(Il n’y a pas d’accès ou d’approbations de requête intégré au système; ces opérations sont effectuées en externe par e-mail, par téléphone ou d’autres types de contacts.)</span><span class="sxs-lookup"><span data-stu-id="83a99-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="83a99-131">**Présentateur:** Utilisateurs pouvant publier des billets dans une salle d’Auditorium.</span><span class="sxs-lookup"><span data-stu-id="83a99-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83a99-132">Serveur Chat permanent permet aux utilisateurs de créer et de gérer des salles de conversation pour un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="83a99-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="83a99-133">Toutefois, les utilisateurs ne peuvent pas créer ou gérer des salles de conversation sur d’autres sites au sein de la même topologie.</span><span class="sxs-lookup"><span data-stu-id="83a99-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="83a99-134">Veillez à spécifier des créateurs et des gestionnaires de salle de conversation pour tous les sites de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="83a99-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="83a99-135">Les rôles suivants sont des rôles d’administrateur pour le serveur Chat permanent:</span><span class="sxs-lookup"><span data-stu-id="83a99-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="83a99-136">**Administrateur de chat permanent (CsPersistentChatAdministrator):** Il s’agit d’un nouveau rôle de contrôle d’accès basé sur un rôle (RBAC) permettant d’administrer et de gérer le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="83a99-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="83a99-137">Les utilisateurs ou groupes de sécurité désignés comme CsPersistentChatAdministrator peuvent administrer le serveur Chat permanent en utilisant des applets de commande Windows PowerShell à distance (à partir d’un ordinateur autre que le serveur de chat permanent).</span><span class="sxs-lookup"><span data-stu-id="83a99-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="83a99-138">Le serveur de chat permanent vérifie que l’administrateur de chat permanent est membre du groupe local de l’administrateur local RTC sur le serveur frontal de chat permanent du serveur.</span><span class="sxs-lookup"><span data-stu-id="83a99-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="83a99-139">Le rôle CsPersistentChatAdministrator peut gérer des salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories, marquer des salles comme désactivées), et créer et gérer des catégories de salle de conversation qui définissent les personnes autorisées à créer des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="83a99-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="83a99-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span><span class="sxs-lookup"><span data-stu-id="83a99-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="83a99-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span><span class="sxs-lookup"><span data-stu-id="83a99-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="83a99-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span><span class="sxs-lookup"><span data-stu-id="83a99-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="83a99-143">Les administrateurs peuvent également modifier et gérer la configuration de chat permanent (propriétés du pool, paramètres globaux et configuration de la conformité) et peut également planifier et implémenter une migration à partir d’un ancien déploiement serveur Chat Server vers Lync Server 2013 persistent. Serveurs.</span><span class="sxs-lookup"><span data-stu-id="83a99-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="83a99-144">**Administrateur Lync:** Administrateur général d’entreprise pour Lync Server 2013 responsable du déploiement.</span><span class="sxs-lookup"><span data-stu-id="83a99-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="83a99-145">**Operations Manager:** Utilisateur responsable de la gestion des opérations quotidiennes.</span><span class="sxs-lookup"><span data-stu-id="83a99-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="83a99-146">**Développeurs et fournisseurs tiers:** Les développeurs tiers étendent le système, en particulier, en fournissant une solution de paroi éthique pour les conversations de groupe, le support technique et les outils, les clients Web/mobiles et l’infrastructure de développement des bot.</span><span class="sxs-lookup"><span data-stu-id="83a99-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

