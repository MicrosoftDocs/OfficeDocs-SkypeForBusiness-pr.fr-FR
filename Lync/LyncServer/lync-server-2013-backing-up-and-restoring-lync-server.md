---
title: 'Lync Server 2013 : sauvegarde et restauration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="358c1-102">Sauvegarde et restauration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="358c1-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="358c1-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="358c1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="358c1-104">Cette section présente les meilleures pratiques en matière de sauvegarde de vos données 2013 Lync Server et de restauration en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="358c1-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="358c1-105">Ces bonnes pratiques s’appliquent aux situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="358c1-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="358c1-106">Un pool de serveurs Lync de n’importe quel type (serveur frontal, serveur Edge, serveur de médiation, serveur de chat permanent ou directeur), ou un serveur individuel dans l’un de ces groupes.</span><span class="sxs-lookup"><span data-stu-id="358c1-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="358c1-107">Serveur de gestion central</span><span class="sxs-lookup"><span data-stu-id="358c1-107">The Central Management Server</span></span>

  - <span data-ttu-id="358c1-108">Un serveur Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="358c1-108">A Standard Edition server</span></span>

  - <span data-ttu-id="358c1-109">Serveur principal d’Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="358c1-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="358c1-110">Magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="358c1-110">A File Store</span></span>

  - <span data-ttu-id="358c1-111">Une base de données d’archivage, une base de données de surveillance ou une base de données de chat permanent</span><span class="sxs-lookup"><span data-stu-id="358c1-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="358c1-112">Cette section n’inclut pas d’informations sur la restauration d’un site entier ou sur le développement d’un site de secours.</span><span class="sxs-lookup"><span data-stu-id="358c1-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="358c1-113">Pour plus d’informations sur le développement d’une solution de reprise après sinistre avec des listes frontales couplées, voir [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="358c1-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="358c1-114">Il s’agit de la méthode recommandée pour la planification de la reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="358c1-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="358c1-115">Si vous avez déployé des pools frontaux couplés, si l’un de ces groupes échoue et devient irrécupérable, vous pouvez restaurer ce pool avec un nouveau nom de domaine complet (FQDN) du pool couplé.</span><span class="sxs-lookup"><span data-stu-id="358c1-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="358c1-116">Pour plus d’informations sur la procédure d’exécution de cette récupération, voir [échec d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="358c1-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="358c1-117">Par ailleurs, si vous voulez recréer un pool failed et unrécupérable qui faisait partie d’une paire frontale, vous pouvez suivre la procédure décrite dans la section [exécution d’un basculement de pool frontal ABC dans Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="358c1-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="358c1-118">La méthodologie décrite dans ce document implique des considérations spéciales lors de la phase de planification.</span><span class="sxs-lookup"><span data-stu-id="358c1-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="358c1-119">Pour plus d’informations, reportez-vous à [la rubrique établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="358c1-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="358c1-120">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="358c1-120">In This Section</span></span>

  - [<span data-ttu-id="358c1-121">Préparation pour la sauvegarde et la restauration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="358c1-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="358c1-122">Sauvegarder des données et des paramètres dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="358c1-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="358c1-123">Restauration de données et de paramètres dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="358c1-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="358c1-124">Sauvegarder et restaurer des feuilles de calcul pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="358c1-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

