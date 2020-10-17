---
title: Colocalisation de serveur Lync Server 2013 dans un déploiement de serveur Standard Edition
description: Colocalisation de serveur Lync Server 2013 dans un déploiement de serveur Standard Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af44761d36c472de1a3da5cd3b3938dc1a130836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555110"
---
# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="e4576-103">Colocalisation des serveurs dans un déploiement de serveur Standard Edition pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4576-103">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4576-104">_**Dernière modification de la rubrique :** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="e4576-104">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="e4576-105">Cette section décrit les rôles serveur, les bases de données et les partages de fichiers que vous pouvez colocaliser dans un déploiement de serveur Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4576-105">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="e4576-106">Rôles serveur</span><span class="sxs-lookup"><span data-stu-id="e4576-106">Server Roles</span></span>

<span data-ttu-id="e4576-107">Dans Lync Server 2013, le service de conférence A/V, le service de médiation, la surveillance et l’archivage sont colocalisés sur le serveur Standard Edition, mais une configuration supplémentaire est nécessaire pour les activer.</span><span class="sxs-lookup"><span data-stu-id="e4576-107">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="e4576-108">Vous pouvez également choisir de déployer le service de médiation sur des serveurs distincts.</span><span class="sxs-lookup"><span data-stu-id="e4576-108">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="e4576-109">Vous pouvez colocaliser un serveur d’applications approuvées avec un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4576-109">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="e4576-110">Les rôles serveur suivants doivent être individuellement déployés sur un ordinateur distinct :</span><span class="sxs-lookup"><span data-stu-id="e4576-110">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="e4576-111">Directeur</span><span class="sxs-lookup"><span data-stu-id="e4576-111">Director</span></span>

  - <span data-ttu-id="e4576-112">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e4576-112">Edge Server</span></span>

  - <span data-ttu-id="e4576-113">Serveur de médiation (s’il n’est pas colocalisé avec le serveur Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="e4576-113">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="e4576-114">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="e4576-114">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="e4576-115">Databases</span><span class="sxs-lookup"><span data-stu-id="e4576-115">Databases</span></span>

<span data-ttu-id="e4576-116">Par défaut, la base de données principale SQL Server Express est colocalisée sur le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4576-116">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="e4576-117">Vous ne pouvez pas la déplacer sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4576-117">You cannot move it to a separate computer.</span></span> <span data-ttu-id="e4576-118">À une exception près, vous ne pouvez pas colocaliser d’autres bases de données sur le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4576-118">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="e4576-119">Si vous choisissez de déployer le serveur de conversation permanente sur un serveur Standard Edition, vous pouvez colocaliser la base de données de conversation permanente et la base de données de conformité de la conversation permanente sur le même serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4576-119">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="e4576-120">Vous pouvez colocaliser chacune des bases de données suivantes sur un serveur de base de données unique :</span><span class="sxs-lookup"><span data-stu-id="e4576-120">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="e4576-121">Base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="e4576-121">Monitoring database</span></span>

  - <span data-ttu-id="e4576-122">Base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="e4576-122">Archiving database</span></span>

  - <span data-ttu-id="e4576-123">Une base de données principale pour un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e4576-123">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="e4576-124">Vous pouvez colocaliser une base de données ou l’ensemble de ces bases de données dans une instance SQL unique ou utiliser une instance SQL distincte pour chaque base de données, en tenant compte des limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4576-124">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="e4576-125">Chaque instance SQL peut ne contenir qu’une seule base de données principale (pour un pool frontal Enterprise Edition), une seule base de données de surveillance, une seule base de données d’archivage, une seule base de données de conversation permanente et une seule base de données de conformité de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e4576-125">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="e4576-126">Le serveur de base de données ne peut pas prendre en charge plusieurs pools frontaux Enterprise Edition, un serveur exécutant l’archivage, un serveur exécutant la surveillance, une seule base de données de conversation permanente et une seule base de données de conformité de conversation permanente, mais il peut en prendre en charge, que les bases de données utilisent ou non la même instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4576-126">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="e4576-127">Vous pouvez également colocaliser un partage de fichiers avec les bases de données comme il est indiqué plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="e4576-127">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4576-128">Dans Lync Server 2013, vous avez la possibilité d’intégrer le stockage de surveillance et d’archivage au stockage Exchange 2013 pour tout ou partie des utilisateurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="e4576-128">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="e4576-129">Vous ne pouvez pas déployer de serveurs exécutant Lync Server ou des composants sur les mêmes serveurs que le stockage Exchange.</span><span class="sxs-lookup"><span data-stu-id="e4576-129">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4576-130">Bien que la colocation des bases de données soit prise en charge, la taille des bases de données peut augmenter rapidement.</span><span class="sxs-lookup"><span data-stu-id="e4576-130">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="e4576-131">Par exemple, lorsque vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données du serveur d’archivage peuvent devenir très importants.</span><span class="sxs-lookup"><span data-stu-id="e4576-131">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="e4576-132">Pour cette raison, nous vous déconseillons de colocaliser plusieurs bases de données, notamment la base de données d’archivage, la base de données de conversation permanente et la base de données de conformité de la conversation permanente avec la base de données principale d’un pool d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e4576-132">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="e4576-133">Partages de fichiers</span><span class="sxs-lookup"><span data-stu-id="e4576-133">File Shares</span></span>

<span data-ttu-id="e4576-134">Le partage de fichier peut être un serveur distinct ou être colocalisé sur le même serveur que l’un ou l’ensemble des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e4576-134">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="e4576-135">Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e4576-135">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="e4576-136">Base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="e4576-136">Archiving database</span></span>

  - <span data-ttu-id="e4576-137">Base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="e4576-137">Monitoring database</span></span>

  - <span data-ttu-id="e4576-138">Base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="e4576-138">Persistent Chat database</span></span>

  - <span data-ttu-id="e4576-139">Base de données de conformité de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="e4576-139">Persistent Chat compliance database</span></span>

<span data-ttu-id="e4576-140">Un partage de fichiers unique peut être utilisé pour plusieurs pools frontaux et serveurs Standard Edition (sur le même site).</span><span class="sxs-lookup"><span data-stu-id="e4576-140">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4576-141">Dans Lync Server 2013, la surveillance et l’archivage utilisent le partage de fichiers Lync Server comme serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4576-141">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="e4576-142">Autres composants</span><span class="sxs-lookup"><span data-stu-id="e4576-142">Other Components</span></span>

<span data-ttu-id="e4576-143">Vous ne pouvez pas colocaliser un serveur proxy inverse, qui n’est pas un composant Lync Server 2013, mais qui est requis dans votre déploiement si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés avec un rôle serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4576-143">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="e4576-144">Toutefois, vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant de votre organisation qui est utilisé pour d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="e4576-144">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="e4576-145">Vous ne pouvez pas colocaliser un composant de messagerie unifiée Exchange ou un composant SharePoint avec un rôle Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4576-145">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

