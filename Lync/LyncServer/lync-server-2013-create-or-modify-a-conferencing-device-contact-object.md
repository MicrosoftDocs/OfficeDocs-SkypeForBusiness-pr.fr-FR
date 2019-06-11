---
title: 'Lync Server 2013: création ou modification d’un objet de contact de périphérique de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b468b2338d115e7b646c28fd4d0b310b6e132d79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Créer ou modifier un objet de contact de l’appareil de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-02_

Pour créer un objet de salle de conférence, commencez par créer un compte d’utilisateur Active Directory pour représenter l’appareil. Vous pouvez ensuite utiliser l’applet de passe **Enable-CsMeetingRoom** pour permettre au compte de fonctionner en tant qu’appareil de conférence. Si vous devez modifier les propriétés d’un appareil de conférence existant, utilisez l’applet de passe **Set-CsMeetingRoom** .

Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Création d’un périphérique de conférence

  - Une fois que vous avez créé le compte d’utilisateur Active Directory qui représente le nouvel appareil de conférence, activez-le à l’aide de l’applet de contrôle **Enable-CsMeetingRoom** . N’oubliez pas d’inclure a) l’identité de l’appareil de conférence, b) du pool de bureaux d’enregistrement dans lequel le compte de la salle sera hébergé et l’adresse SIP doit être attribuée à ce compte. Par exemple :
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Modification d’un appareil de conférence

  - Pour modifier les valeurs de propriétés d’un appareil de conférence existant, utilisez l’applet de passe **Set-CsMeetingRoom** . Par exemple, la commande suivante met à jour le numéro de téléphone (LineUri) associé à un appareil de conférence:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Pour plus d’informations, consultez les rubriques d’aide de l’applet de connexion [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) et de l’applet de connexion [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

