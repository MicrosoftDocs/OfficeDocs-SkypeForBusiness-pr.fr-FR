---
title: 'Lync Server 2013 : (facultatif) définir les heures d’ouverture d’un groupe Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b02ce8434d7912d81855725aa86a11fa377ce44
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a>Module Définition des heures d’ouverture d’un groupe Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

<div>

## <a name="defining-business-hours"></a>Définition des heures d’ouverture

Les paramètres des heures d’ouverture définissent si le flux de travail est disponible pour répondre aux appels et spécifient les actions à prendre lorsque les appels sont passés en dehors des heures d’ouverture. Les administrateurs de Response Group peuvent utiliser la cmdlet **New-CsRgsHoursOfBusiness** afin de créer des plannings prédéfinis disponibles pour un nombre de groupes Response Group quelconque.

<div>


> [!TIP]  
> Lorsque vous créez ou modifiez un flux de travail, vous pouvez spécifier un planning personnalisé s’appliquant uniquement à ce flux de travail. Pour plus d’informations, voir <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">créer ou modifier un flux de travail de groupe de recherche dans Lync server 2013</A> ou <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">créer ou modifier un flux de travail interactif dans Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Si un flux de travail est défini en tant que flux de travail géré, alors tous les utilisateurs affectés au rôle CsResponseGroupManager peuvent définir et modifier les heures d’ouverture personnalisées des flux de travail qu’ils gèrent.



</div>

<div>


> [!IMPORTANT]  
> Utilisez un format 24 heures pour les paramètres des cmdlets suivantes (par exemple, 20:00 = 8:00 du soir).



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a>Pour créer une collection d’heures d’ouverture prédéfinie

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Pour chaque plage horaire unique que vous souhaitez définir, exécutez :
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    Pour créer la collection d’heures d’ouverture qui utilise les plages que vous avez définies, exécutez :
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    L’exemple suivant spécifie les heures d’ouverture suivantes : de 9:00 à 17:00 les jours de la semaine, de 8:00 à 10:00 puis de 14:00 à 18:00 le samedi et fermeture le dimanche :
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification d’un flux de travail de groupe de recherche dans Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Création ou modification d’un flux de travail interactif dans Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

