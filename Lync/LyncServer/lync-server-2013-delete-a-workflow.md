---
title: 'Lync Server 2013: supprimer un flux de travail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="24f8e-102">Supprimer un flux de travail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24f8e-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24f8e-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="24f8e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="24f8e-104">Pour supprimer un flux de travail, utilisez l’une des procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="24f8e-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="24f8e-105">Pour utiliser le panneau de configuration de Lync Server pour supprimer un flux de travail</span><span class="sxs-lookup"><span data-stu-id="24f8e-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="24f8e-106">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="24f8e-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="24f8e-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24f8e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24f8e-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24f8e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24f8e-109">Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **Flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="24f8e-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="24f8e-110">Dans la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="24f8e-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="24f8e-111">Dans le champ de recherche **Sélectionner un service** , tapez tout ou partie du nom du service **ApplicationServer** qui héberge le flux de travail que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="24f8e-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="24f8e-112">Dans la liste de services, cliquez sur le service que vous souhaitez utiliser, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="24f8e-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24f8e-113">La page Web de l’outil de configuration de Response Group s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="24f8e-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="24f8e-114">Vous pouvez également accéder à la page Web de l’outil de configuration du groupe de réponse directement à partir d’un navigateur Web en vous connectant à <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="24f8e-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="24f8e-115">Sous **gérer un flux de travail existant**, recherchez le flux de travail que vous voulez supprimer, puis sous **action**, cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="24f8e-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="24f8e-116">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="24f8e-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="24f8e-117">Pour utiliser Windows PowerShell pour supprimer un flux de travail</span><span class="sxs-lookup"><span data-stu-id="24f8e-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="24f8e-118">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="24f8e-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="24f8e-119">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="24f8e-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="24f8e-120">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="24f8e-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="24f8e-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="24f8e-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

