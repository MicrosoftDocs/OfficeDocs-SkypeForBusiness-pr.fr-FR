---
title: 'Lync Server 2013 : Prise en charge du protocole IP et de gestion réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285ed0d383b09276979ad6e29c390e2fc22a1caf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Prise en charge du protocole IP et de gestion réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Lync Server 2013 prend en charge les protocoles IP et réseau suivants :

  - **Protocoles IP.**    Lync Server 2013 prend en charge les protocoles IP version 4 (IPv4) ou IP version 6 (IPv6) pour le réseau du serveur.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 peut fonctionner dans un réseau doté d’une pile IP double activée.

    
    </div>

  - **Protocoles de transport SIP.**    De manière générale, le protocole SIP peut utiliser au moins trois types de transport : protocole UDP (User Datagram Protocol), protocole TCP (Transmission Control Protocol) et TLS (Transport Layer Security). Dans la configuration de transport SIP par défaut, le protocole TLS s’exécute sur TCP. TLS est utilisé au sein du réseau Lync Server 2013. Au bord du réseau, Lync Server 2013 peut interagir via TCP. Lync Server 2013 ne prend pas en charge le protocole UDP pour les transports SIP, car il ne respecte pas les normes minimales pour la sécurité, la fiabilité et l’évolutivité des communications d’entreprise. Pour plus d’informations, reportez-vous à l’article de blog NextHop, «au protocole UDP ou pas à UDP [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369), qui est la question «à.
    
    <div>
    

    > [!NOTE]  
    > Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

