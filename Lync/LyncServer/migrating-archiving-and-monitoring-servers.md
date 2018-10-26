---
title: Migration des serveurs d’archivage et de surveillance
TOCTitle: Migration des serveurs d’archivage et de surveillance
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205015(v=OCS.15)
ms:contentKeyID: 49297786
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des serveurs d’archivage et de surveillance

 

_**Dernière rubrique modifiée :** 2012-10-02_

Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement Lync Server 2010, vous pouvez les déployer dans votre environnement Lync Server 2013 après avoir fait migrer vos pools frontaux. Cependant, si les fonctionnalités d’archivage et de surveillance sont critiques pour votre organisation, nous vous recommandons d’ajouter le serveur d’archivage et le serveur de surveillance à votre pool pilote Lync Server 2013 avant de migrer pour que la fonctionnalité soit disponible pendant le processus de migration.

Si vous voulez la fonctionnalité d’archivage et de surveillance au cours du processus de migration, gardez les considérations suivantes à l’esprit :

  - Les données d’archivage et de surveillance ne sont pas déplacées vers le déploiement de Lync Server 2013. Les données que vous sauvegardez avant de désaffecter l’environnement hérité correspondent à votre historique d’activité dans l’environnement Lync Server 2010.

  - La version Lync Server 2010 du serveur d’archivage et du serveur de surveillance peut être uniquement associée avec un pool frontal Lync Server 2010. Dans Lync Server 2013, les rôles serveur d’archivage et de surveillance ont été intégrés en tant que services dans le pool frontal de Lync Server 2013.

  - Pendant la coexistence de votre déploiement hérité et de votre déploiement de Lync Server 2013, la version Lync Server 2010 du serveur d’archivage et du serveur de surveillance collecte des données pour les utilisateurs hébergés sur les pools Lync Server 2010. L’archivage et la surveillance dans Lync Server 2013 collectent les données pour les utilisateurs hébergés sur les pools Lync Server 2013.
    
    > [!NOTE]  
    > Au cours de la phase de migration où vous continuez à utiliser votre serveur Edge hérité avec le nouveau pool pilote Lync Server 2013, la version Lync Server 2010 du serveur d’archivage continue de collecter des données pour les utilisateurs hébergés sur les pools Lync Server 2010 et l’archivage dans Lync Server 2013 collecte les données pour les utilisateurs hébergés sur les pools Lync Server 2013.

  - Si vous utilisez une solution d’archivage et de surveillance tierce conjointement avec l’archivage et à la surveillance dans Lync Server 2013, demandez à votre fournisseur quand et comment intégrer la solution tierce à Lync Server 2013.

