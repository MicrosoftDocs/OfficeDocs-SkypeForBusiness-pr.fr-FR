---
title: 'Lync Server 2013 : prise en charge du protocole IP et du réseau'
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
ms.openlocfilehash: ea7312cff97b6c339d960c14902e912f6e2e7bae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Prise en charge des protocoles IP et réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Lync Server 2013 prend en charge les protocoles IP et de mise en réseau suivants :

  - **Protocoles IP.**    Lync Server 2013 prend en charge IP version 4 (IPv4) ou IP version 6 (IPv6) pour le réseau de serveurs.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 peut fonctionner dans un réseau avec une pile IP double activée.

    
    </div>

  - **Protocoles de transport SIP.**    De manière générique, SIP peut utiliser au moins trois types de transport : UDP (User Datagram Protocol), TCP (Transmission Control Protocol) et TLS (Transport Layer Security). Dans la configuration de transport SIP par défaut, le protocole TLS prévaut sur TCP. TLS est utilisé dans le réseau Lync Server 2013. Sur le serveur Edge du réseau, Lync Server 2013 peut interagir sur TCP. Lync Server 2013 ne prend pas en charge le protocole UDP pour le transport SIP car il ne respecte pas les normes minimales pour la sécurité, la fiabilité et l’évolutivité des communications d’entreprise. Pour plus d’informations, reportez-vous à l’article du blog NextHop, « vers UDP, ou non à UDP [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369), qui est la question » à l’adresse.
    
    <div>
    

    > [!NOTE]  
    > Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

