---
title: Facultatif Définir des jeux de vacances de groupe de réponse dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Créer ou modifier des ensembles de jours fériés de Response Group dans Skype entreprise Server Voice.
ms.openlocfilehash: cd277412a9cef2c474b8ba60459e216482f2d872
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304488"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="008a4-103">Facultatif Définir des jeux de vacances de groupe de réponse dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="008a4-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="008a4-104">Créer ou modifier des ensembles de jours fériés de Response Group dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="008a4-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="008a4-p101">Les paramètres relatifs aux congés définissent les jours de fermeture d’un groupe Response Group et spécifient l’action à effectuer pendant ces jours. Une période de congé est un ensemble de congés, qui s’applique à un groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="008a4-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="008a4-107">Si un flux de travail est défini en tant que flux de travail géré, tout utilisateur auquel est affecté le rôle CsResponseGroupManager peut définir et modifier les congés des flux de travail dont il assure la gestion.</span><span class="sxs-lookup"><span data-stu-id="008a4-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="008a4-108">Pour créer une période de congés</span><span class="sxs-lookup"><span data-stu-id="008a4-108">To create a holiday set</span></span>

1. <span data-ttu-id="008a4-109">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="008a4-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="008a4-110">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="008a4-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="008a4-111">Pour chaque congé que vous souhaitez définir, exécutez :</span><span class="sxs-lookup"><span data-stu-id="008a4-111">For each holiday you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="008a4-112">Pour créer la période de congés contenant les congés définis, exécutez :</span><span class="sxs-lookup"><span data-stu-id="008a4-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="008a4-113">L’exemple ci-dessous présente une période de congés incluant deux congés :</span><span class="sxs-lookup"><span data-stu-id="008a4-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="008a4-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="008a4-114">See also</span></span>

[<span data-ttu-id="008a4-115">Conception et création de flux de travail de groupe de réponse dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="008a4-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="008a4-116">Nouveau-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="008a4-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="008a4-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="008a4-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
