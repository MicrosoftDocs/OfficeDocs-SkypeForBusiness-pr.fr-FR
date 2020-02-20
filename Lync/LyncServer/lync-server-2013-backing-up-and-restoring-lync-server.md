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
ms.openlocfilehash: b2dd48b7a4357fef2f848210a52313ae334b608b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="47769-102">Sauvegarde et restauration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47769-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47769-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="47769-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="47769-104">Dans cette section, vous trouverez les meilleures pratiques de sauvegarde de vos données Lync Server 2013 et de restauration en cas de défaillance.</span><span class="sxs-lookup"><span data-stu-id="47769-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="47769-105">Ces meilleures pratiques s’appliquent aux situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="47769-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="47769-106">Un pool Lync Server entier de n’importe quel type (serveur frontal, serveur Edge, serveur de médiation, serveur de conversation permanente ou directeur) ou un serveur individuel dans l’un de ces pools.</span><span class="sxs-lookup"><span data-stu-id="47769-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="47769-107">Le serveur de gestion centralisée</span><span class="sxs-lookup"><span data-stu-id="47769-107">The Central Management Server</span></span>

  - <span data-ttu-id="47769-108">Un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="47769-108">A Standard Edition server</span></span>

  - <span data-ttu-id="47769-109">Un serveur principal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="47769-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="47769-110">Un magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="47769-110">A File Store</span></span>

  - <span data-ttu-id="47769-111">Une base de données d’archivage, une base de données de surveillance ou une base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="47769-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="47769-112">Cette section n’inclut pas d’informations sur la restauration d’un site entier ou sur le développement d’un site de secours.</span><span class="sxs-lookup"><span data-stu-id="47769-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="47769-113">Pour plus d’informations sur le développement d’une solution de récupération d’urgence avec des pools frontaux couplés, consultez la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="47769-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="47769-114">Il s’agit de la méthode recommandée pour la planification de la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="47769-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="47769-115">Si vous avez déployé des pools frontaux couplés, si l’un de ces pools échoue et devient irrécupérable, vous pouvez restaurer ce pool avec un nouveau nom de domaine complet (FQDN) à partir de son pool associé.</span><span class="sxs-lookup"><span data-stu-id="47769-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="47769-116">Pour plus d’informations sur les étapes à suivre pour effectuer cette récupération, voir [basculement d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="47769-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="47769-117">Par ailleurs, si vous souhaitez recréer ultérieurement un pool défaillant et irrécupérable qui faisait partie d’une paire de serveurs frontaux, vous pouvez suivre les étapes décrites dans la section [exécution d’un basculement de pool frontal ABC dans Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="47769-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="47769-118">La méthodologie décrite dans ce document implique des considérations spécifiques lors de la phase de planification.</span><span class="sxs-lookup"><span data-stu-id="47769-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="47769-119">Pour plus d’informations, reportez-vous à [la rubrique établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="47769-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47769-120">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="47769-120">In This Section</span></span>

  - [<span data-ttu-id="47769-121">Préparation de la sauvegarde et de la restauration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47769-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="47769-122">Sauvegarde des données et des paramètres dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47769-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="47769-123">Restauration des données et des paramètres dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47769-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="47769-124">Feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47769-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

