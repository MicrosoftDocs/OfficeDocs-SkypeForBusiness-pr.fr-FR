---
title: 'Lync Server 2013 : gestion des groupes d’agents Response Group'
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
ms.openlocfilehash: 34fab5d046aa11435aff5be416e281e5848fe4d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="b677c-102">Gestion des groupes d’agents Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b677c-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b677c-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b677c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b677c-104">Un groupe d’agents se compose d’un groupe de personnes désigné pour répondre aux appels à un groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="b677c-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="b677c-105">Lorsque vous créez un groupe d’agents, vous sélectionnez les agents qui sont affectés au groupe et spécifiez des paramètres de groupe supplémentaires, tels que la méthode de routage et si un agent peut se connecter au groupe et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="b677c-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b677c-106">Les utilisateurs doivent être activés pour voix entreprise avant de pouvoir les ajouter à des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="b677c-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="b677c-107">Pour plus d’informations sur l’activation d’un utilisateur pour voix entreprise, reportez-vous à la rubrique <A href="lync-server-2013-enable-users-for-enterprise-voice.md">activation des utilisateurs pour voix entreprise dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b677c-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b677c-108">Seuls les utilisateurs locaux peuvent être des agents.</span><span class="sxs-lookup"><span data-stu-id="b677c-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="b677c-109">Si un agent est déplacé de local vers en ligne, les appels Response Group ne sont pas acheminés vers cet agent.</span><span class="sxs-lookup"><span data-stu-id="b677c-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="b677c-110">Un agent qui doit se connecter et se déconnecter du groupe, qui est différent de la connexion ou de la sortie de Lync Server, est appelé *agent formel*.</span><span class="sxs-lookup"><span data-stu-id="b677c-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="b677c-111">Les agents formels doivent être connectés au groupe pour pouvoir recevoir des appels routés vers le groupe.</span><span class="sxs-lookup"><span data-stu-id="b677c-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="b677c-112">Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe.</span><span class="sxs-lookup"><span data-stu-id="b677c-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="b677c-113">Les agents formels se connectent et se déconnectent de leurs groupes en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Internet Windows Internet Explorer et afficher une console de page Web.</span><span class="sxs-lookup"><span data-stu-id="b677c-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="b677c-114">Un agent qui ne se connecte pas ou n’est pas en dehors du groupe est appelé *agent informel*.</span><span class="sxs-lookup"><span data-stu-id="b677c-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="b677c-115">Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server, et ils ne peuvent pas se déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="b677c-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b677c-116">Lorsque vous affectez des utilisateurs en tant qu’agents au groupe de réponses, informez-les que, s’ils ont activé le mode de confidentialité, ils doivent rechercher des contacts « RGS Presence Watcher » et les ajouter à leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="b677c-116">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="b677c-117">Les agents dont le mode de confidentialité est activé, mais qui n’ont pas « RGS presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="b677c-117">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="b677c-118">Cela ne concerne pas les agents qui n’ont pas activé le mode de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="b677c-118">Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b677c-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b677c-119">In This Section</span></span>

  - [<span data-ttu-id="b677c-120">Création ou modification d’un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b677c-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="b677c-121">Supprimer un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b677c-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

