---
title: 'Lync Server 2013 : vue d’ensemble de la jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81690d4f006b5c1df3ed001369cbe5c4b1f560b8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520851"
---
# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="84d36-102">Vue d’ensemble de la jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84d36-102">Overview of SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84d36-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="84d36-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="84d36-p101">Le déploiement d’une jonction SIP peut contribuer grandement à simplifier les télécommunications de votre organisation et à préparer celle-ci en vue des dernières améliorations apportées aux communications en temps réel. L’un des principaux avantages qu’offre le déploiement d’une jonction SIP est que vous pouvez consolider les connexions de votre organisation vers le réseau téléphonique commuté (PSTN) sur le site central, contrairement à la jonction TDM, qui nécessite une jonction séparée pour chaque site de succursale vers le site central.</span><span class="sxs-lookup"><span data-stu-id="84d36-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="84d36-106">Jonction SIP dans Lync Server</span><span class="sxs-lookup"><span data-stu-id="84d36-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="84d36-107">Les fonctionnalités de jonction SIP de Lync Server 2013 permettent les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="84d36-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="84d36-108">Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou un appel longue distance au format E.164 qui aboutit sur le réseau PSTN en tant que service du fournisseur de service correspondant.</span><span class="sxs-lookup"><span data-stu-id="84d36-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="84d36-109">Chaque abonné PSTN peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) associé à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84d36-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="84d36-110">Économies</span><span class="sxs-lookup"><span data-stu-id="84d36-110">Cost Savings</span></span>

<span data-ttu-id="84d36-111">Les économies associées à la jonction SIP peuvent être substantielles :</span><span class="sxs-lookup"><span data-stu-id="84d36-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="84d36-112">Les appels longue distance coûtent en général moins cher via une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="84d36-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="84d36-113">Vous pouvez réduire les coûts de gestion et la complexité du déploiement.</span><span class="sxs-lookup"><span data-stu-id="84d36-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="84d36-p102">Les coûts d’accès de base (Basic rate interface, BRI) et d’accès primaire (Primary Rate Interface, PRI) sont éliminés si vous connectez une jonction SIP directement à votre fournisseur de services de téléphonie Internet pour un coût nettement plus bas. Avec une jonction TDM, les fournisseurs de service facturent les appels à la minute. Le coût d’une jonction SIP peut être basé sur l’utilisation de la bande passante, que vous pouvez acheter en plus petites tranches plus économiques. (Le coût réel dépend du modèle de service du fournisseur de services de téléphonie Internet que vous choisissez.)</span><span class="sxs-lookup"><span data-stu-id="84d36-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="84d36-118">Jonction SIP comparée à l’hébergement d’une passerelle PSTN ou d’un PBX IP</span><span class="sxs-lookup"><span data-stu-id="84d36-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="84d36-p103">Étant donné que les jonctions SIP se connectent directement à votre fournisseur de service, vous pouvez éliminer les passerelles PSTN et éviter le coût et la complexité de leur gestion. L’utilisation d’une jonction SIP peut se traduire par des économies substantielles, car les tâches de maintenance et d’administration sont réduites.</span><span class="sxs-lookup"><span data-stu-id="84d36-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="84d36-121">Services VoIP étendus</span><span class="sxs-lookup"><span data-stu-id="84d36-121">Expanded VoIP Services</span></span>

<span data-ttu-id="84d36-122">Bénéficier de fonctionnalités vocales est souvent la principale motivation pour déployer une jonction SIP, mais la prise en charge de fonctionnalités vocales n’est que la première étape.</span><span class="sxs-lookup"><span data-stu-id="84d36-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="84d36-123">Avec la jonction SIP, vous pouvez étendre les fonctionnalités VoIP et activer Lync Server 2013 pour offrir un ensemble de services plus riche.</span><span class="sxs-lookup"><span data-stu-id="84d36-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="84d36-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="84d36-124">For example:</span></span>

  - <span data-ttu-id="84d36-125">La détection de présence améliorée pour les appareils qui n’exécutent pas Lync Server 2013 peut offrir une meilleure intégration avec les téléphones mobiles, ce qui vous permet de savoir quand un utilisateur est sur un téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="84d36-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="84d36-126">Le service d’appels d’urgence E9-1-1 permet aux services de secours qui répondent aux appels d’urgence de déterminer l’emplacement de la personne qui appelle à partir de son numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="84d36-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84d36-127">Contactez votre fournisseur de services de téléphonie Internet pour savoir quels services il prend en charge et peut activer pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="84d36-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

