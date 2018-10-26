---
title: "(Facul.) Déf. des gr. de congés des gr. Response Group dans Lync Server 2013"
TOCtitle: "(Facul.) Déf. des gr. de congés des gr. Response Group dans Lync Server 2013"
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49891357
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Facultatif) Définition des groupes de congés des groupes Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-07_

Les paramètres relatifs aux congés définissent les jours de fermeture d’un groupe Response Group et spécifient l’action à effectuer pendant ces jours. Une période de congé est un ensemble de congés qui s’applique à un groupe Response Group.

> [!NOTE]  
> Si un flux de travail est défini en tant que flux de travail géré, tout utilisateur auquel est affecté le rôle CsResponseGroupManager peut définir et modifier les congés des flux de travail dont il assure la gestion.

## Pour créer une période de congé

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour chaque congé que vous souhaitez définir, exécutez :
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    Pour créer la période de congé contenant les congés définis, exécutez :
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    L’exemple suivant présente une période de congé incluant deux congés :
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

## Voir aussi

#### Concepts

[Création ou modification d’un flux de travail de groupe de recherche dans Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Création ou modification d’un flux de travail interactif dans Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### Autres ressources

[New-CsRgsHoliday](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHolidaySet)

