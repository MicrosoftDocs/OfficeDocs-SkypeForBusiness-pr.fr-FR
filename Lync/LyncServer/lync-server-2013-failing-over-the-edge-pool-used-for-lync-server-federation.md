---
title: "Lync Server 2013 : Basc. vers le pool Edge utilisé pour la féd. Lync Server"
TOCTitle: Basculement vers le pool Edge utilisé pour la fédération Lync Server
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49891368
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-17_

Si le pool de serveurs Edge où la fédération Lync Server est configurée ne fonctionne pas, vous devez modifier la fédération de manière à ce qu’elle utilise un pool de serveurs Edge différent pour la rendre opérationnelle.

## Basculement du pool de serveurs Edge utilisé pour la fédération Lync Server

1.  Sur un serveur frontal, ouvrez le générateur de topologie. Développez **Pools Edge** , puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés** .

2.  Dans **Modifier les propriétés** , sous **Général** , désactivez l’option **Activer la fédération pour ce pool Edge (Port 5061)** . Cliquez sur **OK** .

3.  Développez **Pool de serveurs Edge** , puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous souhaitez à présent utiliser pour la fédération. Sélectionnez **Modifier les propriétés** .

4.  Dans **Modifier les propriétés** , sous **Général** , sélectionnez l’option **Activer la fédération pour ce pool Edge (Port 5061)** . Cliquez sur **OK** .

5.  Cliquez sur **Action** , sélectionnez **Topologie** , puis **Publier** . Dans **Publier la topologie** , cliquez sur **Suivant** lorsque vous y êtes invité. Une fois la publication terminée, cliquez sur **Terminer** .

6.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **Installer ou mettre à jour le système Lync Server** , puis cliquez sur **Configurer ou supprimer les composants Lync Server** . Cliquez sur **Réexécuter** .

7.  Dans la page Configurer les composants Lync Server, cliquez sur **Suivant** . L’écran de résumé affiche les actions lorsqu’elles sont exécutées. Une fois le déploiement terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.
    
    Si le site contenant le pool de serveurs Edge ayant échoué contient des serveurs frontaux qui sont encore en cours d’exécution, vous devez mettre à jour le service de conférence web et le service de conférence A/V sur ces pools de serveurs frontaux afin d’utiliser un pool de serveurs Edge dans un site distant qui est encore en cours d’exécution. Pour plus d’informations, reportez-vous à [Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

## Voir aussi

#### Tâches

[Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  

#### Concepts

[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

