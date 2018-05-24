---
title: (Facultatif) Définition des groupes de congés des groupes Response Group dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Créer ou modifier les congés Response Group, dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 0ee6ffa0afdff32096845d7450fa92ff6e720022
ms.sourcegitcommit: 68e68c96c18d854afc0158920e6d9d738f276d91
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a>(Facultatif) Définition des groupes de congés des groupes Response Group dans Skype Entreprise 2015
 
Créer ou modifier les congés Response Group, dans Skype pour Business Server Enterprise Voice.
  
Les paramètres relatifs aux congés définissent les jours de fermeture d’un groupe Response Group et spécifient l’action à effectuer pendant ces jours. Une période de congé est un ensemble de congés, qui s’applique à un groupe Response Group.
  
> [!NOTE]
> Si un flux de travail est défini en tant que flux de travail géré, tout utilisateur auquel est affecté le rôle CsResponseGroupManager peut définir et modifier les congés des flux de travail dont il assure la gestion. 
  
### <a name="to-create-a-holiday-set"></a>Pour créer une période de congés

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Pour chaque congé que vous souhaitez définir, exécutez :
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Pour créer la période de congés contenant les congés définis, exécutez :
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    L’exemple ci-dessous présente une période de congés incluant deux congés :
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Voir aussi

[Concevoir et créer des flux de travail de groupe de réponse dans Skype pour Business 2015](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
