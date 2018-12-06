---
title: (Recommandé) Création d’annuaires de conférences
TOCTitle: (Recommandé) Création d’annuaires de conférences
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63232645
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Recommandé) Création d’annuaires de conférences

 

_**Dernière rubrique modifiée :** 2014-10-03_

Les annuaires des conférences gèrent la mise en correspondance de l’ID alphanumérique de la réunion qu’un participant utilise pour accéder à la conférence lorsqu’il exécute Lync 2013 et l’ID de conférence composé exclusivement de chiffres qu’un participant utilise pour accéder à une conférence rendez-vous. Le format de l’ID de conférence est le suivant :

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

La création de plusieurs annuaires des conférences permet de s’assurer que les ID de conférences restent courts jusqu’à ce qu’une quantité importante de conférences ait été créée. Dans une organisation avec un nombre type de conférences par utilisateur, nous vous conseillons de créer un annuaire des conférences ne dépassant pas 999 utilisateurs dans le pool. Le respect de cette consigne permet en général de limiter la longueur des ID de conférences. Cependant, lorsque le nombre d’annuaires de conférences (tous pools confondus) dépasse 9, la longueur de l'ID de conférence augmente pour permettre la prise en charge de conférences supplémentaires.

## Création d’un annuaire de conférences

1.  Dans Lync Server Management Shell, entrez l’applet de commande suivante :
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    Par exemple, l’applet de commande suivante permet de créer un annuaire de conférences dont l’identité est 42 et qui est hébergé sur le pool atl-cs-001.litwareinc.com :
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## Voir aussi

#### Concepts

[Configuration requise pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Autres ressources

[New-CsConferenceDirectory](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsConferenceDirectory)

