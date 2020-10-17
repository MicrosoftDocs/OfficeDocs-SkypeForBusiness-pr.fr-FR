---
title: 'Lync Server 2013 : collecte de données'
description: 'Lync Server 2013 : collecte de données.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1808a68081ee453a56eabdaf264eb53ab5a1ef4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553780"
---
# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="92eaf-103">Collecte de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92eaf-103">Data collection in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92eaf-104">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="92eaf-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="92eaf-105">Dans le logiciel de communication Microsoft Lync Server 2013, vous pouvez exécuter l’outil de planification de Microsoft Lync Server 2013, sans documenter les adresses IP et les noms de domaine complets existants et proposés, mais il est beaucoup plus difficile de le faire sans provoquer d’erreurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="92eaf-105">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="92eaf-106">Par exemple, si la coexistence est requise pendant un certain temps, une erreur fréquente consiste à réutiliser les noms de domaine complets d’un déploiement Edge existant pour votre déploiement Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="92eaf-106">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="92eaf-107">Inscrire les adresses IP existantes et proposées ainsi que les FQDN dans une feuille de calcul, un tableau ou un autre formulaire visuel peut vous aider à prévenir les problèmes de configuration lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="92eaf-107">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="92eaf-108">Si vous avez utilisé les versions précédentes de l’outil de planification, vous avez peut-être utilisé l’outil pour créer votre topologie, ainsi que le document de topologie exporté à utiliser dans le générateur de topologie pour publier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="92eaf-108">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="92eaf-109">La possibilité d’exporter la topologie a été supprimée de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="92eaf-109">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="92eaf-110">L’utilisation d’une version précédente de l’outil de planification pour créer un document de topologie pour Lync Server 2013 est fortement déconseillée et produira des résultats inattendus.</span><span class="sxs-lookup"><span data-stu-id="92eaf-110">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="92eaf-111">Par conséquent, l’approche recommandée consiste à utiliser le modèle de collecte de données suivant, qui correspond à votre topologie Edge, afin de collecter les différents nom de domaine complet et adresses IP que vous devrez entrer dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="92eaf-111">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="92eaf-112">En documentant la configuration actuelle et proposée, vous pouvez saisir les valeurs dans le contexte approprié pour votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="92eaf-112">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="92eaf-113">Et vous devez réfléchir à la façon dont vous configurerez la coexistence et les fonctionnalités comme les URL simples, les partages de fichiers et l’équilibrage de charge.</span><span class="sxs-lookup"><span data-stu-id="92eaf-113">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="92eaf-114">Pour déployer correctement Microsoft Lync Server 2013, vous devez comprendre l’interaction et la dépendance des composants individuels.</span><span class="sxs-lookup"><span data-stu-id="92eaf-114">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="92eaf-115">En collectant des données à partir de votre infrastructure réseau et serveur existante et en appliquant les instructions de planification de ces sections, vous pouvez intégrer les composants de serveur Edge Lync Server 2013 à votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="92eaf-115">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="92eaf-116">Introduit dans [le choix d’une topologie dans Lync Server 2013](lync-server-2013-choosing-a-topology.md), il existe trois architectures principales avec deux variantes, pour un total de cinq scénarios de déploiement possibles.</span><span class="sxs-lookup"><span data-stu-id="92eaf-116">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="92eaf-117">L’un de ces scénarios sera le point de départ de votre collection de données.</span><span class="sxs-lookup"><span data-stu-id="92eaf-117">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="92eaf-118">Les adresses IP, noms de serveurs et noms de domaines sont des exemples qui coïncident avec les certificat, pare-feu et diagrammes DNS correspondants qui détaillent les informations requises pour une solution de planification complète.</span><span class="sxs-lookup"><span data-stu-id="92eaf-118">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="92eaf-119">Les diagrammes et le remplissage des valeurs requises de votre certificat, DNS et pare-feu sont particulièrement importants dans les communications inter-équipes, où la gestion de l’autorité de certification, de la configuration du pare-feu et du DNS est assurée par d’autres équipes que celle qui planifie le déploiement.</span><span class="sxs-lookup"><span data-stu-id="92eaf-119">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="92eaf-120">Les diagrammes fournissent des informations sur les composants requis qui peuvent être utilisées pour communiquer ces exigences pour la collaboration inter-équipes.</span><span class="sxs-lookup"><span data-stu-id="92eaf-120">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="92eaf-121">Les diagrammes fournis sont volontairement génériques, mais prennent en compte la collection de toutes les données pertinentes nécessaires à la communication des exigences dans un scénario entre équipes où la gestion du réseau, du pare-feu, la création et la gestion de certificats, le déploiement de serveur et la gestion de serveur sont assurés par différents groupes.</span><span class="sxs-lookup"><span data-stu-id="92eaf-121">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="92eaf-122">Le fait de disposer des informations requises pour la configuration de la mise en réseau, des pare-feu, des ports et des protocoles, des certificats et des serveurs est inestimable lorsque le déploiement de Lync Server est en cours.</span><span class="sxs-lookup"><span data-stu-id="92eaf-122">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="92eaf-123">**Serveur Edge et pool de serveurs Edge**</span><span class="sxs-lookup"><span data-stu-id="92eaf-123">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="92eaf-124">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="92eaf-124">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="92eaf-125">**Proxy inverse**</span><span class="sxs-lookup"><span data-stu-id="92eaf-125">**Reverse Proxy**</span></span>

<span data-ttu-id="92eaf-126">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="92eaf-126">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="92eaf-127">**Directeur ou pool directeur**</span><span class="sxs-lookup"><span data-stu-id="92eaf-127">**Director or Director pool**</span></span>

<span data-ttu-id="92eaf-128">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="92eaf-128">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

