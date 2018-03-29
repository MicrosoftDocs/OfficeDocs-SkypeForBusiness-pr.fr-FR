---
title: Configuration logicielle et matérielle requise pour l’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle pour l’archivage dans Skype pour Business Server 2015.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="e315b-103">Configuration logicielle et matérielle requise pour l’archivage dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e315b-103">Hardware and software requirements for archiving in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e315b-104">**Résumé :** Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle pour l’archivage dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e315b-104">**Summary:** Read this topic to learn about hardware and software requirements for archiving in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e315b-105">Skype pour Business Server 2015 l’archivage fait désormais partie du rôle de Front-End, vous n’avez pas besoin d’installer un serveur distinct.</span><span class="sxs-lookup"><span data-stu-id="e315b-105">Skype for Business Server 2015 archiving is now part of the Front End role, so you do not need to install a separate server.</span></span> <span data-ttu-id="e315b-106">Vous devez, cependant, avoir à prendre en compte les exigences suivantes :</span><span class="sxs-lookup"><span data-stu-id="e315b-106">You do, however, need to consider the following requirements:</span></span>
  
- <span data-ttu-id="e315b-107">Conditions d’infrastructure requises</span><span class="sxs-lookup"><span data-stu-id="e315b-107">Infrastructure requirements</span></span>
    
- <span data-ttu-id="e315b-108">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="e315b-108">Prerequisite software requirements</span></span>
    
- <span data-ttu-id="e315b-109">Exigences pour le stockage des données</span><span class="sxs-lookup"><span data-stu-id="e315b-109">Data storage requirements</span></span>
    
## <a name="infrastructure-requirements"></a><span data-ttu-id="e315b-110">Conditions d’infrastructure requises</span><span class="sxs-lookup"><span data-stu-id="e315b-110">Infrastructure requirements</span></span>

