---
title: 'Lync Server 2013 : Configuration matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2d05db28ffa61ea25dbb237c388c37a87ac5a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Configuration matérielle pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Pour configurer le matériel et d’autres composants requis dans l’infrastructure dont vous avez besoin pour implémenter votre topologie, avant de publier votre topologie dans le générateur de topologie, procédez comme suit:

  - Installez le matériel de chaque composant de la conception topologique que vous avez créé et enregistré à l’aide du générateur de topologie, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, serveurs de base de données, serveurs exécutant Internet Information Services (IIS) et inversez les serveurs proxy, selon le cas), cartes réseau, équilibreurs de charge matérielle et périphériques de stockage (par exemple, serveurs de fichiers). Vérifiez que vous avez suivi les recommandations en matière de nombre et de vitesse pour les cartes réseau. Si vous utilisez des équilibreurs de charge matérielle, assurez-vous que vous disposez des informations appropriées du fournisseur pour les configurer pour une utilisation avec Lync Server 2013. Si vous utilisez un serveur de fichiers ou un autre serveur pour mettre en place le partage de fichiers requis par Lync Server, assurez-vous que le serveur est disponible et qu’il est prêt pour la configuration du partage de fichiers. Pour plus d’informations sur la définition d’une topologie spécifiant les composants nécessaires à votre déploiement, reportez-vous à la rubrique [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation relative à la prise en charge.

  - Assurez-vous que l’infrastructure réseau répond à la configuration requise. Pour plus d’informations, voir [Configuration requise pour l’infrastructure réseau pour Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.

  - Configurez les services de domaine Active Directory. La configuration de AD DS inclut la préparation de AD DS et la définition de tous les composants que vous voulez déployer dans AD DS. Pour plus d’informations sur la préparation d’AD DS, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.

  - Définissez les autorisations requises pour la création du partage de fichiers. Les autorisations d’utilisation des partages de fichiers par Lync Server 2013 sont automatiquement configurées par le générateur de topologie lors de la publication de votre topologie. Toutefois, le compte d’utilisateur utilisé pour publier la topologie doit avoir le contrôle total (lecture/écriture/modification) sur le partage de fichiers pour permettre au générateur de topologie de configurer les autorisations requises. Pour vous assurer que le partage de fichiers peut être géré correctement lors du processus de publication du générateur de topologie, le groupe d’utilisateurs ou de domaines dont l’utilisateur est membre doit être membre du groupe Administrateurs local sur l’ordinateur où se trouve le partage de fichiers. Dans un scénario multi-domaine, le domaine d’un utilisateur ou d’un groupe doit être membre du groupe Administrateurs local sur l’ordinateur du domaine B où se trouve le partage de fichiers.
    
    Pour plus d’informations sur la mise à jour de l’utilisation des partages de fichiers dans un système de fichiers DFS, voir [configurer le stockage de fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > Le partage de fichiers pour Lync Server 2013 entreprise Edition ne peut pas être localisé sur le serveur frontal.

    
    </div>

  - Installer et configurer l’équilibrage de charge matérielle pour les services Web. Après le déploiement de l’équilibrage de charge DNS (Domain Name System), vous devez également utiliser des équilibreurs de charge matérielle pour ces pools, mais uniquement pour le trafic HTTP/HTTPs. L’équilibrage de charge matérielle est utilisé pour le trafic HTTPs des clients sur les ports 443 et 80. Même si vous avez encore besoin d’équilibreurs de charge matérielle pour ces pools, leur configuration et leur administration seront essentiellement destinées au trafic HTTP/HTTPs, que les administrateurs des équilibreurs de charge matérielle sont habitués.

Une fois toutes les tâches de préparation effectuées comme décrit dans cette rubrique, vous devez également procéder comme suit:

  - [Installation des systèmes d’exploitaition et des logiciels prérequis sur les serveurs pour Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configuration des services Internet (IIS) pour Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configuration de SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configuration des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

