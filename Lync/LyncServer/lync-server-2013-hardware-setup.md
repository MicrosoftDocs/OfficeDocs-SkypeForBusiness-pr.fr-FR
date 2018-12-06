---
title: 'Lync Server 2013 : Configuration matérielle'
TOCTitle: Configuration matérielle
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425852(v=OCS.15)
ms:contentKeyID: 49296876
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration matérielle pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

La configuration du matériel et d’autres composants requis dans l’infrastructure à implémenter dans votre topologie nécessitent, qu’avant de publier la topologie dans le Générateur de topologie, vous procédiez comme suit :

  - Installez le matériel pour chaque composant dans la conception de la topologie que vous créez et enregistrez via Générateur de topologie, dont tous les ordinateurs (serveurs de base de données, serveurs exécutant Lync Server 2013 et les services Internet (IIS) et les serveurs proxy inverses, le cas échéant), cartes réseau, équilibreurs de charge matérielle et dispositifs de stockage (tels que les serveurs de fichiers). Confirmez que vous avez suivi les recommandations relatives au nombre et à la vitesse des cartes réseau. Si vous comptez utiliser des équilibreurs de charge matérielle, veillez à disposer des informations appropriées du fabricant pour les configurer à des fins d’utilisation avec Lync Server 2013. Si vous comptez utiliser un serveur de fichiers ou autre pour héberger le partage de fichiers requis par Lync Server, assurez-vous que le serveur est disponible et prêt pour configurer ce partage de fichiers. Pour plus d’informations sur la définition d’une topologie indiquant les composants nécessaires à votre déploiement, reportez-vous à [Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Pour plus d’informations sur les exigences matérielles des serveurs, reportez-vous à [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.

  - Vérifiez que l’infrastructure réseau respecte les exigences. Pour plus d’informations, reportez-vous à [Exigences relatives à l'infrastructure réseau pour Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.

  - Configurez les services de domaine Active Directory. La configuration des services de domaine Active Directory (AD DS) inclut leur préparation, ainsi que la définition de tous les composants que vous souhaitez déployer dans AD DS. Pour plus d’informations sur la préparation AD DS, reportez-vous à [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.

  - Configurez les autorisations nécessaires à la création du partage de fichiers. Les autorisations d’accès aux partages de fichiers requises par Lync Server 2013 sont automatiquement configurées par le Générateur de topologie lorsque vous publiez la topologie. Cependant, le compte d’utilisateur servant à publier la topologie doit disposer des autorisations de contrôle complètes (lecture/écriture/modification) sur le partage de fichiers pour que le Générateur de topologie puisse configurer les autorisations requises. Afin que le partage de fichiers soit correctement géré par le générateur de topologie lors du processus de publication, le groupe d’utilisateurs ou de domaines auquel appartient l’utilisateur doit comprendre un membre du groupe d’administrateurs local sur l’ordinateur où se trouve le partage de fichiers. Dans un scénario multidomaine, l’utilisateur ou le groupe du domaine A devrait devenir membre du groupe d’administrateurs local sur l’ordinateur du domaine B où se trouve le partage de fichiers.
    
    Pour plus d’informations sur la mise à jour à l’aide des partages de fichiers dans un système de fichiers DFS, reportez-vous à [Configuration du stockage des fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    > [!WARNING]  
    > Le partage de fichiers de Lync Server 2013, Enterprise Edition ne peut pas se trouver sur le serveur frontal.

  - Installez et configurez le programme d’équilibrage de la charge matérielle pour les services web. Si l’équilibrage de la charge DNS (Domain Name System) est déployé, vous devez tout de même utiliser des programmes d’équilibrage de la charge matérielle pour ces pools, mais uniquement pour le trafic HTTP/HTTPS. Les programmes d’équilibrage de la charge matérielle sont utilisés pour le trafic HTTPS provenant des clients et transitant via les ports 443 et 80. Même si le recours à ces programmes est toujours nécessaire pour vos pools de serveurs, leur configuration et leur administration concernera avant tout le trafic HTTP/HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés..

Lorsque vous avez terminé toutes les tâches de préparation décrites dans cette rubrique et avant de publier la topologie, vous devez également effectuer les actions suivantes :

  - [Installation des systèmes d’exploitaition et des logiciels prérequis sur les serveurs pour Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configuration des services Internet (IIS) pour Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configuration de SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configuration des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

