---
title: Utilisation des catégories pour administrer le serveur de conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fed28ecc7c2698f4b320729c68de9c5d56b435b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="9e7da-102">Utilisation des catégories pour administrer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="9e7da-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e7da-103">_**Dernière modification de la rubrique:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="9e7da-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="9e7da-104">Le déploiement de votre serveur Chat permanent peut accueillir de nombreux salles de conversation permanentes concomitantes.</span><span class="sxs-lookup"><span data-stu-id="9e7da-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="9e7da-105">Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="9e7da-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="9e7da-106">Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="9e7da-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="9e7da-107">Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.</span><span class="sxs-lookup"><span data-stu-id="9e7da-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e7da-108">Même si de nombreuses fonctionnalités de gestion des salles de conversation sont disponibles sur des ordinateurs exécutant une conversation permanente (client Lync) pour l’utilisateur, les administrateurs de chat permanent (dans le rôle <STRONG>cspersistentchatadministrator</STRONG> ) doivent utiliser le panneau de configuration de Lync Server ou Cmdlets Windows PowerShell pour créer ou gérer des catégories.</span><span class="sxs-lookup"><span data-stu-id="9e7da-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="9e7da-109">Les administrateurs de chat permanent utilisent le panneau de configuration de Lync Server ou des applets de commande Windows PowerShell pour créer et gérer des catégories, et pour concevoir l’accès aux salles de conversation pour les utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="9e7da-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="9e7da-110">Les gestionnaires de salle de conversation permanents, qui peuvent gérer une ou plusieurs salles de conversation, peuvent utiliser le client Lync pour lancer une application Web de gestion de salle de création et de gestion des salles (ou les clients peuvent créer des solutions et des flux de travail personnalisés à appeler).</span><span class="sxs-lookup"><span data-stu-id="9e7da-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="9e7da-111">Les administrateurs de chat permanent peuvent également utiliser les applets de commande du panneau de configuration de Lync Server ou de Windows PowerShell pour créer et gérer des salles.</span><span class="sxs-lookup"><span data-stu-id="9e7da-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e7da-112">Une salle de conversation permanente ne peut pas avoir le même nom qu’une catégorie de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="9e7da-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="9e7da-p103">Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, mais ne peuvent pas modifier la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9e7da-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="9e7da-115">Désactivation d’une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="9e7da-115">Disabling a chat room</span></span>

  - <span data-ttu-id="9e7da-116">Modification du nom d’une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="9e7da-116">Changing a chat room name</span></span>

  - <span data-ttu-id="9e7da-117">Modification de la description d’une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="9e7da-117">Changing a chat room description</span></span>

  - <span data-ttu-id="9e7da-118">Modification du type de salle d’une conversation (Auditorium ou Normal)</span><span class="sxs-lookup"><span data-stu-id="9e7da-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="9e7da-119">Modification de la confidentialité d’une salle (ouverte, fermée ou secrète)</span><span class="sxs-lookup"><span data-stu-id="9e7da-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="9e7da-120">Ajout ou suppression de membres</span><span class="sxs-lookup"><span data-stu-id="9e7da-120">Adding or removing members</span></span>

  - <span data-ttu-id="9e7da-121">Ajout ou suppression de gestionnaires de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="9e7da-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="9e7da-122">Ajout ou suppression d’un complément</span><span class="sxs-lookup"><span data-stu-id="9e7da-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="9e7da-123">Modification des paramètres, comme les invitations (selon ce qu’autorise la catégorie)</span><span class="sxs-lookup"><span data-stu-id="9e7da-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="9e7da-124">Administration déléguée</span><span class="sxs-lookup"><span data-stu-id="9e7da-124">Delegated Administration</span></span>

<span data-ttu-id="9e7da-125">La création et la gestion des salles de conversation permanentes sont beaucoup plus simples grâce à l’utilisation correcte des catégories.</span><span class="sxs-lookup"><span data-stu-id="9e7da-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="9e7da-126">Un administrateur de chat permanent peut définir des **AllowedMembers** et des **créateurs** pour chaque catégorie, et peut également définir les paramètres et les comportements de la salle de conversation par défaut qui seront appliqués à l’ensemble des salles de conversation créées dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="9e7da-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="9e7da-127">Les administrateurs de chat permanent créent et gèrent des catégories à l’aide du panneau de configuration de Lync Server ou des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e7da-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="9e7da-p105">Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent définir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste **AllowedMembers** de la catégorie comme responsables et membres de salle de conversation pour gérer et participer à la salle.</span><span class="sxs-lookup"><span data-stu-id="9e7da-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="9e7da-130">Les salles de conversation créées dans une catégorie respectent les stratégies et les paramètres appliqués par la catégorie (par exemple, qui peut se trouver dans l’appartenance de la salle, qui peut gérer la salle, si les téléchargements de fichiers sont autorisés, si les invitations sont envoyées, etc.).</span><span class="sxs-lookup"><span data-stu-id="9e7da-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

