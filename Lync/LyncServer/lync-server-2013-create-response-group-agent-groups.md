---
title: 'Lync Server 2013 : créer des groupes d’agents Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b4f97ad93ecdbfef9e8e170c999f8c9860f830
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="a81eb-102">Créer des groupes d’agents Response Group Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a81eb-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a81eb-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a81eb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a81eb-104">Lorsque vous créez un groupe d’agents, vous sélectionnez les agents assignés au groupe et spécifiez divers autres paramètres du groupe. Vous pouvez ainsi sélectionner la méthode de routage des appels et spécifier si un agent peut se connecter au groupe et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="a81eb-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="a81eb-105">Un agent qui doit se connecter et se déconnecter du groupe, qui est différent de la connexion ou de la sortie de Lync Server, est appelé *agent formel*.</span><span class="sxs-lookup"><span data-stu-id="a81eb-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="a81eb-106">Les agents formels doivent être connectés au groupe pour recevoir des appels acheminés vers le groupe.</span><span class="sxs-lookup"><span data-stu-id="a81eb-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="a81eb-107">Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe.</span><span class="sxs-lookup"><span data-stu-id="a81eb-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="a81eb-108">Les agents formels se connectent et se déconnectent de leurs groupes en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Internet Windows Internet Explorer et afficher une console de page Web.</span><span class="sxs-lookup"><span data-stu-id="a81eb-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="a81eb-109">Un agent qui ne se connecte pas ou n’est pas en dehors du groupe est appelé *agent informel*.</span><span class="sxs-lookup"><span data-stu-id="a81eb-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="a81eb-110">Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server, et ils ne peuvent pas se déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="a81eb-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a81eb-111">Seuls les utilisateurs locaux peuvent être des agents.</span><span class="sxs-lookup"><span data-stu-id="a81eb-111">Only on-premises users can be agents.</span></span> <span data-ttu-id="a81eb-112">Si un agent est déplacé de local vers en ligne, les appels Response Group ne sont pas acheminés vers cet agent.</span><span class="sxs-lookup"><span data-stu-id="a81eb-112">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a81eb-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a81eb-113">In This Section</span></span>

[<span data-ttu-id="a81eb-114">Création ou modification d’un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a81eb-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

