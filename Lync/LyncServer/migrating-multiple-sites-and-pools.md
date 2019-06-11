---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7759c52051dfe4ca4a46e105e6a33f3284f334e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="e63e4-102">Migration de plusieurs sites et pools</span><span class="sxs-lookup"><span data-stu-id="e63e4-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e63e4-103">_**Dernière modification de la rubrique:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e63e4-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e63e4-104">Lync Server 2013 prend en charge les déploiements multisites et à plusieurs pools.</span><span class="sxs-lookup"><span data-stu-id="e63e4-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="e63e4-105">Le processus de migration de plusieurs pools de Lync Server 2010 vers Lync Server 2013 nécessite les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="e63e4-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="e63e4-106">Après le déploiement d’un pool de pilotes de Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilote qui seront déplacés vers le pool Lync Server 2013 et une méthodologie permettant de valider les fonctionnalités des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e63e4-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="e63e4-107">Par exemple, après le déplacement d’un utilisateur vers le pool de pilotes, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e63e4-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="e63e4-108">Après le déploiement d’un serveur de périphérie dans le pool de pilotes, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e63e4-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="e63e4-109">Après avoir basculé les itinéraires fédérés de Lync Server 2010 Edge Server vers les serveurs de périphérie de Lync Server 2013, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e63e4-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="e63e4-110">Après avoir déplacé tous les utilisateurs et les objets de contact non-utilisateur, vous devez vérifier que le pool Lync Server 2010 est vide.</span><span class="sxs-lookup"><span data-stu-id="e63e4-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="e63e4-111">Après avoir vérifié que le pool Lync Server 2010 est vide, vous pouvez désactiver le pool.</span><span class="sxs-lookup"><span data-stu-id="e63e4-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="e63e4-112">Pour plus d’informations sur la désactivation du pool et des serveurs hérités de Lync Server 2010, voir [phase 8: désactiver](phase-8-decommission-legacy-pools.md)les pools hérités.</span><span class="sxs-lookup"><span data-stu-id="e63e4-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

