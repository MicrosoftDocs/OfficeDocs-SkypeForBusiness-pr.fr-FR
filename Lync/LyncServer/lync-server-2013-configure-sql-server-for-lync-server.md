---
title: 'Lync Server 2013 : configuration de SQL Server pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e52534744849e41fa08895bd114833892f4b8a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Configuration de SQL Server pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-08-12_

Les rubriques de cette section traitent du déploiement et de la configuration de SQL Server à utiliser dans un déploiement d’entreprise de Lync Server. Les serveurs Standard Edition utilisent une version SQL Server Express colocalisée de SQL Server qui est adaptée aux charges de travail d’un serveur Standard Edition Server.

Le magasin central de gestion Lync Server 2013 contient les données utilisateur pour tous les serveurs Enterprise Edition d’un pool, et est conçu pour être situé sur un serveur principal basé sur SQL Server. En tant que référentiel centralisé, le magasin central de gestion ne peut pas être installé sur le même ordinateur que tout autre rôle Lync Server 2013. Le magasin central de gestion ne peut pas résider sur un serveur Enterprise Edition dans le pool. Le magasin central de gestion est créé automatiquement lorsque vous publiez la topologie pour la première fois et que vous choisissez de créer les bases de données. L’ordinateur que vous désignez en tant que serveur principal doit déjà exécuter le logiciel de base de données SQL Server pour que l’installation réussisse.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Emplacement des fichiers journaux et de données SQL Server pour Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configurer SQL Server dans Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Autorisations de déploiement pour SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Installation de la base de données à l’aide de Lync Server Management Shell dans Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Présentation des exigences en matière de pare-feu pour SQL Server avec Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

