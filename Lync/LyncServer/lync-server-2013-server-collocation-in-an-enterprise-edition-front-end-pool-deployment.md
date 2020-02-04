---
title: Colocalisation de serveur Lync Server 2013 lors d’un déploiement de pool frontal Enterprise Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad549c614fc14b74126a7e81e0223ad584e68141
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="b7790-102">Colocalisation de serveur lors d’un déploiement de pool frontal Enterprise Edition pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7790-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7790-103">_**Dernière modification de la rubrique :** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="b7790-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="b7790-104">Cette section décrit les rôles de serveur, les bases de données et les partages de fichiers que vous pouvez collocate dans un déploiement de pool frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7790-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="b7790-105">Rôles de serveur</span><span class="sxs-lookup"><span data-stu-id="b7790-105">Server Roles</span></span>

<span data-ttu-id="b7790-106">Dans Lync Server 2013, le service de conférence A/V, le service de médiation, la surveillance et l’archivage sont localisés sur le serveur frontal, mais une configuration supplémentaire est nécessaire pour les activer.</span><span class="sxs-lookup"><span data-stu-id="b7790-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="b7790-107">Si vous ne voulez pas que collocate le serveur de médiation du serveur frontal, vous pouvez le déployer en tant que serveur de médiation autonome sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b7790-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="b7790-108">Vous pouvez collocate un serveur d’applications de confiance auprès du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b7790-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="b7790-109">Les rôles serveur suivants doivent être déployés sur un autre ordinateur :</span><span class="sxs-lookup"><span data-stu-id="b7790-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="b7790-110">directeur</span><span class="sxs-lookup"><span data-stu-id="b7790-110">Director</span></span>

  - <span data-ttu-id="b7790-111">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b7790-111">Edge Server</span></span>

  - <span data-ttu-id="b7790-112">Serveur de médiation (en cas de non-colocalisé avec le serveur frontal)</span><span class="sxs-lookup"><span data-stu-id="b7790-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="b7790-113">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="b7790-113">Office Web Apps Server</span></span>

<span data-ttu-id="b7790-114">Vous ne pouvez pas collocate le rôle serveur de chat permanent avec le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b7790-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="b7790-115">Bases de données</span><span class="sxs-lookup"><span data-stu-id="b7790-115">Databases</span></span>

<span data-ttu-id="b7790-116">Vous pouvez collocater les bases de données suivantes sur le même serveur de base de données :</span><span class="sxs-lookup"><span data-stu-id="b7790-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="b7790-117">Base de données principale</span><span class="sxs-lookup"><span data-stu-id="b7790-117">Back-end database</span></span>

  - <span data-ttu-id="b7790-118">base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="b7790-118">Monitoring database</span></span>

  - <span data-ttu-id="b7790-119">base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="b7790-119">Archiving database</span></span>

  - <span data-ttu-id="b7790-120">Base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="b7790-120">Persistent Chat database</span></span>

  - <span data-ttu-id="b7790-121">Base de données de compatibilité des conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="b7790-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="b7790-122">Vous pouvez collocate tout ou partie de ces bases de données dans une instance unique de SQL Server ou utiliser une instance distincte de SQL Server pour chacune d’elles, avec les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b7790-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="b7790-123">Chaque instance de SQL Server peut contenir uniquement une seule base de données principale, une base de données de surveillance unique, une base de données d’archivage unique, une seule base de données de chat permanent et une seule et même base de données de conformité des conversations permanentes.</span><span class="sxs-lookup"><span data-stu-id="b7790-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="b7790-124">Le serveur de base de données ne peut pas prendre en charge plus d’un pool frontal, un déploiement d’archivage et un déploiement de la surveillance, mais il peut prendre en charge l’un de ceux-ci, que les bases de données utilisent ou non la même instance de SQL Server, ou des instances distinctes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7790-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="b7790-125">Vous pouvez collocate un partage de fichiers avec les bases de données, comme décrit plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="b7790-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7790-126">Dans Lync Server 2013, vous avez la possibilité d’intégrer le stockage d’archivage avec le stockage Exchange 2013 pour tout ou partie de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="b7790-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="b7790-127">Vous ne pouvez pas déployer des serveurs exécutant Lync Server ou des composants sur les mêmes serveurs que le stockage Exchange.</span><span class="sxs-lookup"><span data-stu-id="b7790-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b7790-128">Même si la colocalisation des bases de données est prise en charge, la taille de celles-ci peut être rapidement augmentée.</span><span class="sxs-lookup"><span data-stu-id="b7790-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="b7790-129">Par exemple, lorsque vous considérez collocating la base de données d’archivage avec d’autres bases de données, sachez que, si vous archivez les messages de plus de quelques utilisateurs, l’espace disque requis par la base de données d’archivage peut devenir très volumineux.</span><span class="sxs-lookup"><span data-stu-id="b7790-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="b7790-130">C’est pourquoi nous vous déconseillons de collocating plusieurs bases de données, en particulier de la base de données d’archivage, de la base de données de chat permanent ou de la base de données de conformité des conversations permanentes avec la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="b7790-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="b7790-131">Partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="b7790-131">File Share</span></span>

<span data-ttu-id="b7790-132">Le partage de fichiers peut être un serveur distinct ou être colocalisé sur le même serveur que tout ou partie des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b7790-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="b7790-133">Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b7790-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="b7790-134">base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="b7790-134">Archiving database</span></span>

  - <span data-ttu-id="b7790-135">base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="b7790-135">Monitoring database</span></span>

  - <span data-ttu-id="b7790-136">Base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="b7790-136">Persistent Chat database</span></span>

  - <span data-ttu-id="b7790-137">Base de données de compatibilité des conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="b7790-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="b7790-138">Un partage de fichiers unique peut être utilisé pour plusieurs listes frontales, serveurs Standard Edition (tous sur le même site).</span><span class="sxs-lookup"><span data-stu-id="b7790-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7790-139">Dans Lync Server 2013, la surveillance et l’archivage utilisent le partage de fichiers Lync Server comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b7790-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="b7790-140">Autres composants</span><span class="sxs-lookup"><span data-stu-id="b7790-140">Other Components</span></span>

<span data-ttu-id="b7790-141">Vous ne pouvez pas collocate un serveur proxy inverse, qui n’est pas un composant Lync Server 2013, mais qui est requis dans votre déploiement si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés possédant un rôle Server 2013 serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="b7790-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="b7790-142">Toutefois, vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement de Lync Server 2013 en configurant le support sur un serveur de proxy inverse existant dans votre organisation qui est utilisé pour d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="b7790-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="b7790-143">Vous ne pouvez pas collocate un composant de messagerie unifiée Exchange ou un composant SharePoint avec un rôle serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b7790-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

