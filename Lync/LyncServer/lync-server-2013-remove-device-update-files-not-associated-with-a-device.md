---
title: 'Lync Server 2013 : supprimer les fichiers de mise à jour d’appareils non associés à un appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a2579360fbb4af8d6f3c491f5a56c380b593d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Supprimer les fichiers de mise à jour des appareils non associés à un appareil dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Chaque fois que de nouvelles mises à jour de périphériques sont téléchargées sur le système, une règle de mise à jour d’appareil correspondante est créée. Par défaut, ces nouvelles règles de mise à jour de l’appareil sont affectées à l’État en attente. Cela signifie que les règles peuvent être téléchargées et installées sur les appareils de test, mais pas sur les appareils de production, ce qui vous permet de tester les mises à jour avant de les rendre accessibles aux utilisateurs. D’après les tests, vous acceptez et déployez ou rejetez et supprimez la mise à jour. Lorsque vous refusez une mise à jour, la mise à jour de l’appareil est désassociée de sa règle de mise à jour de l’appareil.

<div>


Les fichiers de mise à jour d’appareil qui ne sont plus associés à un appareil peuvent être supprimés à l’aide de Windows PowerShell et de l’applet **de cmdlet Clear-CsDeviceUpdateFile** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».



</div>

<div>


  - Par exemple, la commande suivante supprime toutes les règles de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com qui ne sont plus associées à un appareil :
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

