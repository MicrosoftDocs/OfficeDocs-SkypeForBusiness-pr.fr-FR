---
title: Test de l’évolutivité de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4495524d7ac4e6348f86b84a8b5f860bd9a1db3f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="04936-102">Test de l’extensibilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04936-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04936-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="04936-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="04936-104">Lync Server 2013 fournit l’infrastructure de serveur pour toutes les communications Lync Server en temps réel, y compris la messagerie instantanée et la présence, les conférences et voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="04936-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="04936-105">Cela inclut toutes les fonctionnalités qui utilisent les ressources matérielles d’un pool Lync Server 2013 et, par conséquent, influent sur les performances et l’envergure.</span><span class="sxs-lookup"><span data-stu-id="04936-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="04936-106">Selon les organisations, les fonctionnalités ne sont pas toutes utilisées de la même façon.</span><span class="sxs-lookup"><span data-stu-id="04936-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="04936-107">À titre d’exemple, certaines organisations ont très souvent recours à la vidéo lors des conférences alors que d’autres l’utilisent peu ou pas du tout.</span><span class="sxs-lookup"><span data-stu-id="04936-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="04936-108">De la même façon, certaines organisations préfèrent le partage de présentations PowerPoint au partage d’application (ou inversement).</span><span class="sxs-lookup"><span data-stu-id="04936-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="04936-109">Les organisations qui déploient voix entreprise peuvent ou non utiliser l’application Response Group de manière intensive.</span><span class="sxs-lookup"><span data-stu-id="04936-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="04936-110">La plupart des organisations déploient des serveurs de surveillance, mais pas un grand nombre d’entre elles déploient des serveurs d’archivage.</span><span class="sxs-lookup"><span data-stu-id="04936-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="04936-111">Par ailleurs, toutes les organisations ne disposent pas d’infrastructures identiques, tant sur le plan des capacités matérielles ou réseau que du nombre et de la taille des pools déployés.</span><span class="sxs-lookup"><span data-stu-id="04936-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="04936-112">La diversité des fonctionnalités et infrastructures déployées complique les tests d’extensibilité, car il est impossible de simuler toutes les combinaisons possibles de fonctionnalités et d’infrastructures.</span><span class="sxs-lookup"><span data-stu-id="04936-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="04936-113">Pour déterminer la prise en charge de l’extensibilité pour Lync Server, nous procédons à des tests à l’aide de toutes les fonctionnalités Lync Server simultanément, en fonction d’un modèle d’utilisation moyen (modèle utilisateur).</span><span class="sxs-lookup"><span data-stu-id="04936-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="04936-114">Pour déterminer le modèle utilisateur approprié pour les charges de travail Lync Server, nous analysons de nombreux points de données, notamment les enquêtes des clients, les commentaires du programme d’amélioration de l’expérience utilisateur de Microsoft, les données d’utilisation de Lync Server du service informatique interne de Microsoft, et les données extraites de notre service Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="04936-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="04936-115">Dans de nombreux cas, le modèle utilisateur prévoit des charges de travail plus lourdes afin de laisser une marge de manœuvre confortable pour l’organisation.</span><span class="sxs-lookup"><span data-stu-id="04936-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="04936-116">Dans nos tests d’évolutivité, nous avons configuré les pools Lync Server 2013 conformément aux spécifications matérielles et logicielles recommandées, notamment les composants d’infrastructure, tels que les services de domaine Active Directory, les programmes d’équilibrage de la charge matérielle et les pare-feu.</span><span class="sxs-lookup"><span data-stu-id="04936-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="04936-117">Nous configurerons les environnements Lync Server aussi étroitement que possible dans des environnements réels standard.</span><span class="sxs-lookup"><span data-stu-id="04936-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="04936-118">Nous utilisons ensuite l’outil stress and performance de Lync Server 2013 pour simuler le chargement de Lync Server 2013 (en fonction de notre modèle utilisateur).</span><span class="sxs-lookup"><span data-stu-id="04936-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="04936-119">.</span><span class="sxs-lookup"><span data-stu-id="04936-119">.</span></span>

<span data-ttu-id="04936-p105">Nous effectuons plusieurs phases de tests d’extensibilité (sur plusieurs cycles de test de trois semaines chacun). Nous nous appuyons sur les résultats de l’ensemble des tests pour mieux régler les performances et vérifier la prise en charge des valeurs d’extensibilité dans notre modèle utilisateur.</span><span class="sxs-lookup"><span data-stu-id="04936-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

