---
title: 'Lync Server 2013 : exigences techniques de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cc8a64ee7a49971660e7435a51c816bd4367e26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="80bce-102">Configuration technique requise pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bce-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80bce-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="80bce-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="80bce-104">Les exigences techniques de Lync Server 2013 sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="80bce-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="80bce-105">Exigences d’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="80bce-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="80bce-106">Logiciels requis qui doivent être installés pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="80bce-107">Exigences en matière de stockage des données pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="80bce-108">Exigences relatives à l’échelle et considérations relatives à votre déploiement d’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="80bce-109">Exigences et considérations en matière de performances pour vos bases de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80bce-110">Les informations de mise à l’échelle et de performance ne sont pas disponibles dans la version 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80bce-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="80bce-111">Exigences d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="80bce-111">Infrastructure Requirements</span></span>

<span data-ttu-id="80bce-112">Les exigences d’infrastructure d’archivage de Lync Server 2013 sont les mêmes que pour le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80bce-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="80bce-113">Pour plus d’informations, reportez-vous à la rubrique [détermination de votre configuration d’infrastructure requise pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="80bce-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="80bce-114">Archivage requis</span><span class="sxs-lookup"><span data-stu-id="80bce-114">Archiving Prerequisites</span></span>

<span data-ttu-id="80bce-115">Lync Server 2013 simplifie les conditions préalables à l’archivage pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="80bce-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="80bce-116">Le serveur d’archivage n’est plus un rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="80bce-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="80bce-117">Au lieu de cela, les agents de collection de données unifiés s’exécutent sur les serveurs frontaux d’un pool et de serveurs Standard Edition pour capturer les données pour l’archivage, de sorte que vous ne configurez pas des plateformes système distinctes pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="80bce-118">L’archivage utilise le stockage de fichiers de Lync Server 2013 pour stocker temporairement les fichiers de contenu de la réunion, de sorte que vous n’avez pas configuré de magasin de fichiers distinct pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="80bce-119">Dans Lync Server 2013, Message Queuing n’est pas requis.</span><span class="sxs-lookup"><span data-stu-id="80bce-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="80bce-120">Exigences en matière de stockage des données pour l’archivage</span><span class="sxs-lookup"><span data-stu-id="80bce-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="80bce-121">Par ailleurs, vous devez configurer l’infrastructure pour le stockage d’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="80bce-122">Cela comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="80bce-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="80bce-123">**Stockage Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="80bce-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="80bce-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span><span class="sxs-lookup"><span data-stu-id="80bce-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="80bce-125">Si vous souhaitez utiliser l’intégration de Microsoft Exchange de sorte que les données d’archive Lync soient stockées avec les données de conformité Exchange, vous devez utiliser Exchange 2013 pour votre déploiement Exchange et garantir que la taille de stockage maximale prend en charge le stockage des fichiers de contenu de la réunion.</span><span class="sxs-lookup"><span data-stu-id="80bce-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="80bce-126">Si vous déployez l’archivage à l’aide de l’option d’intégration de Microsoft Exchange, les données d’archive Lync sont stockées avec les données de conformité Exchange 2013 uniquement pour les utilisateurs qui sont hébergés sur vos serveurs Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="80bce-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="80bce-127">Vous devez déployer Exchange 2013 avant de déployer et d’activer l’archivage à l’aide de l’option d’intégration de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="80bce-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="80bce-128">Si vous choisissez d’utiliser le stockage Exchange 2013, vous n’avez pas besoin de déployer des bases de données SQL Server distinctes pour l’archivage, sauf si vous avez des utilisateurs de Lync qui ne sont pas hébergés sur vos serveurs Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="80bce-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="80bce-129">**Stockage de base de données SQL Server pour l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="80bce-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="80bce-130">Pour prendre en charge les utilisateurs qui ne sont pas hébergés sur des serveurs Exchange 2013 ou si vous ne voulez pas utiliser l’option d’intégration de Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="80bce-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="80bce-131">Lync Server 2013 prend en charge les versions 64 bits suivantes de SQL Server :</span><span class="sxs-lookup"><span data-stu-id="80bce-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="80bce-132">Microsoft SQL Server 2008 R2 entreprise</span><span class="sxs-lookup"><span data-stu-id="80bce-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="80bce-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="80bce-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="80bce-134">Microsoft SQL Server 2012 entreprise</span><span class="sxs-lookup"><span data-stu-id="80bce-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="80bce-135">Microsoft SQL Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="80bce-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80bce-136">Microsoft SQL Server 2008 R2 Express et Microsoft SQL Server 2012 Express ne sont pas pris en charge pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="80bce-137">les versions 32 bits de SQL Server ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="80bce-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="80bce-138">Pour plus d’informations et de restrictions concernant SQL Server, voir <A href="lync-server-2013-database-software-support.md">prise en charge de logiciels de base de données dans Lync Server 2013</A> dans la documentation de planification ou dans la documentation sur la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="80bce-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="80bce-139">Vous devez configurer les plates-formes SQL Server avant de déployer et d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="80bce-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="80bce-140">Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="80bce-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="80bce-141">Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation.</span><span class="sxs-lookup"><span data-stu-id="80bce-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="80bce-142">Pour plus d’informations sur SQL Server, voir le site TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="80bce-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

