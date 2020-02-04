---
title: 'Lync Server 2013 : création d’une stratégie de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee1a13667e28ad374f538d61f6cfd941d31fade
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="5da9a-102">Établissement d’une stratégie de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5da9a-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5da9a-103">_**Dernière modification de la rubrique :** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="5da9a-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="5da9a-104">Pour pouvoir développer un plan de sauvegarde et de restauration pour Lync Server, vous devez développer une stratégie adaptée aux objectifs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5da9a-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="5da9a-105">Pour développer une stratégie efficace de sauvegarde et de restauration, vous devez :</span><span class="sxs-lookup"><span data-stu-id="5da9a-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="5da9a-106">Définissez les priorités de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="5da9a-106">Establish business priorities.</span></span>

  - <span data-ttu-id="5da9a-107">Identifiez les exigences de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="5da9a-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="5da9a-108">Établissement de priorités métiers</span><span class="sxs-lookup"><span data-stu-id="5da9a-108">Establishing Business Priorities</span></span>

<span data-ttu-id="5da9a-109">Évaluez les priorités des entreprises de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5da9a-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="5da9a-110">En règle générale, les priorités principales pour les entreprises qui affectent votre stratégie de sauvegarde et de restauration sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="5da9a-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="5da9a-111">Exigences de continuité d’activité</span><span class="sxs-lookup"><span data-stu-id="5da9a-111">Business continuity requirements</span></span>

  - <span data-ttu-id="5da9a-112">Exhaustivité des données</span><span class="sxs-lookup"><span data-stu-id="5da9a-112">Data completeness</span></span>

  - <span data-ttu-id="5da9a-113">Criticité des données</span><span class="sxs-lookup"><span data-stu-id="5da9a-113">Data criticality</span></span>

  - <span data-ttu-id="5da9a-114">Exigences en matière de portabilité</span><span class="sxs-lookup"><span data-stu-id="5da9a-114">Portability requirements</span></span>

  - <span data-ttu-id="5da9a-115">Contraintes de coût</span><span class="sxs-lookup"><span data-stu-id="5da9a-115">Cost constraints</span></span>

<span data-ttu-id="5da9a-116">Les besoins de votre entreprise, tels que ceux-ci, permettent de déterminer les contrats de niveau de service (SLA) que vous développez auprès de vos clients.</span><span class="sxs-lookup"><span data-stu-id="5da9a-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="5da9a-117">Les contrats de niveau de service influent grandement sur votre stratégie de sauvegarde et de récupération.</span><span class="sxs-lookup"><span data-stu-id="5da9a-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="5da9a-118">Identification des exigences de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="5da9a-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="5da9a-119">Les priorités de votre entreprise et les accords de niveau de service agissent pour déterminer les besoins de votre organisation pour la sauvegarde et la restauration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5da9a-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="5da9a-120">Identifiez et documentez vos exigences pour ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="5da9a-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="5da9a-121">**Fréquence des sauvegardes**   pour plus d’informations sur les meilleures pratiques en matière de fréquence de sauvegarde, voir [meilleures pratiques pour la sauvegarde et la restauration de Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="5da9a-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="5da9a-122">**Les outils**   de sauvegarde et de restauration incluent qui consiste à utiliser les outils, et sur quels ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="5da9a-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="5da9a-123">Pour plus d’informations sur les outils mentionnés dans cette rubrique et les autorisations nécessaires, voir [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5da9a-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="5da9a-124">**Emplacement de sauvegarde**   : Déterminez si les sauvegardes sont conservées localement ou à distance, en tenant compte de la sécurité et de l’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="5da9a-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="5da9a-125">Spécifiez le média à utiliser pour les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="5da9a-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="5da9a-126">**Les configurations**   matérielles et logicielles permettent de recenser et de documenter votre configuration matérielle et logicielle requise, y compris le matériel de sauvegarde et de restauration de composants spécifiques et toute connectivité logicielle et réseau requise pour la prise en charge de la sauvegarde et de la restauration.</span><span class="sxs-lookup"><span data-stu-id="5da9a-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="5da9a-127">Lorsque vous développez votre configuration matérielle et logicielle, n’oubliez pas les différents scénarios de restauration suivants.</span><span class="sxs-lookup"><span data-stu-id="5da9a-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="5da9a-128">**Scénarios de restauration**   Voici les processus de restauration des scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="5da9a-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="5da9a-129">Échec d’un pool de serveurs Lync.</span><span class="sxs-lookup"><span data-stu-id="5da9a-129">A Lync Server pool fails.</span></span> <span data-ttu-id="5da9a-130">Ce scénario nécessite la reconstitution de chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="5da9a-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="5da9a-131">Un serveur Standard Edition Server échoue.</span><span class="sxs-lookup"><span data-stu-id="5da9a-131">A Standard Edition server fails.</span></span> <span data-ttu-id="5da9a-132">Ce scénario nécessite la reconstitution du serveur sur un nouvel ordinateur ou un nouvel ordinateur et la restauration de bases de données.</span><span class="sxs-lookup"><span data-stu-id="5da9a-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="5da9a-133">Perte de la boutique centrale de gestion.</span><span class="sxs-lookup"><span data-stu-id="5da9a-133">Loss of the Central Management store.</span></span> <span data-ttu-id="5da9a-134">Ce scénario nécessite au minimum la restauration et la publication du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="5da9a-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="5da9a-135">Perte d’un serveur principal lorsque le magasin central de gestion continue de fonctionner correctement.</span><span class="sxs-lookup"><span data-stu-id="5da9a-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="5da9a-136">Ce scénario nécessite la reconstitution du serveur sur un nouvel ordinateur ou un nouvel ordinateur et la restauration de bases de données.</span><span class="sxs-lookup"><span data-stu-id="5da9a-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="5da9a-137">Un serveur qui fait partie d’un pool de serveurs Lync échoue.</span><span class="sxs-lookup"><span data-stu-id="5da9a-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="5da9a-138">Ce scénario nécessite le réfection du serveur sur un nouvel ordinateur ou un nouvel ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5da9a-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="5da9a-139">Un magasin de fichiers échoue.</span><span class="sxs-lookup"><span data-stu-id="5da9a-139">A File Store fails.</span></span> <span data-ttu-id="5da9a-140">Ce scénario nécessite la restauration du serveur de fichiers ou du groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="5da9a-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="5da9a-141">Une base de données de chat d’archivage, de surveillance ou persistante ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="5da9a-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="5da9a-142">Ce scénario nécessite une recréation des bases de données, et si les données sont importantes pour votre organisation, la restauration des données.</span><span class="sxs-lookup"><span data-stu-id="5da9a-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="5da9a-143">Il n’est pas nécessaire d’archiver, de surveiller et de discussions permanentes sur le serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="5da9a-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

