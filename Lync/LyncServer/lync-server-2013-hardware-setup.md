---
title: 'Lync Server 2013 : configuration matérielle'
description: 'Lync Server 2013 : configuration matérielle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e798ce32c1f89bba40ad9245426492b0489e7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552910"
---
# <a name="hardware-setup-for-lync-server-2013"></a>Configuration matérielle de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Pour configurer le matériel et les autres composants requis dans l’infrastructure nécessaire à l’implémentation de votre topologie, vous devez, avant de publier votre topologie dans le générateur de topologie, procédez comme suit :

  - Installez le matériel de chaque composant de la conception de la topologie que vous avez créé et enregistré à l’aide du générateur de topologies, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, serveurs de bases de données, serveurs exécutant les services Internet (IIS) et serveurs proxy inverses, selon le cas), cartes réseau, programmes d’équilibrage de la charge matérielle Confirmez que vous avez suivi les recommandations pour le nombre et la vitesse des cartes réseau. Si vous utilisez des programmes d’équilibrage de la charge matérielle, vérifiez que vous disposez des informations appropriées du fournisseur pour les configurer en vue d’une utilisation avec Lync Server 2013. Si vous utilisez un serveur de fichiers ou un autre serveur pour héberger le partage de fichiers requis par Lync Server, assurez-vous que le serveur est disponible et prêt pour la configuration du partage de fichiers. Pour plus d’informations sur la définition d’une topologie qui spécifie les composants nécessaires à votre déploiement, reportez-vous à [la rubrique Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.

  - Assurez-vous que l’infrastructure réseau répond à la configuration requise. Pour plus d’informations, reportez-vous à [Network infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.

  - Configurez les services de domaine Active Directory. La configuration des services de domaine Active Directory (AD DS) inclut leur préparation, ainsi que la définition de tous les composants que vous souhaitez déployer dans AD DS. Pour plus d’informations sur la préparation des services AD DS, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.

  - Configurez les autorisations nécessaires à la création du partage de fichiers. Les autorisations d’utilisation des partages de fichiers par Lync Server 2013 sont automatiquement configurées par le générateur de topologies lorsque vous publiez votre topologie. Toutefois, le compte d’utilisateur utilisé pour publier la topologie doit disposer d’un contrôle total (lecture/écriture/modification) sur le partage de fichiers afin que le générateur de topologies configure les autorisations requises. Pour vous assurer que le partage de fichiers peut être correctement géré pendant le processus de publication du générateur de topologie, l’utilisateur ou le groupe de domaines dont l’utilisateur est membre doit être membre du groupe Administrateurs local sur l’ordinateur où se trouve le partage de fichiers. Dans un scénario multidomaine, l’utilisateur ou le groupe du domaine A devrait devenir membre du groupe d’administrateurs local sur l’ordinateur du domaine B où se trouve le partage de fichiers.
    
    Pour plus d’informations sur la mise à jour à l’aide de partages de fichiers dans un système de fichiers DFS, voir [configurer le stockage de fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > Le partage de fichiers pour Lync Server 2013, Enterprise Edition ne peut pas se trouver sur le serveur frontal.

    
    </div>

  - Installez et configurez l’équilibreur de la charge matérielle pour les services Web. Si l’équilibrage de la charge DNS (Domain Name System) est déployé, vous devez tout de même utiliser des programmes d’équilibrage de la charge matérielle pour ces pools, mais uniquement pour le trafic HTTP/HTTPS. Les programmes d’équilibrage de la charge matérielle sont utilisés pour le trafic HTTPS provenant des clients et transitant via les ports 443 et 80. Bien que le recours à ces programmes soit toujours nécessaire pour vos pools de serveurs, leur configuration et leur administration concernera avant tout le trafic HTTP/HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés..

Lorsque vous avez terminé toutes les tâches de préparation décrites dans cette rubrique et avant de publier la topologie, vous devez également effectuer les actions suivantes :

  - [Installer les systèmes d’exploitation et les logiciels prérequis sur les serveurs pour Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurer les services Internet (IIS) pour Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configuration de SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurer des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

