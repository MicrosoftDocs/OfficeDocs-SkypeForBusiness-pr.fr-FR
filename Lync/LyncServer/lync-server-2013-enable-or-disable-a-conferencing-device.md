---
title: 'Lync Server 2013 : activation ou désactivation d’un périphérique de conférence'
description: 'Lync Server 2013 : activer ou désactiver un périphérique de conférence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761bc19536c889cced68ff586753f6800df0da59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558080"
---
# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Activer ou désactiver un périphérique de conférence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Activer et désactiver un périphérique de conférence à l’aide de la cmdlet **Enable-CsMeetingRoom** et de l’applet de commande **Disable-CsMeetingRoom** . Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Activation d’un périphérique de conférence

  - Pour activer un périphérique de conférence, utilisez la cmdlet **Enable-CsMeetingRoom** . Lors de l’activation d’un périphérique de conférence, vous devez inclure a) l’identité de l’appareil de conférence, b) le pool de serveurs d’inscriptions où le compte de salle sera hébergé et c) l’adresse SIP à attribuer à ce compte.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Désactivation d’un périphérique de conférence

  - Pour désactiver un périphérique de conférence, utilisez l’applet de commande **Disable-CsMeetingRoom** . Assurez-vous que vous spécifiez l’identité du périphérique de conférence à désactiver :
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) et la cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

