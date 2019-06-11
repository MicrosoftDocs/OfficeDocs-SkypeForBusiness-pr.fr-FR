---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="5af17-102">Processus de migration</span><span class="sxs-lookup"><span data-stu-id="5af17-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5af17-103">_**Dernière modification de la rubrique:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="5af17-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="5af17-104">La procédure de migration recommandée et prise en charge pour Lync Server 2013 est une procédure de migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="5af17-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="5af17-105">Cette rubrique décrit la raison pour laquelle vous devez utiliser la migration côte à côte et inclut également des informations sur la coexistence.</span><span class="sxs-lookup"><span data-stu-id="5af17-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="5af17-106">Migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="5af17-106">Side-by-Side Migration</span></span>

<span data-ttu-id="5af17-107">Dans presque chaque migration, utilisez le chemin de migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="5af17-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="5af17-108">Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 ainsi qu’un serveur correspondant exécutant Office Communications Server 2007 R2, puis vous transférez des opérations vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="5af17-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="5af17-109">S’il est nécessaire de revenir à la version R2 d’Office Communications Server 2007, vous ne pouvez pas déplacer les opérations vers les serveurs d’origine.</span><span class="sxs-lookup"><span data-stu-id="5af17-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="5af17-110">Notez que dans ce cas, toutes les réunions planifiées avec des clients mis à niveau ne fonctionneront pas et les clients devront également être mis à niveau vers une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="5af17-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="5af17-111">Tests de coexistence</span><span class="sxs-lookup"><span data-stu-id="5af17-111">Coexistence Testing</span></span>

<span data-ttu-id="5af17-112">Après avoir déployé Lync Server 2013 en parallèle avec Office Communications Server 2007 R2, la topologie correspond à un état de test de coexistence de Lync Server 2013 et d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="5af17-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="5af17-113">Dans cet État, il est important de tester et de garantir le bon fonctionnement des services, chaque site peut être administré et les clients peuvent communiquer avec leurs utilisateurs actuels et propriétaires.</span><span class="sxs-lookup"><span data-stu-id="5af17-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="5af17-114">Avant de procéder à la migration de tous les utilisateurs, il est très important de comprendre l’état de chacun d’eux et de garantir le fonctionnement correct de chaque déploiement.</span><span class="sxs-lookup"><span data-stu-id="5af17-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="5af17-115">En règle générale, la phase de test de coexistence existe tout au long des tests pilotes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5af17-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="5af17-116">Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant un certain temps pour garantir que la compatibilité et les fonctionnalités de l’application fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="5af17-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="5af17-117">Après le test pilote, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les applications et pools hérités d’Office Communications Server 2007 R2 sont obsolètes.</span><span class="sxs-lookup"><span data-stu-id="5af17-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

