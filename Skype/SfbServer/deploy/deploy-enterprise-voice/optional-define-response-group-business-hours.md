---
title: (Facultatif) Définir les heures d’ouverture de Response Group dans Skype Entreprise
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 'Créez ou modifiez les heures d’ouverture de Response Group, Skype Entreprise Server Voix Entreprise.'
---

# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(Facultatif) Définir les heures d’ouverture de Response Group dans Skype Entreprise 
 
Créez ou modifiez les heures d’ouverture de Response Group, Skype Entreprise Server Voix Entreprise.
  
## <a name="defining-business-hours"></a>Définition des heures d’ouverture

Les paramètres des heures d’ouverture définissent si le flux de travail est disponible pour répondre aux appels et spécifient les actions à prendre lorsque les appels sont passés en dehors des heures d’ouverture. Les administrateurs de Response Group peuvent utiliser la cmdlet **New-CsRgsHoursOfBusiness** afin de créer des plannings prédéfinis disponibles pour un nombre de groupes Response Group quelconque.
  
> [!TIP]
> Lorsque vous créez ou modifiez un flux de travail, vous pouvez spécifier un planning personnalisé s’appliquant uniquement à ce flux de travail. Pour plus d’informations, voir [Conception et création de flux de travail Response Group dans Skype Entreprise](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Si un flux de travail est défini en tant que flux de travail géré, alors tous les utilisateurs affectés au rôle CsResponseGroupManager peuvent définir et modifier les heures d’ouverture personnalisées des flux de travail qu’ils gèrent. 
  
> [!IMPORTANT]
> Utilisez un format 24 heures pour les paramètres des cmdlets suivantes (par exemple, 20:00 = 8:00 du soir). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Pour créer une collection d’heures d’ouverture prédéfinie

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Pour chaque plage horaire unique que vous souhaitez définir, exécutez :
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Pour créer la collection d’heures d’ouverture qui utilise les plages que vous avez définies, exécutez :
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    L’exemple suivant spécifie les heures d’ouverture suivantes : de 9:00 à 17:00 les jours de la semaine, de 8:00 à 10:00 puis de 14:00 à 18:00 le samedi et fermeture le dimanche :
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Voir aussi

[New-CsRgsTimeRange](/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)