---
title: 'Lync Server 2013 : Configuration de SQL Server pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Configuration de SQL Server pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-08-12_

Les rubriques de cette section expliquent comment déployer et configurer SQL Server pour une utilisation dans un déploiement d’entreprise de Lync Server. Les serveurs Standard Edition utilisent une version SQL Server Express colocalisée de SQL Server, adaptée aux charges de travail d’un serveur Standard Edition Server.

Le magasin de gestion centralisée de Lync Server 2013 contient les données utilisateur pour tous les serveurs Enterprise Edition au sein d’un pool et est conçu pour être localisé sur un serveur principal SQL Server. En tant que référentiel centralisé, le magasin de gestion central ne peut pas être installé sur le même ordinateur que n’importe quel autre rôle Lync Server 2013. Le magasin de gestion central ne peut pas résider sur un serveur Enterprise Edition dans le pool. Le magasin de gestion central est créé automatiquement lorsque vous publiez la topologie pour la première fois et sélectionnez pour créer les bases de données. L’ordinateur désigné comme serveur principal doit déjà exécuter le logiciel de base de données SQL Server pour que l’installation réussisse.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Emplacement des fichiers journaux et des données SQL Server pour Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configuration de SQL Server dans Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Description des exigences de pare-feu pour SQL Server avec Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurer le regroupement SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

