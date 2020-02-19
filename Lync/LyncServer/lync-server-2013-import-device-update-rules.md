---
title: 'Lync Server 2013 : importer des règles de mise à jour des périphériques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb7b911d4f7cd21fd9fbb3ac232048db8691ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Importer des règles de mise à jour des périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les règles de mise à jour des périphériques ne peuvent être importées qu’à l’aide de Windows PowerShell et de l’applet de commande **Import-CsDeviceUpdate** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>Pour importer des règles de mise à jour des périphériques sur un seul serveur Web

  - La commande suivante importe les règles de mise à jour des périphériques vers le serveur Web atl-cs-001.litwareinc.com :
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>Pour importer des règles de mise à jour des périphériques sur tous vos serveurs Web

  - Dans cet exemple, les règles de mise à jour des périphériques sont importées sur tous les serveurs Web déployés dans votre organisation. Pour que cette commande fonctionne, le dossier \\ \\mises\\à jour ATL-FS-001.litwareinc.com doit être partagé et disponible pour tous les serveurs Web.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Afficher des informations sur les règles de mise à jour des périphériques dans Lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Approuver une règle de mise à jour de périphérique dans Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

