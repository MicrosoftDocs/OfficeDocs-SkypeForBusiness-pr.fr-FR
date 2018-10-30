---
title: 'Lync Server 2013 : démarrer des services sur les serveurs'
TOCTitle: Démarrer des services sur les serveurs
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413059(v=OCS.15)
ms:contentKeyID: 49299399
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Démarrer des services sur les serveurs pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-09-03_

Pour réussir à effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations déléguées appropriées. Pour plus d’informations sur la délégation d’autorisations, consultez la rubrique [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Après avoir installé le magasin de configurations local sur vos serveurs, installé les composants Lync Server 2013 et configuré les certificats sur un serveur frontal ou des serveur frontal, vous devez démarrer les services Lync Server 2013 sur le serveur. Utilisez la procédure suivante pour démarrer les services de chaque serveur frontal de votre déploiement.

## Pour démarrer les services sur un serveur frontal ou Standard Edition

1.  Dans l’Assistant Déploiement de Lync Server, sur la page **Lync Server 2013**, cliquez sur le bouton **Exécuter** en regard de **Étape 4 : démarrer les services** .

2.  Dans la page **Démarrer les services** , cliquez sur **Suivant** pour démarrer les services Lync Server sur le serveur.

3.  Dans la page **Exécution de commandes** , une fois que tous les services ont démarré correctement, cliquez sur **Terminer** .
    
    > [!IMPORTANT]  
    > Pour vérifier que les services ont bien démarré, nous vous recommandons d’utiliser la commande de démarrage des services sur le serveur. Cependant, il est possible qu’elle n’indique pas l’état actuel du service. Nous vous recommandons de suivre l’étape <strong>État des services (facultatif)</strong> juste après <strong>Démarrage de services</strong> pour ouvrir la console MMC (Microsoft Management Console) et confirmer que les services ont correctement démarré. Si un service Lync Server n’a pas démarré, vous pouvez cliquer avec le bouton droit sur ce service dans la console MMC (Microsoft Management Console), puis cliquer sur <strong>Démarrer</strong> .
