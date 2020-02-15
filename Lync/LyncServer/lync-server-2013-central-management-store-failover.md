---
title: Basculement du magasin central de gestion Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be877275c2d5f70b7a7038b55f5d42f887ba1739
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="9f872-102">Basculement du magasin central de gestion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f872-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f872-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9f872-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9f872-104">Le magasin central de gestion contient des données de configuration sur les serveurs et les services dans votre déploiement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9f872-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="9f872-105">Il fournit un stockage robuste et schématisées des données nécessaires pour définir, configurer, gérer, gérer, décrire et exploiter un déploiement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9f872-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="9f872-106">Il valide également les données afin de garantir la cohérence de la configuration.</span><span class="sxs-lookup"><span data-stu-id="9f872-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="9f872-107">Chaque déploiement Lync comprend un magasin central de gestion, hébergé par le serveur principal d’un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9f872-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="9f872-108">Lorsque vous établissez un jumelage de pools qui inclut le pool qui héberge le magasin central de gestion, une base de données du magasin central de gestion de sauvegarde est configurée dans le pool de sauvegarde et les services du magasin central de gestion sont installés dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="9f872-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="9f872-109">À tout moment, l’une des deux bases de données du magasin central de gestion est la forme de base active et l’autre est une mise en veille.</span><span class="sxs-lookup"><span data-stu-id="9f872-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="9f872-110">Le contenu est répliqué par le service de sauvegarde de la forme de base active vers la mise en veille.</span><span class="sxs-lookup"><span data-stu-id="9f872-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="9f872-111">Au cours d’un basculement de pool qui implique les pools hébergeant le magasin central de gestion, l’administrateur doit basculer le magasin central de gestion avant de basculer sur le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9f872-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="9f872-112">Une fois le sinistre réparé, il n’est pas nécessaire de restaurer le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="9f872-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="9f872-113">Après la réparation, le magasin central de gestion dans le pool de sauvegarde d’origine peut demeurer comme la forme de base active.</span><span class="sxs-lookup"><span data-stu-id="9f872-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="9f872-114">Les objectifs d’ingénierie du basculement du magasin central de gestion sont de 5 minutes pour l’objectif de temps de récupération (RTO) et de 5 minutes pour l’objectif de point de récupération (RPO).</span><span class="sxs-lookup"><span data-stu-id="9f872-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

