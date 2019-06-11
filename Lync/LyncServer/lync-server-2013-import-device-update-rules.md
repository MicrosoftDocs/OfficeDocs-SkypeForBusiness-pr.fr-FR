---
title: 'Lync Server 2013: importer les règles de mise à jour de périphériques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cef7e14806a1f4c7853d157d0c4ce304583b9720
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Importer des règles de mise à jour de périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Les règles de mise à jour d’appareils peuvent être importées uniquement à l’aide de Windows PowerShell et de l’applet **de cmdlet Import-CsDeviceUpdate** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>Pour importer des règles de mise à jour de périphériques sur un serveur Web unique

  - La commande suivante importe les règles de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>Pour importer des règles de mise à jour de périphériques sur tous vos serveurs Web

  - Dans cet exemple, les règles de mise à jour d’appareil sont importées sur tous les serveurs Web déployés dans votre organisation. Pour que cette commande fonctionne, les mises \\ \\à\\jour de ATL-FS-001.litwareinc.com de dossiers doivent être partagées et disponibles pour tous les serveurs Web.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Afficher des informations sur les règles de mise à jour des appareils dans Lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Approuver une règle de mise à jour d’appareil dans Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

