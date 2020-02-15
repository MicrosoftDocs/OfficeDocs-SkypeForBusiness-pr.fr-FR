---
title: 'Lync Server 2013 : suppression d’une file d’attente Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Response Group queue
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48184356
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ee159d95a21b351da21c76cd04209da1c4ee938
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-response-group-queue-in-lync-server-2013"></a><span data-ttu-id="a623a-102">Supprimer une file d’attente Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a623a-102">Delete a Response Group queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a623a-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a623a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a623a-104">Utilisez l’une des procédures suivantes pour supprimer une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="a623a-104">Use one of the following procedures to delete a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a><span data-ttu-id="a623a-105">Pour supprimer une file d’attente à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="a623a-105">To use Lync Server Control Panel to delete a queue</span></span>

1.  <span data-ttu-id="a623a-106">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="a623a-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a623a-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a623a-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a623a-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a623a-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a623a-109">Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **File d’attente**.</span><span class="sxs-lookup"><span data-stu-id="a623a-109">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="a623a-110">Dans le champ de recherche, tapez entièrement ou partiellement le nom de la file d’attente que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="a623a-110">In the search field, type part or all of the name of the queue you want to delete.</span></span>

5.  <span data-ttu-id="a623a-111">Dans la liste des files d’attente, cliquez sur la file d’attente souhaitée, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a623a-111">In the list of queues, click the queue that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="a623a-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a623a-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a><span data-ttu-id="a623a-113">Pour utiliser Windows PowerShell pour supprimer une file d’attente</span><span class="sxs-lookup"><span data-stu-id="a623a-113">To use Windows PowerShell to delete a queue</span></span>

1.  <span data-ttu-id="a623a-114">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="a623a-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a623a-115">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a623a-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a623a-116">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a623a-116">At the command line, run:</span></span>
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    <span data-ttu-id="a623a-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a623a-117">For example:</span></span>
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

