---
title: 'Lync Server 2013 : établissement d’une stratégie de sauvegarde et de restauration'
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
ms.openlocfilehash: e281b85879063cacb9538d03fe221a4bf96b6bc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514211"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="a3ce1-102">Établissement d’une stratégie de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3ce1-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3ce1-103">_**Dernière modification de la rubrique :** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="a3ce1-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="a3ce1-104">Avant de pouvoir développer un plan de sauvegarde et de restauration pour Lync Server, vous devez développer une stratégie adaptée aux objectifs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="a3ce1-105">Pour développer une stratégie de sauvegarde et de restauration efficace, vous devez :</span><span class="sxs-lookup"><span data-stu-id="a3ce1-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="a3ce1-106">Établir les priorités de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-106">Establish business priorities.</span></span>

  - <span data-ttu-id="a3ce1-107">Identifier les besoins en matière de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="a3ce1-108">Définition des priorités de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="a3ce1-108">Establishing Business Priorities</span></span>

<span data-ttu-id="a3ce1-p102">Évaluez les priorités de votre organisation. Habituellement, les principales priorités de l’entreprise qui ont des répercussions sur votre stratégie de sauvegarde et de restauration sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3ce1-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="a3ce1-111">Besoins de continuité de l’activité</span><span class="sxs-lookup"><span data-stu-id="a3ce1-111">Business continuity requirements</span></span>

  - <span data-ttu-id="a3ce1-112">Exhaustivité des données</span><span class="sxs-lookup"><span data-stu-id="a3ce1-112">Data completeness</span></span>

  - <span data-ttu-id="a3ce1-113">Sensibilité des données</span><span class="sxs-lookup"><span data-stu-id="a3ce1-113">Data criticality</span></span>

  - <span data-ttu-id="a3ce1-114">Besoins de portabilité</span><span class="sxs-lookup"><span data-stu-id="a3ce1-114">Portability requirements</span></span>

  - <span data-ttu-id="a3ce1-115">Contraintes budgétaires</span><span class="sxs-lookup"><span data-stu-id="a3ce1-115">Cost constraints</span></span>

<span data-ttu-id="a3ce1-116">Les besoins de l’entreprise, tels que ceux-ci, permettent de déterminer les contrats de niveau de service (SLA) que vous développez avec vos clients.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="a3ce1-117">Les contrats de niveau de service influencent considérablement votre stratégie de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="a3ce1-118">Identification des besoins de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="a3ce1-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="a3ce1-119">Les priorités de votre entreprise et les contrats de niveau de service agissent dans la détermination de la configuration requise de votre organisation pour la sauvegarde et la restauration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="a3ce1-120">Identifiez et documentez vos besoins dans les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="a3ce1-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="a3ce1-121">**Fréquence des sauvegardes**     Pour plus d’informations sur les meilleures pratiques en matière de fréquence de sauvegarde, voir [Best Practices for Backup and Restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="a3ce1-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="a3ce1-122">Outils de sauvegarde **et de restauration**     Indiquez qui doit utiliser les outils et sur quels ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="a3ce1-123">Pour plus d’informations sur les outils présentés dans cette rubrique et les autorisations nécessaires, voir [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a3ce1-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="a3ce1-124">**Emplacement**     de sauvegarde Déterminez si les sauvegardes sont conservées localement ou à distance, tout en tenant compte de la sécurité et de l’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="a3ce1-125">Spécifiez les supports à utiliser pour les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="a3ce1-126">**Configuration matérielle et logicielle requise**     Identifiez et consignez les configurations matérielle et logicielle requises spécifiques, notamment le matériel de stockage de sauvegarde et de restauration de composants spécifiques, ainsi que les logiciels et la connectivité réseau requis pour prendre en charge la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="a3ce1-127">Au fur et à mesure que vous développez votre configuration matérielle et logicielle requise, gardez à l’esprit les divers scénarios de restauration ci-après.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="a3ce1-128">**Scénarios**     de restauration Voici les processus de restauration pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="a3ce1-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="a3ce1-129">Un pool Lync Server ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-129">A Lync Server pool fails.</span></span> <span data-ttu-id="a3ce1-130">Ce scénario requiert une nouvelle création de chaque serveur inclus dans le pool.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="a3ce1-131">Un serveur Standard Edition Server échoue.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-131">A Standard Edition server fails.</span></span> <span data-ttu-id="a3ce1-132">Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé ainsi que la restauration des bases de données.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="a3ce1-133">Perte du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-133">Loss of the Central Management store.</span></span> <span data-ttu-id="a3ce1-134">Au minimum, ce scénario nécessite la restauration et la publication du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="a3ce1-135">Perte d’un serveur principal lorsque le magasin central de gestion fonctionne toujours normalement.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="a3ce1-136">Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé ainsi que la restauration des bases de données.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="a3ce1-137">Un serveur qui est membre d’un pool Lync Server ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="a3ce1-138">Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="a3ce1-139">Un magasin de fichiers échoue.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-139">A File Store fails.</span></span> <span data-ttu-id="a3ce1-140">Ce scénario requiert la restauration du serveur de fichiers ou du cluster de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="a3ce1-141">Une base de données d’archivage, de surveillance ou de conversation permanente échoue.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="a3ce1-142">Ce scénario requiert une nouvelle création des bases de données et, si les données sont critiques pour l’organisation, une restauration des données.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="a3ce1-143">Les données d’archivage, de surveillance et de conversation permanente ne sont pas requises pour la sauvegarde et l’exécution de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

