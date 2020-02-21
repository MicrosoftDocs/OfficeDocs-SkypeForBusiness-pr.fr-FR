---
title: 'Lync Server 2013 : applets de commande de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf77a99b1f8bbe374a6bb1a5129c6fa1fab84d4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Applets de commande de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Microsoft Lync Server 2013 permet aux utilisateurs de participer à des conférences de deux manières différentes : à l’aide d’une application de conférence telle que Lync 2013 ou en utilisant un téléphone. Les utilisateurs connectés par téléphone ne peuvent pas visualiser de diapositives ni échanger des messages instantanés, mais ils peuvent prendre part à la partie audio d’une conférence.

<div>

## <a name="conferencing-cmdlets"></a>Applets de commande de conférence

Les applets de commande **CsDialInConferencing** servent à configurer toutes les propriétés de conférence rendez-vous, de la spécification des numéros de téléphone que les utilisateurs peuvent appeler pour participer à une conférence aux commandes clavier mises à leur disposition après avoir rejoint une conférence (par exemple, en appuyant sur la touche 6 pour activer ou désactiver le microphone de leur téléphone). La plupart des autres fonctionnalités d’une conférence (par exemple si les utilisateurs peuvent enregistrer la conférence, s’ils peuvent partager des applications pendant la conférence, etc.) sont gérées à l’aide des applets de commande **CsConferencingPolicy**.

**[Applets de commande de conférence rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - <span></span>  
    [Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - <span></span>  
    [New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - <span></span>  
    [New-applet csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - <span></span>  
    [Remove-applet csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Set-applet csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

**[Applets de commande de conférence Web dans Lync Server 2013](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-applet csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - <span></span>  
    [Remove-applet csconferencedisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - <span></span>  
    [Set-applet csconferencedisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - <span></span>  
    [New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - <span></span>  
    [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - <span></span>  
    [New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - <span></span>  
    [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - <span></span>  
    [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - <span></span>  
    [Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - <span></span>  
    [Test-applet cswebscheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Blog Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

