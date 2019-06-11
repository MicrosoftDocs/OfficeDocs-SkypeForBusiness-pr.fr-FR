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

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="50e9e-102">Configuration de SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e9e-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50e9e-103">_**Dernière modification de la rubrique:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="50e9e-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="50e9e-104">Les rubriques de cette section expliquent comment déployer et configurer SQL Server pour une utilisation dans un déploiement d’entreprise de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50e9e-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="50e9e-105">Les serveurs Standard Edition utilisent une version SQL Server Express colocalisée de SQL Server, adaptée aux charges de travail d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="50e9e-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="50e9e-106">Le magasin de gestion centralisée de Lync Server 2013 contient les données utilisateur pour tous les serveurs Enterprise Edition au sein d’un pool et est conçu pour être localisé sur un serveur principal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="50e9e-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="50e9e-107">En tant que référentiel centralisé, le magasin de gestion central ne peut pas être installé sur le même ordinateur que n’importe quel autre rôle Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50e9e-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="50e9e-108">Le magasin de gestion central ne peut pas résider sur un serveur Enterprise Edition dans le pool.</span><span class="sxs-lookup"><span data-stu-id="50e9e-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="50e9e-109">Le magasin de gestion central est créé automatiquement lorsque vous publiez la topologie pour la première fois et sélectionnez pour créer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="50e9e-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="50e9e-110">L’ordinateur désigné comme serveur principal doit déjà exécuter le logiciel de base de données SQL Server pour que l’installation réussisse.</span><span class="sxs-lookup"><span data-stu-id="50e9e-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="50e9e-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="50e9e-111">In This Section</span></span>

  - [<span data-ttu-id="50e9e-112">Emplacement des fichiers journaux et des données SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e9e-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="50e9e-113">Configuration de SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e9e-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="50e9e-114">Autorisations de déploiement de SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e9e-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="50e9e-115">Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e9e-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="50e9e-116">Description des exigences de pare-feu pour SQL Server avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e9e-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="50e9e-117">Configurer le regroupement SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e9e-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

