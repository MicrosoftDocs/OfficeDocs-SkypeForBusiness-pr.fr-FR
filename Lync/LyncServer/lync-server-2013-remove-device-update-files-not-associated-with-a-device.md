---
title: 'Lync Server 2013 : suppression des fichiers de mise à jour de périphérique non associés à un appareil'
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
ms.openlocfilehash: a21ef2e9dae4c09ce975bd048f628930cd3dfeda
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536441"
---
# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Supprimer les fichiers de mise à jour des périphériques qui ne sont pas associés à un périphérique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Dès que de nouvelles mises à jour des périphériques sont téléchargées sur le système, une règle de mise correspondante est créée. Par défaut, ces nouvelles règles de mise à jour des appareils sont affectées à l’État en attente. Cela signifie que les règles peuvent être téléchargées et installées sur des périphériques de test, mais pas sur des appareils de production, ce qui vous permet de tester les mises à jour avant de les rendre accessibles aux utilisateurs. En fonction des tests, vous acceptez et déployez ou rejetez et supprimez la mise à jour. Lorsque vous rejetez une mise à jour, la mise à jour de l’appareil n’est pas associée à sa règle de mise à jour d’appareil.

<div>


Les fichiers de mise à jour de périphérique qui ne sont plus associés à un périphérique peuvent être supprimés à l’aide de Windows PowerShell et de la cmdlet **Clear-CsDeviceUpdateFile** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


  - Par exemple, la commande suivante supprime toutes les règles de mise à jour des périphériques sur le serveur Web atl-cs-001.litwareinc.com qui ne sont plus associées à un périphérique :
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

