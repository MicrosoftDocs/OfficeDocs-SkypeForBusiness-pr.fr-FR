---
title: Migration des serveurs d’archivage et de surveillance
TOCTitle: Migration des serveurs d’archivage et de surveillance
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49891433
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des serveurs d’archivage et de surveillance

 

_**Dernière rubrique modifiée :** 2012-10-02_

Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans Office Communications Server 2007 R2, vous pouvez les déployer dans votre environnement Lync Server 2013 après avoir migré vos pools frontaux. Cependant, si les fonctionnalités d’archivage et de surveillance sont critiques pour votre organisation, nous vous recommandons d’ajouter l’archivage et la surveillance à votre pool pilote avant la migration pour que la fonctionnalité soit disponible pendant le processus de migration.

Si vous voulez que les fonctionnalités d’archivage et de surveillance soient disponibles au cours de la phase de migration et de coexistence, gardez les éléments suivants à l’esprit :

  - Les données d’archivage et de surveillance ne sont pas déplacées vers le déploiement Lync Server 2013. Les données que vous sauvegardez avant de désactiver l’environnement hérité sera votre historique d’activité dans Office Communications Server 2007 R2.

  - La version Office Communications Server 2007 R2 du serveur d’archivage et du serveur de surveillance peut être uniquement associée avec un pool frontal Office Communications Server 2007 R2. Dans Lync Server 2013, les rôles serveur d’archivage et de surveillance ont été intégrés en tant que services dans le pool frontal de Lync Server 2013.

  - Pendant le moment où votre déploiement hérité et votre déploiement Lync Server 2013 coexistent, la version Office Communications Server 2007 R2 du serveur d’archivage et du serveur de surveillance collectent des données pour les utilisateurs hébergés sur les pools Office Communications Server 2007 R2. La version Lync Server 2013 du serveur d’archivage et du serveur de surveillance collectent des données pour les utilisateurs hébergés sur les pools Lync Server 2013.
    
    > [!NOTE]  
    > Au cours de la phase de migration pendant que vous continuez à utiliser le serveur Edge hérité avec le nouveau pool pilote Lync Server 2013, la version Office Communications Server 2007 R2 du serveur d’archivage continue de collecter des données pour les utilisateurs hébergés sur les pools Office Communications Server 2007 R2 et la version Lync Server 2013 du serveur d’archivage les données pour les utilisateurs hébergés sur les pools Lync Server 2013.

  - Si vous utilisez une solution d’archivage et de surveillance tierce conjointement au serveur d’archivage et au serveur de surveillance, demandez à votre fournisseur quand et comment intégrer la solution tierce à Lync Server 2013.

