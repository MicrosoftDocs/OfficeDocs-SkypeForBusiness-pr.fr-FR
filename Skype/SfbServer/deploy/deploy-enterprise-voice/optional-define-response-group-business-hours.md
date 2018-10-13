---
title: (Facultatif) Groupe de réponse de définir les heures d’ouverture Skype pour les entreprises
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Créer ou modifier des heures d’ouverture, dans Skype pour Business Server Enterprise Voice Response Group.
ms.openlocfilehash: a5f24d218ab15cb1307f042363147c9e915a351e
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546805"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="68725-103">(Facultatif) Groupe de réponse de définir les heures d’ouverture Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="68725-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="68725-104">Créer ou modifier des heures d’ouverture, dans Skype pour Business Server Enterprise Voice Response Group.</span><span class="sxs-lookup"><span data-stu-id="68725-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="68725-105">Définition des heures d’ouverture</span><span class="sxs-lookup"><span data-stu-id="68725-105">Defining Business Hours</span></span>

<span data-ttu-id="68725-106">Les paramètres des heures d’ouverture définissent si le flux de travail est disponible pour répondre aux appels et spécifient les actions à prendre lorsque les appels sont passés en dehors des heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="68725-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="68725-107">Les administrateurs de Response Group peuvent utiliser l’applet de commande **New-CsRgsHoursOfBusiness** pour créer des planifications prédéfinies que vous pouvez utiliser pour n’importe quel nombre de groupes de réponses.</span><span class="sxs-lookup"><span data-stu-id="68725-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="68725-108">Lorsque vous créez ou modifiez un flux de travail, vous pouvez spécifier un planning personnalisé s’appliquant uniquement à ce flux de travail.</span><span class="sxs-lookup"><span data-stu-id="68725-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="68725-109">Pour plus d’informations, voir [conception et créer des flux de travail de groupe dans Skype pour les entreprises de réponse](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="68725-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68725-110">Si un flux de travail est défini en tant que flux de travail géré, alors tous les utilisateurs affectés au rôle CsResponseGroupManager peuvent définir et modifier les heures d’ouverture personnalisées des flux de travail qu’ils gèrent.</span><span class="sxs-lookup"><span data-stu-id="68725-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="68725-111">Utilisez un format 24 heures pour les paramètres des applets de commande suivantes (par exemple, 20:00 = 8:00 du soir).</span><span class="sxs-lookup"><span data-stu-id="68725-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="68725-112">Pour créer une collection d’heures d’ouverture prédéfinie</span><span class="sxs-lookup"><span data-stu-id="68725-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="68725-113">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="68725-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="68725-114">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="68725-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="68725-115">Pour chaque plage horaire unique que vous souhaitez définir, exécutez :</span><span class="sxs-lookup"><span data-stu-id="68725-115">For each unique range of hours you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="68725-116">Pour créer la collection d’heures d’ouverture qui utilise les plages que vous avez définies, exécutez :</span><span class="sxs-lookup"><span data-stu-id="68725-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="68725-p103">L’exemple ci-après spécifie les heures d’ouverture suivantes : de 9:00 à 17:00 les jours de la semaine, de 8:00 à 10:00 puis de 14:00 à 18:00 le samedi et fermeture le dimanche :</span><span class="sxs-lookup"><span data-stu-id="68725-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="68725-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68725-124">See also</span></span>

[<span data-ttu-id="68725-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="68725-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="68725-126">Nouvelle-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="68725-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
