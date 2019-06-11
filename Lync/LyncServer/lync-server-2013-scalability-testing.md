---
title: Test de l’évolutivité de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="ba710-102">Tests d’évolutivité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba710-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba710-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ba710-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ba710-104">Lync Server 2013 fournit l’infrastructure de serveur pour toutes les communications en temps réel de Lync Server, notamment la messagerie instantanée (mi) et la présence, la Conférence et la voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="ba710-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="ba710-105">Cela inclut toutes les fonctionnalités qui utilisent les ressources matérielles d’un pool Lync Server 2013 et, par conséquent, affectent les performances et l’évolutivité.</span><span class="sxs-lookup"><span data-stu-id="ba710-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="ba710-106">Toutes les organisations n’utilisent pas toutes les fonctionnalités de manière égale.</span><span class="sxs-lookup"><span data-stu-id="ba710-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="ba710-107">Par exemple, certaines organisations peuvent utiliser la vidéo dans les conférences de manière très importante alors que d’autres peuvent avoir peu ou pas d’utilisation de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="ba710-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="ba710-108">Certaines organisations préfèrent le partage de diapositives PowerPoint au partage d’application, tandis que d’autres préfèrent.</span><span class="sxs-lookup"><span data-stu-id="ba710-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="ba710-109">Les organisations qui déploient une voix entreprise peuvent ou ne peuvent pas utiliser énormément l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="ba710-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="ba710-110">La plupart des organisations déploient des serveurs de contrôle, mais pas la plupart d’entre eux déploient des serveurs d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ba710-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="ba710-111">De plus, les organisations n’ont pas toutes les mêmes infrastructures, notamment les capacités matérielles, les capacités du réseau, ainsi que le nombre de pools et de tailles de pools déployés.</span><span class="sxs-lookup"><span data-stu-id="ba710-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="ba710-112">La diversité des fonctionnalités et de l’infrastructure repose sur le défi des tests d’évolutivité: il n’est pas possible de simuler toutes les combinaisons possibles de fonctionnalités et d’infrastructures.</span><span class="sxs-lookup"><span data-stu-id="ba710-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="ba710-113">Pour déterminer la prise en charge de l’évolutivité de Lync Server, nous effectuons des tests en utilisant toutes les fonctionnalités du serveur Lync en même temps, en fonction d’un modèle d’utilisation moyenne (modèle utilisateur).</span><span class="sxs-lookup"><span data-stu-id="ba710-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="ba710-114">Pour déterminer un modèle utilisateur approprié pour des charges de travail Lync Server, nous analysons de nombreux points de données, notamment les enquêtes de clients, les commentaires du programme d’amélioration du produit de Microsoft, les données d’utilisation de Lync Server du département informatique interne de Microsoft. et données extraites de notre service Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="ba710-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="ba710-115">Dans de nombreux cas, le modèle utilisateur a une polarisation pour des charges plus lourdes afin de fournir une marge confortable pour l’utilisation au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="ba710-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="ba710-116">Dans nos tests d’évolutivité, nous configurerons les pools Lync Server 2013 conformément aux spécifications matérielles et logicielles recommandées, notamment les composants d’infrastructure, tels que les services de domaine Active Directory (AD FS), les équilibreurs de charge matérielle et les pare-feu.</span><span class="sxs-lookup"><span data-stu-id="ba710-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="ba710-117">Nous configurerons les environnements de serveur Lync de la même façon que possible dans les environnements réels.</span><span class="sxs-lookup"><span data-stu-id="ba710-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="ba710-118">L’outil de stress et de performance de Lync Server 2013 est ensuite utilisé pour simuler le chargement de Lync Server 2013 (en fonction de notre modèle d’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="ba710-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="ba710-119">.</span><span class="sxs-lookup"><span data-stu-id="ba710-119"></span></span>

<span data-ttu-id="ba710-120">Nous effectuons plusieurs itérations des tests d’évolutivité (y compris les séries de tests sur trois semaines).</span><span class="sxs-lookup"><span data-stu-id="ba710-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="ba710-121">Nous utilisons les résultats de tous les tests pour vous aider à optimiser les performances et à vérifier la prise en charge des numéros de modularité dans notre modèle d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ba710-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

