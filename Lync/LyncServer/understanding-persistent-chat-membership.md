---
title: Description de l’appartenance à la conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="0e999-102">Description de l’appartenance à la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="0e999-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e999-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0e999-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0e999-104">L’accès des utilisateurs aux salles de conversation permanentes est géré par l’appartenance ; les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages.</span><span class="sxs-lookup"><span data-stu-id="0e999-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="0e999-105">Seuls les **présentateurs** disposant d’une affiliation désignée avec des salles de conversation peuvent utiliser la **publication sur les salles d’Auditorium**.</span><span class="sxs-lookup"><span data-stu-id="0e999-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="0e999-106">Un auditorium est un type de salle de conversation (l’autre est **normal**), dans lequel seuls les présentateurs peuvent publier et tout le monde peut lire.</span><span class="sxs-lookup"><span data-stu-id="0e999-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="0e999-107">De plus, les salles de conversation permanente fonctionnent conformément aux règles d’une catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="0e999-108">Pour plus d’informations sur les catégories, voir [gérer des catégories, des salles et des compléments dans Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), ainsi que les sections « fonctionnement de la portée de la catégorie » et « stratégies de catégorie de salle » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="0e999-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="0e999-109">Un administrateur de chat permanent peut créer et gérer des catégories de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="0e999-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="0e999-110">Dans le cadre de la création et de la gestion des catégories de salle de conversation, l’administrateur de chat permanent peut configurer des principales (services de domaine Active Directory) qui peuvent être membres ou créateurs de salles de conversation d’une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="0e999-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="0e999-111">Services de domaine Active Directory et conversation permanente</span><span class="sxs-lookup"><span data-stu-id="0e999-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="0e999-112">Le serveur Chat permanent s’appuie sur Active Directory pour le pool d’utilisateurs de chat permanents internes.</span><span class="sxs-lookup"><span data-stu-id="0e999-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="0e999-113">Après l’installation d’une conversation permanente (client), vous pouvez ajouter des domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie salle.</span><span class="sxs-lookup"><span data-stu-id="0e999-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="0e999-114">Vous pouvez ensuite ajouter ces utilisateurs et groupes à l’appartenance aux catégories de votre salle.</span><span class="sxs-lookup"><span data-stu-id="0e999-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e999-115">Vous devez vérifier qu’il n’y a aucun doublon pour les utilisateurs qui souhaitent apporter des modifications à leurs salles de conversation permanentes.</span><span class="sxs-lookup"><span data-stu-id="0e999-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="0e999-116">S’il existe des noms d’utilisateur en double, remplacez-les par d’autres noms pour autoriser les utilisateurs à y apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="0e999-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="0e999-117">Si un utilisateur a des noms dupliqués dans Active Directory et tente d’y apporter des modifications, un message d’erreur s’affiche pour inviter l’utilisateur à contacter l’administrateur pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="0e999-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="0e999-118">Fonctionnement de la portée de la catégorie</span><span class="sxs-lookup"><span data-stu-id="0e999-118">How Category Scoping Works</span></span>

<span data-ttu-id="0e999-119">Une catégorie spécifie tous les utilisateurs et groupes qui peuvent être membres d’une liste d’appartenance d’une salle de conversation permanente de cette catégorie en fonction de la propriété **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="0e999-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="0e999-120">Par exemple, si vous définissez le **AllowedMembers** de la catégorie sur contoso.com, vous pouvez ajouter un groupe ou un utilisateur de *contoso* en tant que membre aux salles de conversation de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="0e999-121">Si vous définissez **AllowedMembers** sur une catégorie sur *ventes*, seuls les groupes et les utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membres à des salles de conversation dans cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="0e999-122">De même, la propriété **créateurs** vous permet de contrôler qui peut créer des salles de conversation dans cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="0e999-123">Après la création d’une salle de conversation, tous les membres du groupe **AllowedMembers** peuvent être désignés en tant que **responsable** pour les opérations de gestion en cours sur les salles (par exemple, modifications d’appartenance et approbations).</span><span class="sxs-lookup"><span data-stu-id="0e999-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="0e999-124">La définition de **AllowedMembers** et de **créateurs** pour une catégorie offre les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="0e999-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="0e999-125">Toutes les salles de conversation de cette catégorie sont liées par des limitations définies au niveau de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="0e999-126">Vous pouvez utiliser cela pour isoler des salles de conversation en fonction des besoins et des stratégies d’accès.</span><span class="sxs-lookup"><span data-stu-id="0e999-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="0e999-127">Les utilisateurs qui se trouvent dans la liste de **créateurs** peuvent créer de nouvelles salles de conversation dans cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="0e999-128">Si vous voulez implémenter un système dans lequel un nombre restreint de membres du personnel de l’organisation peut créer des salles de conversation, ce contrôle peut être utilisé pour respecter cette exigence.</span><span class="sxs-lookup"><span data-stu-id="0e999-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="0e999-129">Stratégies de catégorie de salle</span><span class="sxs-lookup"><span data-stu-id="0e999-129">Room Category Strategies</span></span>

<span data-ttu-id="0e999-130">Le **AllowedMembers** d’une catégorie doit inclure tous les utilisateurs qui utiliseront toute salle de conversation permanente de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="0e999-131">En fonction de vos besoins en matière de protection des données d’entreprise et de garantir le niveau d’accès approprié, vous pouvez définir une ou plusieurs catégories pour spécifier qui peut rechercher et participer à des salles.</span><span class="sxs-lookup"><span data-stu-id="0e999-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="0e999-132">Si vous ne souhaitez autoriser qu’un ensemble spécifique d’utilisateurs (un support technique central ou uniquement des employés à plein temps) à créer des salles, vous pouvez définir la portée des **créateurs** d’une catégorie pour ce faire.</span><span class="sxs-lookup"><span data-stu-id="0e999-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="0e999-133">Les catégories peuvent également être utilisées pour créer des murs éthiques.</span><span class="sxs-lookup"><span data-stu-id="0e999-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="0e999-134">Les murs éthiques empêchent tout conflit d’intérêt au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="0e999-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="0e999-135">Par exemple, un administrateur peut créer des salles de conversation dans une catégorie uniquement pour les commerçants, alors qu’il n’est pas possible d’utiliser les analystes dans une autre catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e999-136">Dans Lync Server 2013, serveur de chat permanent, nous ne prenons pas en charge l’accès aux utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="0e999-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="0e999-137">S’il existe des discussions des utilisateurs fédérés dans les versions précédentes du serveur de chat permanent, celles-ci sont déplacées.</span><span class="sxs-lookup"><span data-stu-id="0e999-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="0e999-138">Les utilisateurs fédérés sont ajoutés comme principaux désactivés.</span><span class="sxs-lookup"><span data-stu-id="0e999-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="0e999-139">Réduction des membres à des groupes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0e999-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="0e999-140">Lorsque vous ajoutez un domaine à une catégorie, il est possible d’accéder aux groupes d’utilisateurs dont les objets de groupe sont contenus dans ce domaine, afin que vous puissiez les spécifier en tant que membres de salles de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="0e999-141">En règle générale, nous vous conseillons d’utiliser les conteneurs Active Directory, tels que les domaines et les unités d’organisation, pour définir les **AllowedMembers** et **créateurs**d’une catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="0e999-142">Vous pouvez ajouter des objets de n’importe quel domaine à une liste de **AllowedMembers** ou de **créateurs** .</span><span class="sxs-lookup"><span data-stu-id="0e999-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="0e999-143">Seuls les objets figurant dans la liste **AllowedMembers** ou **Creators** peuvent être ajoutés aux salles de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="0e999-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

