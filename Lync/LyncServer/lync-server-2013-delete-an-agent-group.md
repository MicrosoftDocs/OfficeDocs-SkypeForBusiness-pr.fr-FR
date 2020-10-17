---
title: 'Lync Server 2013 : suppression d’un groupe d’agents'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46ec34da45e22386d1b6b45528818725b60790f2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516281"
---
# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="4eced-102">Supprimer un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eced-102">Delete an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eced-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4eced-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4eced-104">Les procédures suivantes permettent de supprimer un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="4eced-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="4eced-105">Pour supprimer un groupe d’agents à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="4eced-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="4eced-106">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="4eced-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="4eced-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4eced-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4eced-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4eced-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4eced-109">Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="4eced-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="4eced-110">Dans la page **Services Response Group**, tapez entièrement ou partiellement le nom du groupe d’agents que vous voulez supprimer dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="4eced-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="4eced-111">Dans la liste obtenue, cliquez sur le groupe à supprimer, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="4eced-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="4eced-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4eced-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="4eced-113">Pour utiliser Windows PowerShell afin de supprimer un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="4eced-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="4eced-114">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="4eced-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="4eced-115">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4eced-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4eced-116">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4eced-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="4eced-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4eced-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4eced-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4eced-118">See Also</span></span>


[<span data-ttu-id="4eced-119">Création ou modification d’un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eced-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="4eced-120">Remove-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4eced-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="4eced-121">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4eced-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

