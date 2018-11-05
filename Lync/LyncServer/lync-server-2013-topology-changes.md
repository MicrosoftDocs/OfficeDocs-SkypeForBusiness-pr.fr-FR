---
title: Modifications de la topologie dans Lync Server 2013
TOCTitle: Modifications de la topologie
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49891463
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifications de la topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-02_

Les points à prendre en compte et les conditions requises concernant les topologies Lync Server 2013 sont différents de ceux des versions précédentes, comme décrit dans cette section.

## Nouvelle architecture de pools frontaux

Dans Lync Server 2013, l’architecture des pools de serveurs frontauxEnterprise Edition est une architecture de systèmes distribués.

Avec cette nouvelle architecture, la base de données principale n’est plus le magasin de données en temps réel dans un pool. Les informations relatives à un utilisateur particulier sont conservées sur trois serveurs frontaux dans le pool. Pour chaque utilisateur, un serveur frontal joue le rôle de maître pour les informations de cet utilisateur et deux autres serveurs frontaux servent de réplicas. En cas de défaillance d’un serveur frontal, un autre serveur frontal qui servait de réplica est promu automatiquement en maître.

Cela se produisant en arrière-plan, il n’est pas nécessaire que les administrateurs sachent quels serveurs frontaux sont les maîtres pour chaque utilisateur. Cette distribution du stockage de données améliore les performances et l’extensibilité au sein du pool et élimine le point de défaillance unique d’un serveur principal.

Le serveur principal sert de stockage de sauvegarde pour les données utilisateur et de conférence, et est également le stockage principal pour d’autres bases de données telles que la base de données Response Group.

Ces améliorations sont également synonymes de changements dans la manière dont vous planifiez et maintenez vos pools. Nous vous conseillons de faire en sorte que tous vos pools de serveurs frontauxEnterprise Edition incluent au moins trois serveurs frontaux afin de fournir la quantité totale de réplicas pour laquelle l’architecture de pool de serveurs frontaux a été conçue. Par ailleurs, vous devez respecter certaines procédures lors de l’ajout ou de la suppression de serveurs d’un pool de serveurs frontaux ou lors de la mise à niveau de serveurs. Pour plus d’informations, reportez-vous à [Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

## Modifications de topologie de rôles serveur

Certains rôles serveur qui s’exécutaient auparavant sur des serveurs distincts sont maintenant consolidés dans le rôle de serveur frontal, ce qui vous permet de faire des économies sur les coûts matériels.

  - Dans Lync Server 2013, le serveur de conférence A/V est toujours colocalisé avec le serveur frontal.

  - Les serveurs frontaux de surveillance et d’archivage sont désormais toujours colocalisés avec le serveur frontal. Ces deux fonctionnalités nécessitent toujours une base de données principale distincte, qui peut être colocalisée sur le même serveur que la base de données principale du pool frontal ou peut être hébergée sur des serveurs principaux distincts.

  - Le serveur de conversations permanentes est maintenant un rôle serveur. Dans Microsoft Lync Server 2010, le serveur Group Chat était une application tierce approuvée pour Microsoft Lync Server 2010. Dans Lync Server 2013, la fonctionnalité de serveur de conversations permanentes est mise en œuvre à l’aide de trois nouveaux rôles serveur :
    
      - **PersistentChatService** : principaux services de serveur de conversations permanentes mis en œuvre en tant que rôle frontal
    
      - **PersistentChatStore** : rôle serveur principal
    
      - **PersistentChatComplianceStore** : rôle serveur principal pour la conformité de conversation permanente

