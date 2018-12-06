---
title: "Lync Server 2013 : Rest. du pool Edge util. pour la féd. XMPP ou Lync Server "
TOCTitle: Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49891560
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Lorsqu’un pool Edge en échec qui hébergeait la fédération a été remis en ligne, suivez cette procédure pour restaurer l’itinéraire de fédération Lync Server et/ou l’itinéraire de fédération XMPP pour réutiliser ce pool Edge restauré.

## Restauration de la fédération sur un pool Edge restauré

1.  Sur le pool Edge de nouveau disponible, lancez les Services Edge.

2.  Si vous voulez restaurer l’itinéraire de fédération Lync Server pour utiliser le serveur Edge restauré, procédez comme suit :
    
      - Sur un serveur frontal, ouvrez le générateur de topologie. Développez **Pools Edge** , puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés** .
    
      - Dans **Modifier les propriétés** , sous **Général** , désactivez l’option **Activer la fédération pour ce pool Edge (Port 5061)** . Cliquez sur **OK** .
    
      - Développez **Pools Edge** , puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge d’origine que vous voulez réutiliser pour la fédération. Sélectionnez **Modifier les propriétés** .
    
      - Dans **Modifier les propriétés** , sous **Général** , sélectionnez l’option **Activer la fédération pour ce pool Edge (Port 5061)** . Cliquez sur **OK** .
    
      - Cliquez sur **Action** , sélectionnez **Topologie** , puis **Publier** . Dans **Publier la topologie** , cliquez sur **Suivant** lorsque vous y êtes invité. Une fois la publication terminée, cliquez sur **Terminer** .
    
      - Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **Installer ou mettre à jour le système Lync Server** , puis cliquez sur **Configurer ou supprimer les composants Lync Server** . Cliquez sur **Réexécuter** .
    
      - Dans la page Configurer les composants Lync Server, cliquez sur **Suivant** . L’écran de résumé affiche les actions lorsqu’elles sont exécutées. Une fois le déploiement terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.

3.  Si vous voulez restaurer l’itinéraire de fédération XMPP pour utiliser le serveur Edge restauré, procédez comme suit :
    
      - Exécutez l’applet de commande suivante pour pointer de nouveau l’itinéraire de fédération XMPP sur le pool Edge qui héberge désormais la fédération XMPP (dans cet exemple, EdgeServer1) :
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Dans cet exemple, Site1 représente le site qui contient le pool Edge qui hébergera désormais l’itinéraire de fédération XMPP, et EdgeServer1.contoso.com représente le nom de domaine complet (FQDN) d’un serveur Edge de ce pool.
    
      - Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP qui aboutit au pool Edge qui héberge désormais la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir une valeur de port de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.
    
      - Vérifiez que le port 5269 du pool Edge qui héberge désormais la fédération XMPP est ouvert de façon externe.

4.  Si les pools frontaux ont continué à s’exécuter sur le site contenant le pool Edge qui a échoué et a été restauré, vous devez mettre à jour les services de conférence web et de conférence A/V sur ces pools frontaux pour réutiliser les pools Edge sur leur site local. Pour plus d’informations, reportez-vous à [Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md) (contenu éventuellement en anglais).

5.  Si le pool frontal du site où le pool Edge a échoué échoue également, vous pouvez désormais utiliser Invoke–CsPoolFailback pour restaurer le pool frontal.

## Voir aussi

#### Tâches

[Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  

#### Concepts

[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

