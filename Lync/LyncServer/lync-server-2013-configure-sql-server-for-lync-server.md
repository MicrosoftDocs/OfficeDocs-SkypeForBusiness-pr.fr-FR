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
ms.openlocfilehash: 77f6357d38731438555b2c9e3af7ec6a22e9df7c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="c48d9-102">Configuration de SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48d9-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c48d9-103">_**Dernière modification de la rubrique :** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="c48d9-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="c48d9-104">Les rubriques de cette section traitent du déploiement et de la configuration de SQL Server à utiliser dans un déploiement d’entreprise de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c48d9-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="c48d9-105">Les serveurs Standard Edition utilisent une version SQL Server Express colocalisée de SQL Server qui est adaptée aux charges de travail d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="c48d9-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="c48d9-106">Le magasin central de gestion Lync Server 2013 contient les données utilisateur pour tous les serveurs Enterprise Edition d’un pool, et est conçu pour être situé sur un serveur principal basé sur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c48d9-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="c48d9-107">En tant que référentiel centralisé, le magasin central de gestion ne peut pas être installé sur le même ordinateur que tout autre rôle Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c48d9-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="c48d9-108">Le magasin central de gestion ne peut pas résider sur un serveur Enterprise Edition dans le pool.</span><span class="sxs-lookup"><span data-stu-id="c48d9-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="c48d9-109">Le magasin central de gestion est créé automatiquement lorsque vous publiez la topologie pour la première fois et que vous choisissez de créer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="c48d9-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="c48d9-110">L’ordinateur que vous désignez en tant que serveur principal doit déjà exécuter le logiciel de base de données SQL Server pour que l’installation réussisse.</span><span class="sxs-lookup"><span data-stu-id="c48d9-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c48d9-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c48d9-111">In This Section</span></span>

  - [<span data-ttu-id="c48d9-112">Emplacement des fichiers journaux et de données SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48d9-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="c48d9-113">Configurer SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48d9-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="c48d9-114">Autorisations de déploiement pour SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48d9-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="c48d9-115">Installation de la base de données à l’aide de Lync Server Management Shell dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48d9-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="c48d9-116">Présentation des exigences en matière de pare-feu pour SQL Server avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48d9-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="c48d9-117">Configurer le clustering SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48d9-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

