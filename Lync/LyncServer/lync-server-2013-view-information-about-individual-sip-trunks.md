---
title: 'Lync Server 2013: afficher des informations sur les Trunks SIP individuels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c7d29c7318c8fb6d1cd08775853eb46b1c898d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Afficher des informations sur les lignes SIP individuelles dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Les Trunks SIP sont utilisés pour connecter le réseau téléphonique de Lync Server 2013 voix sur IP avec le réseau téléphonique public commuté. Dans la version précédente du produit, les Trunks permettaient le routage des appels sortants d’un serveur de médiation vers une passerelle RTC et chaque passerelle était limitée à un seul Trunk. Par conséquent, une passerelle RTC et un Trunk SIP étaient essentiellement identiques. Pour les administrateurs, cela signifie qu’ils pouvaient afficher les informations relatives à une ligne SIP individuelle en consultant les informations relatives à la passerelle RTC associée.

Dans Lync Server 2013, il est possible que plusieurs Trunks puissent désormais être attribuées à une seule passerelle PSTN; Cela signifie que les passerelles et les liaisons ne sont plus une seule et même. Cela signifie que les administrateurs doivent utiliser la nouvelle applet de commande [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur un Trunk SIP individuel.

Vous pouvez exécuter l’applet de commande Get-CsTrunk à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>Pour afficher des informations sur toutes vos jonctions SIP

  - La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>Pour afficher les informations relatives à une jonction SIP spécifique

  - La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Affichage des informations pour toutes les lignes SIP attribuées à un pool

  - Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

