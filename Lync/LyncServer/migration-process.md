---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53021b37baca7a859c79a6c47bfbf3d587a3466d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="dc775-102">Processus de migration</span><span class="sxs-lookup"><span data-stu-id="dc775-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc775-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="dc775-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="dc775-104">La procédure de migration recommandée et prise en charge pour Lync Server 2013 est une migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="dc775-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="dc775-105">Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et inclut des informations sur les tests de coexistence.</span><span class="sxs-lookup"><span data-stu-id="dc775-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="dc775-106">Migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="dc775-106">Side-By-Side Migration</span></span>

<span data-ttu-id="dc775-107">Dans presque chaque migration, utilisez le chemin de migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="dc775-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="dc775-108">Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 avec un serveur correspondant exécutant Lync Server 2010, puis transférez les opérations sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="dc775-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="dc775-109">S’il est nécessaire de revenir à Lync Server 2010, vous ne pouvez pas déplacer les opérations vers les serveurs d’origine.</span><span class="sxs-lookup"><span data-stu-id="dc775-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="dc775-110">Notez que dans ce cas, toutes les réunions planifiées avec des clients mis à niveau ne fonctionneront pas et les clients devront également être mis à niveau vers une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="dc775-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="dc775-111">Tests de coexistence</span><span class="sxs-lookup"><span data-stu-id="dc775-111">Coexistence Testing</span></span>

<span data-ttu-id="dc775-112">Après avoir déployé Lync Server 2013 en parallèle avec Lync Server 2010, le déploiement représente un état de test de coexistence de Lync Server 2013 et de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dc775-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="dc775-113">Dans cet État, il est important de tester et de veiller à ce que les services soient démarrés, chaque site peut être administré et les clients peuvent communiquer avec leurs utilisateurs actuels et propriétaires.</span><span class="sxs-lookup"><span data-stu-id="dc775-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="dc775-114">Avant de procéder à la migration de tous les utilisateurs, il est très important de comprendre l’état de chacun d’eux et de garantir le fonctionnement correct de chaque déploiement.</span><span class="sxs-lookup"><span data-stu-id="dc775-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="dc775-115">En règle générale, la phase de test de coexistence existe tout au long des tests pilotes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc775-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="dc775-116">Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant un certain temps pour garantir que la compatibilité et les fonctionnalités de l’application fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="dc775-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="dc775-117">Après le test pilote, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les applications et pools hérités de Lync Server 2010 sont obsolètes.</span><span class="sxs-lookup"><span data-stu-id="dc775-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

