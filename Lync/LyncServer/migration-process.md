---
title: Processus de migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a31a127ef3a37ed366117247dd68c192d19e691
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="fdc76-102">Processus de migration</span><span class="sxs-lookup"><span data-stu-id="fdc76-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdc76-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="fdc76-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="fdc76-104">La procédure de migration recommandée et prise en charge pour Lync Server 2013 est une migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="fdc76-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="fdc76-105">Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et fournit également des informations sur les tests de coexistence.</span><span class="sxs-lookup"><span data-stu-id="fdc76-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="fdc76-106">Migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="fdc76-106">Side-By-Side Migration</span></span>

<span data-ttu-id="fdc76-107">Il est recommandé d’appliquer la migration côte à côte dans pratiquement toutes les migrations.</span><span class="sxs-lookup"><span data-stu-id="fdc76-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="fdc76-108">Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 avec un serveur correspondant exécutant Lync Server 2010, puis transférez des opérations vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="fdc76-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="fdc76-109">S’il s’avère nécessaire de restaurer Lync Server 2010, vous ne pouvez basculer les opérations vers les serveurs d’origine.</span><span class="sxs-lookup"><span data-stu-id="fdc76-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="fdc76-110">Sachez que dans cette situation, toute nouvelle réunion planifiée avec les clients mis à niveau ne fonctionnera pas, et que les clients devront également être rétrogradés.</span><span class="sxs-lookup"><span data-stu-id="fdc76-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="fdc76-111">Test de coexistence</span><span class="sxs-lookup"><span data-stu-id="fdc76-111">Coexistence Testing</span></span>

<span data-ttu-id="fdc76-112">Une fois que vous avez déployé Lync Server 2013 en parallèle avec Lync Server 2010, le déploiement représente un état de test de coexistence de Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fdc76-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="fdc76-113">Dans cet État, il est important de tester et de vérifier que les services sont démarrés, que chaque site peut être administré et que les clients peuvent communiquer avec les utilisateurs actuels et hérités.</span><span class="sxs-lookup"><span data-stu-id="fdc76-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="fdc76-114">Avant la migration de tous les utilisateurs, il est très important de comprendre l’état de chaque déploiement et de veiller à ce que chaque déploiement soit opérationnel et fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="fdc76-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="fdc76-115">En règle générale, la phase de test de coexistence existe tout au long du test pilote de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdc76-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="fdc76-116">Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant une période de temps pour garantir le bon fonctionnement de la compatibilité et des fonctions des applications.</span><span class="sxs-lookup"><span data-stu-id="fdc76-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="fdc76-117">Une fois le test pilote effectué, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les pools hérités et les applications de Lync Server 2010 sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="fdc76-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

