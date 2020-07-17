---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6efbad7107109096a5f17d82912353e6f8a1a14a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="805ed-102">Migration de plusieurs sites et pools</span><span class="sxs-lookup"><span data-stu-id="805ed-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="805ed-103">_**Dernière modification de la rubrique :** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="805ed-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="805ed-104">Lync Server 2013 prend en charge les déploiements multisites et à plusieurs pools.</span><span class="sxs-lookup"><span data-stu-id="805ed-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="805ed-105">Le processus de migration de plusieurs pools à partir d’Office Communications Server 2007 R2 vers Lync Server 2013 requiert les considérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="805ed-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="805ed-106">Après avoir déployé un pool pilote Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Lync Server 2013, ainsi qu’une méthodologie pour la validation de la fonctionnalité des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="805ed-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="805ed-107">Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="805ed-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="805ed-108">Après avoir effectué la transition des itinéraires fédérés des serveurs Edge Office Communications Server 2007 R2 vers les serveurs Edge de Lync Server 2013 pilotes, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="805ed-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="805ed-109">Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool Office Communications Server 2007 R2 est vide.</span><span class="sxs-lookup"><span data-stu-id="805ed-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="805ed-110">Après avoir vérifié que le pool Office Communications Server 2007 R2 est vide, vous pouvez désactiver le pool.</span><span class="sxs-lookup"><span data-stu-id="805ed-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="805ed-111">Pour plus d’informations sur la façon de désactiver le pool et les serveurs Office Communications Server 2007 R2 hérités, voir [phase 10 : decommission Legacy site](phase-10-decommission-legacy-site.md).</span><span class="sxs-lookup"><span data-stu-id="805ed-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

