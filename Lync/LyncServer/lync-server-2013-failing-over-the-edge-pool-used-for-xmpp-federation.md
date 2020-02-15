---
title: 'Lync Server 2013 : basculement du pool de serveurs Edge utilisé pour la Fédération XMPP'
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
ms.openlocfilehash: f3957f3fc5a315c5b661ddeec4ea83b8e7f0eab0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Dans votre organisation, il existe un pool de serveurs Edge désigné en tant que pool à utiliser pour la fédération XMPP. Si ce pool tombe en panne, vous devez effectuer un basculement de la fédération XMPP et utiliser un autre pool de serveurs Edge pour permettre à la fédération XMPP de fonctionner à nouveau.

Quand vous installez des pools de serveurs Edge et que vous activez la fédération XMPP, vous pouvez simplifier le processus de récupération d’urgence en configurant des enregistrements SRV DNS externes pour tous les pools de serveurs Edge (au lieu d’un seul) de la fédération XMPP. Chacun de ces enregistrements SRV doit avoir une priorité distincte. Tout le trafic de la fédération XMPP passe par le pool dont l’enregistrement SRV a la priorité la plus élevée. Pour plus d’informations sur l’activation et la configuration de la Fédération XMPP, voir [configuration de la Fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

Dans la procédure suivante, EdgePool1 est le pool qui a hébergé à l’origine la fédération XMPP. EdgePool2 est le pool qui va désormais héberger la fédération XMPP.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Basculement du pool de serveurs Edge utilisé pour la fédération XMPP

1.  Si vous n’avez pas d’autre pool de serveurs Edge déployé (en plus de celui qui est actuellement en panne), déployez ce pool. Pour plus d’informations, reportez-vous à la rubrique [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  Sur chaque serveur Edge du nouveau pool de serveurs Edge qui va héberger la fédération XMPP (EdgePool2), exécutez l’applet de commande suivante :
    
        Stop-CsWindowsService

3.  Exécutez l’applet de commande suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers EdgePool2 :
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Dans cet exemple, Site2 est le site contenant le pool de serveurs Edge qui va héberger l’itinéraire de fédération XMPP. EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.

4.  Sur le serveur DNS externe, modifiez l’enregistrement DNS A afin que la fédération XMPP pointe vers EdgeServer2.contoso.com.

5.  Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP correspondant au pool de serveurs Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. La valeur du port de cet enregistrement SRV doit être 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Assurez-vous que le port externe 5269 du pool de serveurs Edge qui va héberger la fédération XMPP est ouvert.

7.  Démarrez les services de tous les serveurs Edge du pool de serveurs Edge qui va héberger la fédération XMPP :
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

