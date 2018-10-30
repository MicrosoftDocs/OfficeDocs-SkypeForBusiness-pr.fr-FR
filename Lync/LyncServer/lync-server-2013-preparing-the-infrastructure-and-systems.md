---
title: 'Lync Server 2013 : Préparation de l’infrastructure et des systèmes'
TOCTitle: Préparation de l’infrastructure et des systèmes
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398205(v=OCS.15)
ms:contentKeyID: 49296317
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation de l’infrastructure et des systèmes pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Le déploiement de Lync Server 2013 nécessite d’utiliser le Générateur de topologie pour définir et publier la conception de la topologie. Pour identifier les composants requis pour la topologie, vous devez également utiliser le Générateur de topologie qui vous permet de créer et d’enregistrer la conception de la topologie. Avant de publier votre topologie dans le générateur de topologie, procédez comme suit :

  - Achetez et installez le matériel pour chaque composant de la conception de la topologie que vous avez créée et enregistrée à l’aide du générateur de topologie, dont tous les ordinateurs (serveurs exécutant Lync Server 2013, serveurs de base de données, serveurs exécutant les services Internet (IIS) et serveurs proxy inverses, le cas échéant), cartes réseau, programmes d’équilibrage de la charge matérielle et dispositifs de stockage (comme les serveurs de fichiers) requis. Pour plus d’informations sur la définition d’une topologie qui indique les composants requis dans le cadre de votre déploiement, reportez-vous à [Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) Pour plus d’informations sur la configuration matérielle de serveur requise, reportez-vous à [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.

  - Vérifiez que l’infrastructure réseau répond à la configuration suivante. Pour plus d’informations, reportez-vous à [Exigences relatives à l'infrastructure réseau pour Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.

  - Configurez services de domaine Active Directory. Pour publier et activer la topologie, les serveurs internes doivent être représentés par des comptes d’ordinateur dans AD DS. Il suffit pour cela de joindre les ordinateurs aux services de domaine Active Directory. Pour plus d’informations sur la préparation AD DS, reportez-vous à [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Créez un partage de fichiers. Les serveurs Standard Edition peuvent héberger le partage de fichiers pour le fichier requis, tandis que dans un déploiement d’entreprise, le partage de fichiers ne peut pas être hébergé sur le serveur frontal. Les autorisations et les appartenances à un groupe requises pour le déploiement et la définition de la liste de contrôle d’accès (ACL) sur le dossier et le partage doivent être configurées de manière adéquate afin que le générateur de topologie s’exécute correctement. Vous devez vérifier que la personne l’exécutant dispose des autorisations et des appartenances à un groupe suivantes :
    
      - Membre du groupe Administrateurs local
    
      - Membre des utilisateurs du domaine
    
      - Contrôle total du partage et du dossier du magasin de fichiers

  - Pour Enterprise Edition, installez et configurez SQL Server. Pour que la configuration de SQL Server réussisse, le serveur SQL Server doit être en ligne et la personne chargée de la publication de la topologie doit être un administrateur local sur le serveur SQL Server et membre du groupe SQL Server sysadmin sur l’instance SQL Server.

Lorsque vous avez terminé toutes les tâches de préparation décrites dans cette rubrique et avant de publier la topologie, vous devez également exécuter les autres tâches de préparation telles que l’installation des systèmes d’exploitation Windows et d’autres logiciels requis, la configuration des services Internet (IIS) et la configuration du DNS. Pour plus d’informations sur ces tâches, reportez-vous à [Configuration système requise pour les serveurs exécutant Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configuration des services Internet (IIS) pour Lync Server 2013](lync-server-2013-configure-iis.md) et [Préparation de l’infrastructure et des systèmes pour Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). De plus, vous devez prendre connaissance des clients et de leurs besoins. Pour plus d’informations, reportez-vous à [Déploiement des clients et appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

## Dans cette section

  - [Configuration matérielle pour Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuration logicielle pour Lync Server 2013](lync-server-2013-software-setup.md)

  - [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configuration de SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configuration des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

