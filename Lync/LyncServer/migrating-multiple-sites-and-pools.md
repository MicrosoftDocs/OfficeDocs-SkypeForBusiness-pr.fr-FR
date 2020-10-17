---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d95f38ab0adc1457abee7cdd90e8f385f7176ce3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527361"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="c37c3-102">Migration de plusieurs sites et pools</span><span class="sxs-lookup"><span data-stu-id="c37c3-102">Migrating multiple sites and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c37c3-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c37c3-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c37c3-104">Lync Server 2013 prend en charge les déploiements multisites et à plusieurs pools.</span><span class="sxs-lookup"><span data-stu-id="c37c3-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="c37c3-105">Le processus de migration de plusieurs pools de Lync Server 2010 vers Lync Server 2013 nécessite les considérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c37c3-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="c37c3-106">Après avoir déployé un pool pilote Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Lync Server 2013, ainsi qu’une méthodologie pour la validation de la fonctionnalité des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c37c3-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="c37c3-107">Par exemple, après avoir déplacé un utilisateur vers le pool pilote, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c37c3-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="c37c3-108">Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c37c3-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="c37c3-109">Après avoir effectué la transition des itinéraires fédérés des serveurs Edge Lync Server 2010 vers les serveurs Edge de Lync Server 2013, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c37c3-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="c37c3-110">Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool Lync Server 2010 est vide.</span><span class="sxs-lookup"><span data-stu-id="c37c3-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="c37c3-111">Après avoir vérifié que le pool Lync Server 2010 est vide, vous pouvez désactiver le pool.</span><span class="sxs-lookup"><span data-stu-id="c37c3-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="c37c3-112">Pour plus d’informations sur la façon de désactiver le pool et les serveurs Lync Server 2010 hérités, voir [phase 8 : retirer les pools hérités](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="c37c3-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

