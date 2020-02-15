---
title: Recommandation Créer des annuaires de conférences
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f4a0dbd2caf7e9a04354e0b0670dcbb47adb1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a>Recommandation Créer des annuaires de conférences

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-03_

Les annuaires de conférence maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence en utilisant Lync 2013 et l’ID de conférence numérique uniquement qu’un participant de conférence rendez-vous utilise pour rejoindre la Conférence. Le format de l’ID de conférence est le suivant :

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

La création de plusieurs annuaires de conférences permet de s’assurer que les ID de conférence resteront courts jusqu’à ce qu’une quantité importante de conférences ait été créée. Dans une organisation avec un nombre classique de conférences par utilisateur, nous vous recommandons de créer un annuaire de conférences pour chaque 999 utilisateurs du pool. À l’aide de cette instruction, les ID de conférence peuvent généralement être réduits. Toutefois, une fois que le nombre d’annuaires de conférence (dans les pools) dépasse 9, la longueur de l’ID de conférence augmentera pour prendre en charge des conférences supplémentaires.

<div>

## <a name="creating-a-conference-directory"></a>Création d’un annuaire des conférences

1.  Dans Lync Server Management Shell, tapez l’applet de commande suivante :
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    Par exemple, le code suivant crée un annuaire des conférences avec l’identité 42, hébergée sur le pool atl-cs-001.litwareinc.com :
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exigences en matière de conférence rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

