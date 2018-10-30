---
title: "Lync Server 2013 : Dépl. de LS 2013 SE dans une instance exist. de LS 2013 E"
TOCTitle: Déploiement de Lync Server 2013 Standard Edition dans une instance existante de Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398112(v=OCS.15)
ms:contentKeyID: 49296131
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement de Lync Server 2013 Standard Edition dans une instance existante de Lync Server 2013 Enterprise

 

_**Dernière rubrique modifiée :** 2012-10-01_

Déployer un serveur Standard Edition dans un déploiement Enterprise Edition revient au même que de déployer des rôles serveur supplémentaires. Un serveur Standard Edition peut être déployé sur un autre site, ce qui permet d’héberger les utilisateurs de ce site sur le serveur Standard Edition au lieu du pool de serveurs frontaux sur un réseau étendu (WAN). Les procédures pour installer le nouveau site et les serveurs sur ce site sont déjà définies dans d’autres sections de la documentation [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md).

**Pour définir un nouveau site**

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **Nouveau site central** .

3.  Dans la page **Identifier le site** , indiquez le nom du site et éventuellement entrez sa description.

4.  Suivez les procédures pour définir le reste de la topologie du site. Pour plus d’informations, reportez-vous à [Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Publiez la topologie mise à jour. Pour plus d’informations, reportez-vous à [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Configurez et installez un serveur Standard Edition.
    
    > [!CAUTION]  
    > Si vous avez déployé un environnement avec seulement un serveur Standard Edition, vous avez dû commencer le processus de configuration à l’aide de l’Assistant Déploiement de Lync Server en utilisant le lien <strong>Préparer d’abord le serveur Standard Edition</strong> pour installer les fichiers de base de données initiaux sur le nouveau serveur Standard Edition. <strong>Ne suivez pas</strong> cette procédure pour installer un serveur Standard Edition dans un déploiement Lync Server 2013 existant.
