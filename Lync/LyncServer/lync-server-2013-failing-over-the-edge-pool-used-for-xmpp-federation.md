---
title: 'Lync Server 2013 : Basculement vers le pool Edge utilisé pour la fédération XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Dans votre organisation, il existe un pool Edge désigné comme pool à utiliser pour la Fédération XMPP. Si ce pool est vers le bas, vous devez le faire basculer sur la Fédération XMPP pour utiliser un pool Edge différent avant que la Fédération XMPP puisse fonctionner de nouveau.

Lorsque vous installez les pools de périphérie et activez la Fédération XMPP, vous pouvez simplifier le processus de reprise après sinistre en configurant des enregistrements SRV DNS externes pour tous vos pools de périphérie pour la Fédération XMPP, au lieu d’une seule. Chacun de ces enregistrements SRV doit avoir un ensemble de priorités différent. Tout le trafic de Fédération XMPP traverse le pool avec l’enregistrement SRV dont la priorité est la plus élevée. Pour plus d’informations sur l’activation et la configuration de la Fédération XMPP, voir [configuration de la Fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

Dans la procédure ci-dessous, EdgePool1 est le pool qui a hébergé la Fédération XMPP et EdgePool2 est le pool qui héberge désormais la Fédération de XMPP.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Échec du pool Edge utilisé pour la Fédération XMPP

1.  Si vous n’avez pas encore déployé un pool Edge (en plus de celui qui est actuellement disponible), vous devez déployer ce pool. Pour plus d’informations, reportez-vous à [déploiement d’un accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  Sur chaque serveur Edge du nouveau pool de périphériques Edge qui hébergera maintenant la Fédération de XMPP (EdgePool2), exécutez l’applet de commande suivante :
    
        Stop-CsWindowsService

3.  Exécutez l’applet de commande suivante pour rediriger l’itinéraire de Fédération XMPP vers EdgePool2 :
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Dans cet exemple, site2 est le site contenant le pool de bords qui héberge désormais l’itinéraire de Fédération XMPP et EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge dans ce pool.

4.  Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la Fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.

5.  Si vous ne disposez pas encore d’un enregistrement DNS SRV pour la Fédération XMPP qui se résout au pool de périphérie qui hébergera maintenant la Fédération de XMPP, vous devez l’ajouter, comme dans l’exemple ci-dessous. Cet enregistrement SRV doit avoir une valeur de port de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Assurez-vous que le pool de bords qui hébergera désormais la Fédération XMPP dispose d’une ouverture externe du port 5269.

7.  Démarrez les services sur tous les serveurs Edge du pool Edge qui hébergeront désormais la Fédération XMPP :
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

