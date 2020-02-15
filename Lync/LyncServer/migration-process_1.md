---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6eec7971665aa8e4494ca4509c92c406458cb08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="6ab85-102">Processus de migration</span><span class="sxs-lookup"><span data-stu-id="6ab85-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ab85-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="6ab85-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="6ab85-104">La procédure de migration recommandée et prise en charge pour Lync Server 2013 est la procédure de migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="6ab85-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="6ab85-105">Cette rubrique décrit les raisons pour lesquelles il est recommandé d’effectuer une migration côte à côte et inclut également des informations sur la coexistence.</span><span class="sxs-lookup"><span data-stu-id="6ab85-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="6ab85-106">Migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="6ab85-106">Side-by-Side Migration</span></span>

<span data-ttu-id="6ab85-107">Il est recommandé de pratiquer la migration côte à côte dans pratiquement toutes les migrations.</span><span class="sxs-lookup"><span data-stu-id="6ab85-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="6ab85-108">Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 avec un serveur correspondant exécutant Office Communications Server 2007 R2, puis vous transférez des opérations vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="6ab85-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="6ab85-109">S’il s’avère nécessaire de restaurer Office Communications Server 2007 R2, vous ne pouvez basculer les opérations vers les serveurs d’origine.</span><span class="sxs-lookup"><span data-stu-id="6ab85-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="6ab85-110">Sachez que dans cette situation, toute nouvelle réunion planifiée avec les clients mis à niveau ne fonctionnera pas, et que les clients devront également être rétrogradés.</span><span class="sxs-lookup"><span data-stu-id="6ab85-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="6ab85-111">Test de coexistence</span><span class="sxs-lookup"><span data-stu-id="6ab85-111">Coexistence Testing</span></span>

<span data-ttu-id="6ab85-112">Une fois que vous avez déployé Lync Server 2013 en parallèle avec Office Communications Server 2007 R2, la topologie représente un état de test de coexistence de Lync Server 2013 et Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6ab85-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6ab85-113">Dans cet état, il est important d’effectuer des tests et de vérifier que les services sont démarrés ; chaque site peut être administré, et les clients peuvent communiquer avec les utilisateurs actuels et hérités.</span><span class="sxs-lookup"><span data-stu-id="6ab85-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="6ab85-114">Avant la migration de tous les utilisateurs, il est très important de comprendre l’état de chaque déploiement et de veiller à ce que chaque déploiement soit opérationnel et fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="6ab85-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="6ab85-115">En règle générale, la phase de test de coexistence existe tout au long du test pilote de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ab85-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="6ab85-116">Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant une période de temps pour garantir le bon fonctionnement de la compatibilité et des fonctions des applications.</span><span class="sxs-lookup"><span data-stu-id="6ab85-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="6ab85-117">Une fois le test pilote effectué, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les pools hérités et les applications d’Office Communications Server 2007 R2 sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="6ab85-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

