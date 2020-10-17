---
title: 'Lync Server 2013 : planification de voix entreprise'
description: 'Lync Server 2013 : planification de voix entreprise.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dfa0d91fe8270e49524d648ef403cd69ede2407
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571850"
---
# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="e8b32-103">Planification de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-103">Planning for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8b32-104">_**Dernière modification de la rubrique :** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="e8b32-104">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="e8b32-105">Le processus de déploiement de voix entreprise dépend de votre topologie existante, de votre infrastructure et des fonctionnalités vocales de l’entreprise que vous souhaitez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="e8b32-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="e8b32-106">Les procédures requises dépendront des fonctionnalités que vous choisirez, mais vous devrez tenir compte d’autres facteurs pour la planification à un niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="e8b32-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="e8b32-107">En règle générale, tenez compte du type et du nombre de sites que vous voulez déployer et de leur emplacement géographique, du volume d’appels sur chaque site, des types de liens réseaux qui relient les sites, si vous souhaitez offrir la redondance et le basculement pour la fonctionnalité voix pour chaque site, et enfin si vous voulez utiliser l’équipement PBX existant.</span><span class="sxs-lookup"><span data-stu-id="e8b32-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="e8b32-108">Certaines considérations, telles que la haute disponibilité, doivent être prises en compte lors de la planification du logiciel de communication Lync Server dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="e8b32-108">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="e8b32-109">Ces considérations sont traitées dans les rubriques de cette section, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="e8b32-109">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="e8b32-110">Considérations sur la planification</span><span class="sxs-lookup"><span data-stu-id="e8b32-110">Planning Considerations</span></span>

<span data-ttu-id="e8b32-111">Pour les décisions de planification relatives au déploiement d’une fonctionnalité voix entreprise ou d’un scénario ou d’un composant de déploiement spécifiques, consultez les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="e8b32-111">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="e8b32-112">Définition de la configuration requise pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-112">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="e8b32-113">Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-113">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="e8b32-114">Paramètres réseau pour les fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-114">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="e8b32-115">Composants requis pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-115">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="e8b32-116">Planification de la résistance voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-116">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="e8b32-117">Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-117">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="e8b32-118">Planification du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-118">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="e8b32-119">Planification des services d’urgence (E9-1-1) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-119">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="e8b32-120">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-120">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="e8b32-121">Planification des lignes téléphoniques privées avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-121">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="e8b32-122">Planification du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-122">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="e8b32-123">Planification de la résistance voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-123">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="e8b32-124">Instructions de déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-124">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="e8b32-125">Vue d’ensemble du processus de déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-125">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="e8b32-126">Transfert d’utilisateurs vers voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-126">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="e8b32-127">Outil de diagnostic de préappel Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b32-127">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

