---
title: 'Lync Server 2013 : création ou modification d’un objet contact de l’appareil de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ff0a3dbc50b48994752e48ea8889508f2376068
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506171"
---
# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Création ou modification d’un objet contact de périphérique de conférence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-02_

Pour créer un objet de salle de conférence, commencez par créer un compte d’utilisateur Active Directory pour représenter l’appareil. Ensuite, utilisez l’applet de commande **Enable-CsMeetingRoom** pour permettre à ce compte de fonctionner en tant que périphérique de conférence. Si vous devez modifier les propriétés d’un périphérique de conférence existant, utilisez la cmdlet **Set-CsMeetingRoom** .

Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Création d’un périphérique de conférence

  - Une fois que vous avez créé le compte d’utilisateur Active Directory qui représente le nouveau périphérique de conférence, activez-le à l’aide de la cmdlet **Enable-CsMeetingRoom** . N’oubliez pas d’inclure a) l’identité de l’appareil de conférence, b) le pool de serveurs d’inscriptions dans lequel le compte de salle sera hébergé et c, l’adresse SIP à attribuer à ce compte. Par exemple :
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Modification d’un périphérique de conférence

  - Pour modifier les valeurs des propriétés d’un périphérique de conférence existant, utilisez la cmdlet **Set-CsMeetingRoom** . Par exemple, la commande suivante met à jour le numéro de téléphone (LineUri) associé à un périphérique de conférence :
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) et la cmdlet [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

