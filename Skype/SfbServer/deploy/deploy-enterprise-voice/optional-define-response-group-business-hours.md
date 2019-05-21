---
title: Facultatif Définir des heures d’activité de groupe de réponse dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Créez ou modifiez les heures d’activité du groupe de réponses dans Skype entreprise Server Voice.
ms.openlocfilehash: 9f00e89bede48af8c36de93da951df9b69a692e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306332"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="dd608-103">Facultatif Définir des heures d’activité de groupe de réponse dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="dd608-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="dd608-104">Créez ou modifiez les heures d’activité du groupe de réponses dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="dd608-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="dd608-105">Définition des heures d’ouverture</span><span class="sxs-lookup"><span data-stu-id="dd608-105">Defining Business Hours</span></span>

<span data-ttu-id="dd608-106">Les paramètres des heures d’ouverture définissent si le flux de travail est disponible pour répondre aux appels et spécifient les actions à prendre lorsque les appels sont passés en dehors des heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="dd608-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="dd608-107">Les administrateurs de Response Group peuvent utiliser l’applet de commande **New-CsRgsHoursOfBusiness** afin de créer des plannings prédéfinis disponibles pour un nombre de groupes Response Group quelconque.</span><span class="sxs-lookup"><span data-stu-id="dd608-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="dd608-108">Lorsque vous créez ou modifiez un flux de travail, vous pouvez spécifier un planning personnalisé s’appliquant uniquement à ce flux de travail.</span><span class="sxs-lookup"><span data-stu-id="dd608-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="dd608-109">Pour plus d’informations, reportez-vous à [conception et création de flux de travail de groupe de réponse dans Skype entreprise](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="dd608-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dd608-110">Si un flux de travail est défini en tant que flux de travail géré, alors tous les utilisateurs affectés au rôle CsResponseGroupManager peuvent définir et modifier les heures d’ouverture personnalisées des flux de travail qu’ils gèrent.</span><span class="sxs-lookup"><span data-stu-id="dd608-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dd608-111">Utilisez un format 24 heures pour les paramètres des applets de commande suivantes (par exemple, 20:00 = 8:00 du soir).</span><span class="sxs-lookup"><span data-stu-id="dd608-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="dd608-112">Pour créer une collection d’heures d’ouverture prédéfinie</span><span class="sxs-lookup"><span data-stu-id="dd608-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="dd608-113">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="dd608-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="dd608-114">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dd608-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dd608-115">Pour chaque plage horaire unique que vous souhaitez définir, exécutez :</span><span class="sxs-lookup"><span data-stu-id="dd608-115">For each unique range of hours you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="dd608-116">Pour créer la collection d’heures d’ouverture qui utilise les plages que vous avez définies, exécutez :</span><span class="sxs-lookup"><span data-stu-id="dd608-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="dd608-p103">L’exemple ci-après spécifie les heures d’ouverture suivantes : de 9:00 à 17:00 les jours de la semaine, de 8:00 à 10:00 puis de 14:00 à 18:00 le samedi et fermeture le dimanche :</span><span class="sxs-lookup"><span data-stu-id="dd608-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="dd608-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd608-124">See also</span></span>

[<span data-ttu-id="dd608-125">Nouveau-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="dd608-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="dd608-126">Nouveau-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="dd608-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