<span data-ttu-id="e315b-111">Skype pour les exigences de l’infrastructure d’archivage de Server Business sont les mêmes que pour déploiement de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="e315b-111">Skype for Business Server Archiving infrastructure requirements are the same as for deployment of Skype for Business Server.</span></span> <span data-ttu-id="e315b-112">Pour plus d’informations, voir [Configuration requise pour votre Skype pour environnement d’entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e315b-112">For details, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
## <a name="prerequisite-software-requirements"></a><span data-ttu-id="e315b-113">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="e315b-113">Prerequisite software requirements</span></span>

<span data-ttu-id="e315b-114">L’archivage des conditions préalables pour Skype pour Business Server sont plus simples que les versions précédentes de Lync Server raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="e315b-114">Archiving prerequisites for Skype for Business Server are simpler than earlier versions of Lync Server because of the following:</span></span> 
  
- <span data-ttu-id="e315b-115">Étant donné que l’archivage n’est plus un rôle de serveur, il est inutile d’installer un serveur distinct pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="e315b-115">Because archiving is no longer a server role, you do not need to install a separate server for archiving.</span></span> <span data-ttu-id="e315b-116">Au lieu de cela, les agents de collecte de données unifiée sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et chaque serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e315b-116">Instead, Unified Data Collection Agents are installed and activated automatically on every Enterprise Edition Front End pool and every Standard Edition Server.</span></span> <span data-ttu-id="e315b-117">Vous devrez activer et publier votre topologie d’archivage en utilisant le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e315b-117">You will need to enable and publish your archiving topology by using Topology Builder.</span></span>
    
- <span data-ttu-id="e315b-118">L’archivage d’utilise le Skype pour le stockage de fichiers de serveur d’entreprise pour le stockage temporaire des fichiers de contenu, à la réunion afin que vous ne définissez pas un magasin de fichier distinct pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="e315b-118">Archiving uses the Skype for Business Server file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>
    
- <span data-ttu-id="e315b-119">Dans Skype pour Business Server, Microsoft Message Queuing n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e315b-119">In Skype for Business Server, Microsoft Message Queuing is not required.</span></span>
    
## <a name="data-storage-requirements"></a><span data-ttu-id="e315b-120">Exigences pour le stockage des données</span><span class="sxs-lookup"><span data-stu-id="e315b-120">Data Storage requirements</span></span>

<span data-ttu-id="e315b-p104">Vous devez configurer l’infrastructure d’archivage des données. Cela inclut le choix de l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e315b-p104">You will need to set up the infrastructure for archiving storage. This includes choosing one or both of the following options:</span></span>
  
- <span data-ttu-id="e315b-123">**Stockage de Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e315b-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="e315b-124">Les fichiers de contenu de réunion, par exemple, les présentations PowerPoint, sont archivés sous forme de pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="e315b-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="e315b-125">Si vous souhaitez stocker Skype pour archiver les données métiers avec des données de conformité d’Exchange, vous devez utiliser Exchange pour votre déploiement d’Exchange et assurez-vous que la taille maximale de stockage prend en charge le stockage des fichiers de contenu de réunion.</span><span class="sxs-lookup"><span data-stu-id="e315b-125">If you want to store Skype for Business archive data with Exchange compliance data, you must use Exchange for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="e315b-126">Vous devez déployer Exchange avant de déployer et d’activation de l’archivage à l’aide de l’option d’intégration de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="e315b-126">You must deploy Exchange prior to deploying and enabling archiving using the Microsoft Exchange integration option.</span></span> 
    
    <span data-ttu-id="e315b-127">Si vous choisissez d’utiliser le stockage Exchange, vous n’avez pas besoin déployer des bases de données SQL Server distinctes pour l’archivage, à moins d’avoir Skype pour les utilisateurs professionnels qui ne sont pas hébergées sur vos serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="e315b-127">If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers.</span></span> <span data-ttu-id="e315b-128">Si vous déployez l’archivage à l’aide de l’option d’intégration de Microsoft Exchange, Skype pour archiver les données métier est stockée avec les données de conformité d’Exchange uniquement pour les utilisateurs qui sont hébergés sur vos serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="e315b-128">If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers.</span></span> 
    
- <span data-ttu-id="e315b-129">**Skype pour le stockage d’archivage du serveur de l’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="e315b-129">**Skype for Business Server archiving storage**.</span></span> <span data-ttu-id="e315b-130">Pour prendre en charge les utilisateurs qui ne sont pas hébergées sur les serveurs Exchange, ou si vous ne souhaitez pas utiliser l’option d’intégration de Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e315b-130">To support users who are not homed on Exchange servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy archiving storage using a SQL Server database.</span></span> <span data-ttu-id="e315b-131">Skype pour Business Server prend en charge les versions 64 bits suivantes de SQL Server :</span><span class="sxs-lookup"><span data-stu-id="e315b-131">Skype for Business Server supports the following 64-bit versions of SQL Server:</span></span>
    
  - <span data-ttu-id="e315b-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e315b-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
  - <span data-ttu-id="e315b-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="e315b-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
  - <span data-ttu-id="e315b-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e315b-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
  - <span data-ttu-id="e315b-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="e315b-135">Microsoft SQL Server 2012 Standard</span></span>
    
  - <span data-ttu-id="e315b-136">Entreprise 2014 de Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="e315b-136">Microsoft SQL Server 2014 Enterprise</span></span>
    
  - <span data-ttu-id="e315b-137">Microsoft SQL Server 2014 Standard</span><span class="sxs-lookup"><span data-stu-id="e315b-137">Microsoft SQL Server 2014 Standard</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e315b-138">Versions de Microsoft SQL Server Express ne sont pas pris en charge pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="e315b-138">Microsoft SQL Server Express versions are not supported for archiving.</span></span> <span data-ttu-id="e315b-139">versions 32 bits de SQL Server ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e315b-139">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="e315b-140">Pour des exigences de SQL Server et des restrictions supplémentaires, voir [Configuration requise pour votre Skype pour environnement d’entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e315b-140">For additional SQL Server requirements and restrictions, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
    <span data-ttu-id="e315b-141">Vous devez paramétrer les plates-formes SQL Server avant de déployer et d’activation de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="e315b-141">You must set up the SQL Server platforms prior to deploying and enabling archiving.</span></span> <span data-ttu-id="e315b-142">Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="e315b-142">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="e315b-143">Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.</span><span class="sxs-lookup"><span data-stu-id="e315b-143">You can also create the database later, included as part of the installation procedure.</span></span> <span data-ttu-id="e315b-144">Pour plus d’informations sur SQL Server, voir [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span><span class="sxs-lookup"><span data-stu-id="e315b-144">For details about SQL Server, see the [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span></span>
    
    <span data-ttu-id="e315b-145">L’augmentation de la charge pour cause d’archivage peut être importante.</span><span class="sxs-lookup"><span data-stu-id="e315b-145">The load increase for archiving can be significant.</span></span> <span data-ttu-id="e315b-146">Par conséquent, vous devez vous assurer que l’espace disque est suffisant pour les serveurs frontaux sur lesquels l’archivage est activé.</span><span class="sxs-lookup"><span data-stu-id="e315b-146">Therefore, you should ensure that disk space is adequate for Front End Servers on which archiving is enabled.</span></span>
    

