---
title: Basculement du magasin central de gestion dans Lync Server 2013
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
ms.openlocfilehash: 38bde96b74fa1c00fc937a159c5e8e40df42d4dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="ebc45-102">Basculement du magasin central de gestion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebc45-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebc45-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ebc45-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ebc45-104">Le magasin de gestion central contient des données de configuration relatives aux serveurs et services dans votre déploiement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ebc45-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="ebc45-105">Il fournit un stockage fiable schematized des données nécessaires pour définir, configurer, gérer, gérer, décrire et utiliser un déploiement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ebc45-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="ebc45-106">Il valide également les données afin de garantir la cohérence de la configuration.</span><span class="sxs-lookup"><span data-stu-id="ebc45-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="ebc45-107">Chaque déploiement Lync inclut un magasin de gestion central, hébergé par le serveur principal d’un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="ebc45-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="ebc45-108">Lorsque vous établissez une jumelage de réserve qui inclut le pool hébergeant le magasin central de gestion, une base de données de magasin de gestion centrale de sauvegarde est configurée dans le pool de sauvegarde, et les services du magasin de gestion centrale sont installés dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="ebc45-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="ebc45-109">À tout moment, l’une des deux bases de données de la Banque centrale de gestion est la forme de base active et l’autre est une réserve.</span><span class="sxs-lookup"><span data-stu-id="ebc45-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="ebc45-110">Le contenu est répliqué par le service de sauvegarde de la forme de base active vers la veille.</span><span class="sxs-lookup"><span data-stu-id="ebc45-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="ebc45-111">Au cours d’un basculement de pool qui implique les pools hébergeant la Banque centrale de gestion, l’administrateur doit basculer sur le magasin de gestion central avant d’avoir basculé sur le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="ebc45-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="ebc45-112">Une fois la récupération d’urgence effectuée, il n’est pas nécessaire de rebasculer le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="ebc45-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="ebc45-113">Après la réparation, le magasin de gestion central dans le pool de sauvegarde d’origine peut rester le maître actif.</span><span class="sxs-lookup"><span data-stu-id="ebc45-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="ebc45-114">Les objectifs d’ingénierie du basculement du magasin central de gestion sont les suivants : un objectif de durée de reprise (RTO) de 5 minutes et 5 minutes pour chaque objectif de point de reprise (RPO).</span><span class="sxs-lookup"><span data-stu-id="ebc45-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

