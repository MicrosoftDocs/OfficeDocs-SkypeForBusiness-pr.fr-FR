---
title: Utilisation de catégories pour administrer le serveur de conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2aa30e39594bfa0a294b4ad0d5755cdcb60c090
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="59d76-102">Utilisation de catégories pour administrer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="59d76-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59d76-103">_**Dernière modification de la rubrique :** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="59d76-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="59d76-104">Votre déploiement de serveur de conversation permanente peut héberger de nombreuses salles de conversation permanentes simultanées.</span><span class="sxs-lookup"><span data-stu-id="59d76-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="59d76-105">Les salles de conversation peuvent être organisées en un ensemble de catégories sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="59d76-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="59d76-106">Chaque salle de conversation appartient à une catégorie et hérite de certains paramètres de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="59d76-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="59d76-107">Cette organisation crée une structure utile pour l’identification des conversations en fonction de leur objectif professionnel et simplifie la délégation de l’administration ainsi que la gestion.</span><span class="sxs-lookup"><span data-stu-id="59d76-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59d76-108">Bien que de nombreuses fonctionnalités de gestion des salles de conversation soient disponibles sur les ordinateurs qui exécutent une conversation permanente (client Lync) pour l’utilisateur, les administrateurs de conversation permanente (dans le rôle <STRONG>cspersistentchatadministrator</STRONG> ) doivent utiliser le panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer ou gérer des catégories.</span><span class="sxs-lookup"><span data-stu-id="59d76-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="59d76-109">Les administrateurs de conversation permanente utilisent le panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer et gérer des catégories, ainsi que pour concevoir l’accès aux salles de conversation pour les utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="59d76-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="59d76-110">Les gestionnaires de salles de conversation permanente, qui peuvent gérer une ou plusieurs salles de conversation, peuvent utiliser le client Lync pour lancer une application Web de gestion de salle afin de créer et gérer des salles (ou les clients peuvent créer des solutions et des flux de travail personnalisés à appeler).</span><span class="sxs-lookup"><span data-stu-id="59d76-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="59d76-111">Les administrateurs de conversation permanente peuvent également utiliser le panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer et gérer des salles.</span><span class="sxs-lookup"><span data-stu-id="59d76-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59d76-112">Une salle de conversation permanente ne peut pas avoir le même nom qu’une catégorie de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="59d76-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="59d76-p103">Les responsables de salles de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, à l’exception de la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="59d76-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="59d76-115">Désactivation d’une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="59d76-115">Disabling a chat room</span></span>

  - <span data-ttu-id="59d76-116">Modification du nom d’une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="59d76-116">Changing a chat room name</span></span>

  - <span data-ttu-id="59d76-117">Modification de la description d’une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="59d76-117">Changing a chat room description</span></span>

  - <span data-ttu-id="59d76-118">Modification du type d’une salle de conversation (Auditorium ou Normal)</span><span class="sxs-lookup"><span data-stu-id="59d76-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="59d76-119">modification de la confidentialité d’une salle (ouverte/fermée/secrète) ;</span><span class="sxs-lookup"><span data-stu-id="59d76-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="59d76-120">Ajout ou suppression de membres</span><span class="sxs-lookup"><span data-stu-id="59d76-120">Adding or removing members</span></span>

  - <span data-ttu-id="59d76-121">Ajout ou suppression de gestionnaires de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="59d76-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="59d76-122">Ajout ou suppression d’un complément</span><span class="sxs-lookup"><span data-stu-id="59d76-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="59d76-123">Modification de paramètres tels que les invitations (en fonction de ce qui est autorisé par la catégorie)</span><span class="sxs-lookup"><span data-stu-id="59d76-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="59d76-124">Administration déléguée</span><span class="sxs-lookup"><span data-stu-id="59d76-124">Delegated Administration</span></span>

<span data-ttu-id="59d76-125">La création et la gestion de salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories.</span><span class="sxs-lookup"><span data-stu-id="59d76-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="59d76-126">Un administrateur de conversation permanente peut définir **AllowedMembers** et des **créateurs** pour chaque catégorie, et peut également définir les paramètres et les comportements de la salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="59d76-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="59d76-127">Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du panneau de configuration Lync Server ou des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59d76-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="59d76-128">Les utilisateurs, les unités d’organisation (UO) et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="59d76-128">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="59d76-129">Une fois la catégorie créée, les utilisateurs, les unités d’organisation et les groupes d’utilisateurs de la liste **AllowedMembers** de la catégorie peuvent choisir comme responsables et membres de la salle de conversation pour gérer et participer à la salle.</span><span class="sxs-lookup"><span data-stu-id="59d76-129">After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="59d76-130">Les salles de conversation créées dans une catégorie adhèrent aux stratégies et paramètres appliqués par la catégorie (par exemple, qui peuvent être dans l’appartenance de la salle, qui peut gérer la salle, si les téléchargements de fichiers sont autorisés, si les invitations sont envoyées, etc.).</span><span class="sxs-lookup"><span data-stu-id="59d76-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

