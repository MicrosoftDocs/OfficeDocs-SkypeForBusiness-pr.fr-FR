---
title: 'Lync Server 2013 : Préparation de l’infrastructure et des systèmes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Préparation de l’infrastructure et des systèmes pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Le déploiement de Lync Server 2013 nécessite l’utilisation du générateur de topologie pour définir et publier la conception topologique. Pour identifier les composants requis pour votre topologie, utilisez le générateur de topologie pour créer et enregistrer une conception de topologie. Avant de publier votre topologie dans le générateur de topologie, procédez comme suit :

  - Obtenez et installez le matériel de chaque composant de la conception topologique que vous avez créé et enregistré à l’aide du générateur de topologie, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, serveurs de base de données, serveurs exécutant Internet Information Services ( IIS) et inversez les serveurs proxy, selon le cas), les cartes réseau, les équilibreurs de charge matérielle et les périphériques de stockage (par exemple, les serveurs de fichiers). Pour plus d’informations sur la définition d’une topologie spécifiant les composants nécessaires à votre déploiement, reportez-vous à la rubrique [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation relative à la prise en charge.

  - Assurez-vous que l’infrastructure réseau répond à la configuration requise. Pour plus d’informations, voir [Configuration requise pour l’infrastructure réseau pour Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.

  - Configurez les services de domaine Active Directory. Pour publier et activer la topologie, vous avez besoin que les serveurs internes soient représentés par des comptes d’ordinateur dans AD DS. Pour cela, il suffit de joindre les ordinateurs à AD DS. Pour plus d’informations sur la préparation d’AD DS, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Créer un partage de fichiers. Les serveurs Standard Edition peuvent héberger le partage de fichiers du fichier requis, lors d’un déploiement d’entreprise, le partage de fichier ne peut pas être hébergé sur le serveur frontal. Les autorisations et appartenances aux groupes requises pour le déploiement et la configuration de la liste de contrôle d’accès (ACL) sur le dossier et du partage doivent être correctement configurées pour que le générateur de topologie s’exécute correctement. Assurez-vous que la personne exécutant le générateur de topologie dispose des autorisations et des appartenances aux groupes suivantes :
    
      - Membre du groupe administrateurs locaux
    
      - Membre du domaine utilisateurs
    
      - Contrôle total sur le partage et le dossier du magasin de fichiers

  - Pour Enterprise Edition, installez et configurez SQL Server. Pour que le programme d’installation de SQL Server réussisse, le serveur SQL Server doit être connecté et la personne qui publie la topologie doit être un administrateur local sur le serveur SQL Server et doit être membre du groupe SQL Server sysadmin sur l’instance SQL Server.

Une fois toutes les tâches de préparation effectuées comme décrit dans cette rubrique, mais avant la publication de la topologie, vous devez effectuer les autres tâches de préparation, y compris l’installation des systèmes d’exploitation Windows et d’autres logiciels requis, configuration Services Internet et configuration DNS. Pour plus d’informations sur ces tâches, voir [Configuration système requise pour les serveurs exécutant Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurer IIS pour Lync Server 2013](lync-server-2013-configure-iis.md)et [préparer l’infrastructure et les systèmes pour Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Par ailleurs, vous devez vous familiariser avec les clients et les exigences clientes. Pour plus d’informations, reportez-vous à la section [déploiement de clients et d’appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration matérielle pour Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuration logicielle pour Lync Server 2013](lync-server-2013-software-setup.md)

  - [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configuration de SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configuration des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

