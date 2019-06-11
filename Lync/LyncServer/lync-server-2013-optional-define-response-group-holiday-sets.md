---
title: 'Lync Server 2013: (facultatif) définir les jeux de jours fériés de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ca58b3e2c17ea70e9af7a9eba48df8582b1485c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="ca8ff-102">Facultatif Définir des jeux de vacances de groupe de réponse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca8ff-102">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca8ff-103">_**Dernière modification de la rubrique:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="ca8ff-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="ca8ff-p101">Les paramètres relatifs aux congés définissent les jours de fermeture d’un groupe Response Group et spécifient l’action à effectuer pendant ces jours. Une période de congé est un ensemble de congés, qui s’applique à un groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="ca8ff-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca8ff-106">Si un flux de travail est défini en tant que flux de travail géré, tout utilisateur auquel est affecté le rôle CsResponseGroupManager peut définir et modifier les congés des flux de travail dont il assure la gestion.</span><span class="sxs-lookup"><span data-stu-id="ca8ff-106">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="ca8ff-107">Pour créer une période de congés</span><span class="sxs-lookup"><span data-stu-id="ca8ff-107">To create a holiday set</span></span>

1.  <span data-ttu-id="ca8ff-108">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="ca8ff-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ca8ff-109">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ca8ff-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ca8ff-110">Pour chaque congé que vous souhaitez définir, exécutez :</span><span class="sxs-lookup"><span data-stu-id="ca8ff-110">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="ca8ff-111">Pour créer la période de congés contenant les congés définis, exécutez :</span><span class="sxs-lookup"><span data-stu-id="ca8ff-111">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="ca8ff-112">L’exemple ci-dessous présente une période de congés incluant deux congés :</span><span class="sxs-lookup"><span data-stu-id="ca8ff-112">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca8ff-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca8ff-113">See Also</span></span>


[<span data-ttu-id="ca8ff-114">Création ou modification d’un flux de travail de groupe de recherche dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca8ff-114">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="ca8ff-115">Création ou modification d’un flux de travail interactif dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca8ff-115">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="ca8ff-116">Nouveau-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="ca8ff-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="ca8ff-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="ca8ff-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

