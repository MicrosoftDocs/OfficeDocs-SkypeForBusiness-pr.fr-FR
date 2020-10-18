---
title: 'Lync Server 2013 : préparation de l’infrastructure et des systèmes'
description: 'Lync Server 2013 : préparation de l’infrastructure et des systèmes.'
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
ms.openlocfilehash: bfabdda9d117af1534578c8543f9ce72808d5a53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579990"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Préparation de l’infrastructure et des systèmes pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Le déploiement de Lync Server 2013 nécessite l’utilisation du générateur de topologies pour définir et publier la conception de la topologie. Pour identifier les composants requis pour votre topologie, vous utilisez le générateur de topologies pour créer et enregistrer une conception de topologie. Avant de publier votre topologie dans le Générateur de topologie, procédez comme suit :

  - Procurez-vous et installez le matériel pour chaque composant de la conception de la topologie que vous avez créé et enregistré à l’aide du générateur de topologie, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, les serveurs de bases de données, les serveurs exécutant les services Internet (IIS) et les serveurs proxy inverses, selon le cas) Pour plus d’informations sur la définition d’une topologie qui spécifie les composants nécessaires à votre déploiement, reportez-vous à [la rubrique Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.

  - Assurez-vous que l’infrastructure réseau répond à la configuration requise. Pour plus d’informations, reportez-vous à [Network infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.

  - Configurez les services de domaine Active Directory. Pour publier et activer la topologie, les serveurs internes doivent être représentés par des comptes d’ordinateur dans AD DS. Il suffit pour cela de joindre les ordinateurs aux services de domaine Active Directory. Pour plus d’informations sur la préparation des services AD DS, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Créez un partage de fichiers. Les serveurs Standard Edition peuvent héberger le partage de fichiers pour le fichier requis, tandis que dans un déploiement d’entreprise, le partage de fichiers ne peut pas être hébergé sur le serveur frontal. Les autorisations et les appartenances à un groupe requises pour le déploiement et la définition de la liste de contrôle d’accès (ACL) sur le dossier et le partage doivent être configurées de manière adéquate pour que le Générateur de topologie s’exécute correctement. Assurez-vous que la personne qui exécute le générateur de topologie dispose des autorisations et appartenances de groupe suivantes :
    
      - Membre du groupe Administrateurs local
    
      - Membre des utilisateurs du domaine
    
      - Contrôle total du partage et du dossier du magasin de fichiers

  - Pour Enterprise Edition, installez et configurez SQL Server. Pour que la configuration de SQL Server réussisse, le serveur SQL Server doit être en ligne et la personne chargée de la publication de la topologie doit être un administrateur local sur le serveur SQL Server et membre du groupe SQL Server sysadmin sur l’instance SQL Server.

Lorsque vous avez terminé toutes les tâches de préparation décrites dans cette rubrique et avant de publier la topologie, vous devez également exécuter les autres tâches de préparation telles que l’installation des systèmes d’exploitation Windows et d’autres logiciels requis, la configuration IIS et la configuration du DNS. Pour plus d’informations sur ces tâches, reportez-vous à la rubrique [Configuration requise pour les serveurs exécutant Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configuration des services Internet (IIS) pour Lync Server 2013](lync-server-2013-configure-iis.md)et [préparation de l’infrastructure et des systèmes pour Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). De plus, vous devez prendre connaissance des clients et de leurs besoins. Pour plus d’informations, reportez-vous à la rubrique [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration matérielle de Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuration logicielle pour Lync Server 2013](lync-server-2013-software-setup.md)

  - [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configuration de SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurer des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installer les outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

