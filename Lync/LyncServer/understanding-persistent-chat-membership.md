---
title: Présentation de l’appartenance à la conversation permanente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400866812ab2d5efb12960dc3c2f37c2fcb8eb45
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="43058-102">Présentation de l’appartenance à la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="43058-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43058-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="43058-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="43058-104">L’accès des utilisateurs aux salles de conversation permanente est géré par l’appartenance ; les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages.</span><span class="sxs-lookup"><span data-stu-id="43058-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="43058-105">Seuls les **Présentateurs** qui ont une affiliation aux salles de conversation sont autorisés à utiliser la **publication dans des auditoriums**.</span><span class="sxs-lookup"><span data-stu-id="43058-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="43058-106">Un auditorium est un type de salle de conversation (l’autre type est **Normal**), dans lequel seuls les présentateurs peuvent publier et tout le monde peut lire.</span><span class="sxs-lookup"><span data-stu-id="43058-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="43058-107">En outre, les salles de conversation permanente fonctionnent sous les règles d’une catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="43058-108">Pour plus d’informations sur les catégories, voir [Managing Categories, rooms, and Add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), ainsi que les sections « fonctionnement de la portée des catégories » et « stratégies de catégorie de salle » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="43058-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="43058-109">Un administrateur de conversation permanente peut créer et gérer des catégories de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="43058-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="43058-110">Dans le cadre de la création et de la gestion des catégories de salles de conversation, l’administrateur de conversation permanente peut configurer les principaux (groupes, conteneurs et utilisateurs des services de domaine Active Directory) qui ont accès aux membres ou aux créateurs des salles de conversation d’une catégorie particulière.</span><span class="sxs-lookup"><span data-stu-id="43058-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="43058-111">Services de domaine Active Directory et conversation permanente</span><span class="sxs-lookup"><span data-stu-id="43058-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="43058-112">Le serveur de conversation permanente s’appuie sur Active Directory pour le pool d’utilisateurs de conversation permanente interne.</span><span class="sxs-lookup"><span data-stu-id="43058-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="43058-113">Après avoir installé la conversation permanente (client), vous pouvez ajouter des domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie de salle.</span><span class="sxs-lookup"><span data-stu-id="43058-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="43058-114">Vous pouvez ensuite ajouter ces utilisateurs et groupes à l’appartenance de vos catégories de salles.</span><span class="sxs-lookup"><span data-stu-id="43058-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43058-115">Vous devez vous assurer qu’il n’existe aucun nom en double pour les utilisateurs qui souhaitent modifier leurs salles de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="43058-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="43058-116">Si des noms d’utilisateurs en double existent, modifiez-les pour débloquer les utilisateurs afin qu’ils puissent apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="43058-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="43058-117">Si un utilisateur a des noms en double dans Active Directory et tente d’y effectuer des modifications, un message d’erreur s’affiche pour demander à l’utilisateur de contacter l’administrateur pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="43058-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="43058-118">Fonctionnement de l’étendue des catégories</span><span class="sxs-lookup"><span data-stu-id="43058-118">How Category Scoping Works</span></span>

<span data-ttu-id="43058-119">Une catégorie spécifie tous les utilisateurs et les groupes qui peuvent être membres d’une liste d’appartenance d’une salle de conversation permanente de cette catégorie, en fonction de sa propriété **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="43058-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="43058-120">Par exemple, si vous définissez le **AllowedMembers** de la catégorie sur contoso.com, vous pouvez ajouter un groupe ou un utilisateur de *contoso* en tant que membre aux salles de conversation de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="43058-121">Si vous définissez **AllowedMembers** d’une catégorie à *Ventes*, seuls les groupes et utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membre des salles de conversation de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="43058-122">De la même façon, la propriété **Créateurs** vous permet de contrôler qui peut créer des salles de conversation dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="43058-123">Une fois la salle de conversation créée, toute personne membre du groupe **AllowedMembers** peut être désignée en tant que **Gestionnaire** pour les opérations de gestion courantes des salles (par exemple, modifications des membres et approbations).</span><span class="sxs-lookup"><span data-stu-id="43058-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="43058-124">La définition de **AllowedMembers** et **Créateurs** pour une catégorie comporte les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="43058-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="43058-125">All chat rooms in this category are bound by the restrictions set at the category level.</span><span class="sxs-lookup"><span data-stu-id="43058-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="43058-126">You can use this to segregate chat rooms based on business need and access policies.</span><span class="sxs-lookup"><span data-stu-id="43058-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="43058-127">A user who is in the **Creators** list can create new chat rooms in that category.</span><span class="sxs-lookup"><span data-stu-id="43058-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="43058-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span><span class="sxs-lookup"><span data-stu-id="43058-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="43058-129">Stratégies de catégorie de salle</span><span class="sxs-lookup"><span data-stu-id="43058-129">Room Category Strategies</span></span>

<span data-ttu-id="43058-130">Le **AllowedMembers** d’une catégorie doit inclure tous les utilisateurs qui utiliseront toute salle de conversation permanente de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="43058-131">En fonction des besoins de protection de vos données et pour contrôler les niveaux d’accès, vous pouvez définir une ou plusieurs catégories pour spécifier qui peut effectuer des recherches dans les salles et y participer.</span><span class="sxs-lookup"><span data-stu-id="43058-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="43058-132">Si vous ne voulez autoriser qu’un groupe d’utilisateurs donnés (support technique ou employés à plein temps) à créer des salles, vous pouvez définir l’étendue de **Créateurs** d’une catégorie pour répondre à ce besoin.</span><span class="sxs-lookup"><span data-stu-id="43058-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="43058-133">Categories can also be used to create ethical walls.</span><span class="sxs-lookup"><span data-stu-id="43058-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="43058-134">Ethical walls prevent any conflict of interest in an organization.</span><span class="sxs-lookup"><span data-stu-id="43058-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="43058-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span><span class="sxs-lookup"><span data-stu-id="43058-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43058-136">Dans Lync Server 2013, serveur de conversation permanente, nous ne prenons pas en charge l’accès aux utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="43058-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="43058-137">S’il existe des conversations d’utilisateurs fédérés dans les versions précédentes du serveur de conversation permanente, elles sont migrées.</span><span class="sxs-lookup"><span data-stu-id="43058-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="43058-138">Les utilisateurs fédérés sont ajoutés en tant que principaux désactivés.</span><span class="sxs-lookup"><span data-stu-id="43058-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="43058-139">Limitation des membres aux groupes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="43058-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="43058-140">Lorsque vous ajoutez un domaine à une catégorie, les groupes d’utilisateurs dont les objets de groupe sont contenus dans ce domaine sont mis à votre disposition pour que vous les définissiez en tant que membres des salles de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="43058-141">Nous vous recommandons, en règle générale, d’utiliser des conteneurs Active Directory, tels que des domaines et des unités d’organisation, pour définir le **AllowedMembers** et les **créateurs**d’une catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="43058-142">Vous pouvez ajouter des objets d’un domaine à une liste **AllowedMembers** ou **Créateurs**.</span><span class="sxs-lookup"><span data-stu-id="43058-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="43058-143">Seuls les objets de ces listes **AllowedMembers** ou **Créateurs** peuvent être ajoutés aux salles de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="43058-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

