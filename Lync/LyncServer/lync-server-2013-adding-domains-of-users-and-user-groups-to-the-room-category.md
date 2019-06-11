---
title: 'Lync Server 2013 : Ajout de domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie de salles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32539c66523cf625c80d5f113cf788b02d3c905b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="40ce9-102">Ajout de domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie de salles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40ce9-102">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40ce9-103">_**Dernière modification de la rubrique:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="40ce9-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="40ce9-104">Pour ajouter des groupes de personnes plus importants à une salle de conversation, voir [configurer les catégories dans Lync Server 2013](lync-server-2013-configure-categories.md) et [gérer les catégories](manage-categories.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="40ce9-104">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="40ce9-105">Par exemple, la commande suivante permet d’ajouter tous les utilisateurs de l’unité d’organisation NorthAmericaUsers dans Active Directory à la salle de conversation du Nord:</span><span class="sxs-lookup"><span data-stu-id="40ce9-105">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="40ce9-106">Sa commande permet d’ajouter tous les membres du groupe de distribution finance à la même salle de conversation:</span><span class="sxs-lookup"><span data-stu-id="40ce9-106">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

