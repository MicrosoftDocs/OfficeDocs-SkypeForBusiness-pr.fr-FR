---
title: Vue d’ensemble du processus de sauvegarde et de restauration
TOCTitle: Vue d’ensemble du processus de sauvegarde et de restauration
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202192(v=OCS.15)
ms:contentKeyID: 53095549
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du processus de sauvegarde et de restauration

 

_**Dernière rubrique modifiée :** 2013-03-26_

Cette section fournit une vue d’ensemble du fonctionnement du processus de sauvegarde et de restauration pour Lync Server 2013. Vous utilisez le même processus pour tous les serveurs Standard Edition et les serveurs Enterprise Edition, quel que soit leur emplacement.

En général, le processus de sauvegarde fonctionne comme suit :

  - Vous créez un emplacement de sauvegarde en tant que dossier partagé sur un ordinateur autonome qui ne fait partie d’aucun pool. L’emplacement de la sauvegarde est référencé dans **$Backup**.

  - De manière régulière et planifiée, vous sauvegardez toutes les bases de données Lync Server et tous les magasins de fichiers décrits dans [Besoins de sauvegarde et de restauration dans Lync Server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md) en appliquant les procédures décrites dans [Sauvegarde de Lync Server](lync-server-2013-backing-up-lync-server.md). Le magasin central de gestion inclut tous les paramètres et configurations de serveur.

  - Chaque fois que vous exécutez une sauvegarde ultérieure, vous créez un nouveau dossier partagé et modifiez le chemin d’accès que **$Backup** référence.

En général, le processus de restauration fonctionne comme suit :

  - Lorsqu’une défaillance ou une panne se produit, vous restaurez les données situées à l’emplacement référencé par **$Backup** sur des ordinateurs nouveaux ou nettoyés.
    
    > [!IMPORTANT]  
    > Ce processus de restauration ne restaure pas les données sur un état de serveur existant. C’est-à-dire que ce processus requiert que le serveur soit nettoyé ou nouveau.

  - Pour faire en sorte que vos informations utilisateur et de conférence soient récupérables au point de défaillance, vous pouvez mettre en œuvre une topologie de récupération d’urgence avec des pools frontaux associés, comme décrit dans [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Outre cette option, Lync Server prend en charge uniquement le mode de récupération simple pour ses bases de données. Avec le mode de récupération simple, les bases de données sont récupérées à la date de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer une base de données à la date de la défaillance ou à moment spécifique. Pour de nombreuses organisations, le modèle de récupération simple est optimal, car la base de données principale Lync Server (RTCXDS.mdf) est en fait plus petite que les fichiers journaux des transactions et beaucoup plus petite que ceux des applications de bases de données métier ordinaires.

  - Toute la configuration DNS (Domain Name System), la configuration DHCP (Dynamic Host Configuration Protocol), les noms de domaine, les noms de domaine complets des ordinateurs, les chemins d’accès aux magasins de fichiers, etc. doivent être les mêmes au moment de la restauration que ceux qu’ils étaient au moment de la sauvegarde.

Si un serveur exécutant Lync Server subit une défaillance, la récupération comprend les étapes suivantes :

  - Installez le système d’exploitation sur un ordinateur nouveau ou nettoyé portant le même nom de domaine complet (FQDN) que l’ordinateur défaillant.

  - Réinstallez les certificats.

  - Si le serveur hébergeait une base de données, installez Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2.

  - En général, si le serveur hébergeait une base de données, exécutez le Générateur de topologie pour créer et installer la base de données, puis configurez les listes de contrôle d’accès.

  - En général, si le serveur hébergeait un rôle serveur, exécutez les étapes 1 à 4 de l’Assistant Déploiement de Lync Server pour installer les fichiers de configuration locaux, installez les composants du rôle serveur, assignez les certificats, puis démarrez les services.
    
    > [!NOTE]  
    > Si le serveur hébergeait une base de données colocalisée avec le rôle serveur, l’exécution de l’étape 2 de l’Assistant Déploiement de Lync Server permet de recréer la base de données.

  - Si le serveur hébergeait une base de données, restaurez les données sauvegardées.

