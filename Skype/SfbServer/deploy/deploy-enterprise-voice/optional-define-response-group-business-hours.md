---
title: (Facultatif) Groupe de réponse de définir les heures d’ouverture Skype pour les entreprises
ms.reviewer: ''
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
ms.openlocfilehash: ba10f513495d21c7f94397350c1227cb77fe588b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884676"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(Facultatif) Groupe de réponse de définir les heures d’ouverture Skype pour les entreprises 
 
Créer ou modifier des heures d’ouverture, dans Skype pour Business Server Enterprise Voice Response Group.
  
## <a name="defining-business-hours"></a>Définition des heures d’ouverture

Les paramètres des heures d’ouverture définissent si le flux de travail est disponible pour répondre aux appels et spécifient les actions à prendre lorsque les appels sont passés en dehors des heures d’ouverture. Les administrateurs de Response Group peuvent utiliser l’applet de commande **New-CsRgsHoursOfBusiness** afin de créer des plannings prédéfinis disponibles pour un nombre de groupes Response Group quelconque.
  
> [!TIP]
> Lorsque vous créez ou modifiez un flux de travail, vous pouvez spécifier un planning personnalisé s’appliquant uniquement à ce flux de travail. Pour plus d’informations, voir [conception et créer des flux de travail de groupe dans Skype pour les entreprises de réponse](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Si un flux de travail est défini en tant que flux de travail géré, alors tous les utilisateurs affectés au rôle CsResponseGroupManager peuvent définir et modifier les heures d’ouverture personnalisées des flux de travail qu’ils gèrent. 
  
> [!IMPORTANT]
> Utilisez un format 24 heures pour les paramètres des applets de commande suivantes (par exemple, 20:00 = 8:00 du soir). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Pour créer une collection d’heures d’ouverture prédéfinie

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis qui prennent en charge Response Group.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. Pour chaque plage horaire unique que vous souhaitez définir, exécutez :
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Pour créer la collection d’heures d’ouverture qui utilise les plages que vous avez définies, exécutez :
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    L’exemple ci-après spécifie les heures d’ouverture suivantes : de 9:00 à 17:00 les jours de la semaine, de 8:00 à 10:00 puis de 14:00 à 18:00 le samedi et fermeture le dimanche :
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Voir aussi

[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[Nouvelle-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
