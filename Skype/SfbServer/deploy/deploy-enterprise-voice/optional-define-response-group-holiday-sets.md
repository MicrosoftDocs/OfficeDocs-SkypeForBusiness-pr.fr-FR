---
title: (Facultatif) Définir des groupes de congés Response Group dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Créez ou modifiez des groupes de congés Response Group dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 3a8173964cf32c148146ffc4c501861b35bf6077
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103680"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="48935-103">(Facultatif) Définir des groupes de congés Response Group dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="48935-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="48935-104">Créez ou modifiez des groupes de congés Response Group dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="48935-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="48935-p101">Les paramètres relatifs aux congés définissent les jours de fermeture d’un groupe Response Group et spécifient l’action à effectuer pendant ces jours. Une période de congé est un ensemble de congés qui s’applique à un groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="48935-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48935-107">Si un flux de travail est défini en tant que flux de travail géré, tout utilisateur auquel est affecté le rôle CsResponseGroupManager peut définir et modifier les congés des flux de travail dont il assure la gestion.</span><span class="sxs-lookup"><span data-stu-id="48935-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="48935-108">Pour créer une période de congé</span><span class="sxs-lookup"><span data-stu-id="48935-108">To create a holiday set</span></span>

1. <span data-ttu-id="48935-109">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="48935-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="48935-110">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="48935-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="48935-111">Pour chaque congé que vous souhaitez définir, exécutez :</span><span class="sxs-lookup"><span data-stu-id="48935-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="48935-112">Pour créer la période de congé contenant les congés définis, exécutez :</span><span class="sxs-lookup"><span data-stu-id="48935-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="48935-113">L’exemple suivant présente une période de congé incluant deux congés :</span><span class="sxs-lookup"><span data-stu-id="48935-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="48935-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48935-114">See also</span></span>

[<span data-ttu-id="48935-115">Conception et création de flux de travail Response Group dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="48935-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="48935-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="48935-116">New-CsRgsHoliday</span></span>](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="48935-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="48935-117">New-CsRgsHolidaySet</span></span>](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)