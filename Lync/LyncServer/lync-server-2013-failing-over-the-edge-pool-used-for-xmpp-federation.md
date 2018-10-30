---
title: "Lync Server 2013 : Basculement vers le pool Edge utilisé pour la féd. XMPP"
TOCTitle: Basculement vers le pool Edge utilisé pour la fédération XMPP
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49891359
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Dans votre organisation, il existe un pool de serveurs Edge désigné en tant que pool à utiliser pour la fédération XMPP. Si ce pool ne fonctionne pas, vous devez effectuer un basculement de la fédération XMPP et utiliser un autre pool de serveurs Edge pour permettre à la fédération XMPP de fonctionner à nouveau.

Quand vous installez des pools de serveurs Edge et que vous activez la fédération XMPP, vous pouvez simplifier le processus de récupération d’urgence en configurant des enregistrements SRV DNS externes pour tous les pools de serveurs Edge (au lieu d’un seul) de la fédération XMPP. Chacun de ces enregistrements SRV doit avoir une priorité distincte. Tout le trafic de la fédération XMPP passe par le pool dont l’enregistrement SRV a la priorité la plus élevée. Pour plus d’informations sur l’activation et la configuration de la fédération XMPP, reportez-vous à [Configuration de la fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

Dans la procédure suivante, EdgePool1 est le pool qui a hébergé à l’origine la fédération XMPP. EdgePool2 est le pool qui va désormais héberger la fédération XMPP.

## Basculement du pool de serveurs Edge utilisé pour la fédération XMPP

1.  Si vous n’avez pas d’autre pool de serveurs Edge déployé (en plus de celui qui est actuellement en panne), déployez ce pool. Pour plus d’informations, reportez-vous à [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  Sur chaque serveur Edge du nouveau pool de serveurs Edge qui va héberger la fédération XMPP (EdgePool2), exécutez l’applet de commande suivante :
    
        Stop-CsWindowsService

3.  Exécutez l’applet de commande suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers EdgePool2 :
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Dans cet exemple, Site2 est le site contenant le pool de serveurs Edge qui va héberger l’itinéraire de fédération XMPP. EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.

4.  Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.

5.  Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP qui aboutit au pool Edge qui héberge désormais la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir une valeur de port de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Vérifiez que le port 5269 du pool Edge qui héberge désormais la fédération XMPP est ouvert de façon externe.

7.  Démarrez les services de tous les serveurs Edge du pool de serveurs Edge qui va héberger la fédération XMPP :
    
        Start-CsWindowsService

