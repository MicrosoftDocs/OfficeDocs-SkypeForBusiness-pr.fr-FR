---
title: 'Lync Server 2013 : gestion des groupes d’agents de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="9e1db-102">Gestion des groupes d’agents de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1db-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e1db-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9e1db-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9e1db-104">Un groupe d’agents se compose d’un groupe de personnes qui sont conçues pour répondre aux appels d’un Response Group.</span><span class="sxs-lookup"><span data-stu-id="9e1db-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="9e1db-105">Lorsque vous créez un groupe d’agents, vous sélectionnez les agents qui sont affectés au groupe et spécifiez des paramètres de groupe supplémentaires, tels que la méthode de routage, et la possibilité pour un agent de se connecter au groupe et de s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="9e1db-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e1db-106">Les utilisateurs doivent être activés pour voix entreprise avant de pouvoir les ajouter aux groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="9e1db-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="9e1db-107">Pour plus d’informations sur l’activation d’un utilisateur pour la voix entreprise, voir <A href="lync-server-2013-enable-users-for-enterprise-voice.md">activer les utilisateurs d’Enterprise Voice dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e1db-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9e1db-108">Seuls les utilisateurs locaux peuvent être des agents.</span><span class="sxs-lookup"><span data-stu-id="9e1db-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="9e1db-109">Si un agent est déplacé de local vers en ligne, les appels de groupe de réponse ne seront pas routés vers cet agent.</span><span class="sxs-lookup"><span data-stu-id="9e1db-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="9e1db-110">Un agent qui doit se connecter ou se déconnecter du groupe, qui est différent de la connexion ou de la déconnexion de Lync Server, est appelé *agent formel*.</span><span class="sxs-lookup"><span data-stu-id="9e1db-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="9e1db-111">Les agents officiels doivent être connectés au groupe pour pouvoir recevoir des appels routés vers le groupe.</span><span class="sxs-lookup"><span data-stu-id="9e1db-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="9e1db-112">Cela peut s’avérer utile pour les agents qui répondent à temps partiel aux appels du groupe.</span><span class="sxs-lookup"><span data-stu-id="9e1db-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="9e1db-113">Les agents officiels se connectent à leurs groupes en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Internet de Windows Internet Explorer et afficher une console Web.</span><span class="sxs-lookup"><span data-stu-id="9e1db-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="9e1db-114">Un agent qui ne se connecte pas ou n’utilise pas le groupe est appelé *agent informel*.</span><span class="sxs-lookup"><span data-stu-id="9e1db-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="9e1db-115">Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server et ne peuvent pas se déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="9e1db-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9e1db-p106">Lorsque vous affectez des utilisateurs comme agents de groupe de réponse, informez-les que, si leur mode de confidentialité est activé, ils doivent rechercher des contacts « RGS Presence Watcher » et les rajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont aucun contact « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe de réponse. Les agents dont le mode de confidentialité n’est pas activé ne seront pas affectés.</span><span class="sxs-lookup"><span data-stu-id="9e1db-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e1db-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9e1db-119">In This Section</span></span>

  - [<span data-ttu-id="9e1db-120">Créer ou modifier un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1db-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="9e1db-121">Supprimer un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e1db-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

