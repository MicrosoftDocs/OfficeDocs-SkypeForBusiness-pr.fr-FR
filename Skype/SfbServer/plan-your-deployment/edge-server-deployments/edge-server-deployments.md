---
title: Planifier le déploiement de serveurs de périphérie dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Résumé: planifiez votre environnement Edge Skype entreprise Server. Cette rubrique présente les concepts d’arête et vous permet de vous organiser grâce à de nouvelles rubriques détaillées.'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277159"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="2b1ae-104">Planifier le déploiement de serveurs de périphérie dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2b1ae-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="2b1ae-105">**Résumé:** Planifiez votre environnement Edge Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="2b1ae-106">Cette rubrique présente les concepts d’arête et vous permet de vous organiser grâce à de nouvelles rubriques détaillées.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="2b1ae-107">Lorsque vous disposez d’un environnement Skype entreprise Server qui fonctionne bien en interne, l’étape suivante consiste à introduire un serveur Edge ou un pool Edge pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="2b1ae-108">Ce rôle serait vital si vous souhaitez que les services fournis par Skype entreprise Server soient utilisés par des personnes extérieures à votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="2b1ae-109">Les éléments suivants peuvent éventuellement être:</span><span class="sxs-lookup"><span data-stu-id="2b1ae-109">These can potentially include:</span></span>
  
- <span data-ttu-id="2b1ae-110">Utilisateurs distants : employés qui travaillent hors site, de manière temporaire ou permanente ;</span><span class="sxs-lookup"><span data-stu-id="2b1ae-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="2b1ae-111">Utilisateurs fédérés: employés de votre organisation partenaire.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="2b1ae-112">Utilisateurs d’appareils mobiles ;</span><span class="sxs-lookup"><span data-stu-id="2b1ae-112">Mobile Users.</span></span>
    
- <span data-ttu-id="2b1ae-113">Clients potentiels, partenaires et même utilisateurs anonymes que vous souhaitez inviter à des réunions et à des présentations.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="2b1ae-114">L’accès des utilisateurs externes, qui est fourni par les serveurs de périphérie, permettent à tous ces opérations de se produire.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="2b1ae-115">Vos utilisateurs internes pourront profiter des services suivants hébergés par votre déploiement de Skype entreprise Server:</span><span class="sxs-lookup"><span data-stu-id="2b1ae-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="2b1ae-116">Messagerie instantanée et présence pour les communications : les utilisateurs externes autorisés peuvent participer à des conversations de messagerie instantanée et des conférences.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="2b1ae-117">Ils peuvent obtenir des informations de présence pour les autres utilisateurs (qui obtiennent également leurs informations de présence).</span><span class="sxs-lookup"><span data-stu-id="2b1ae-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="2b1ae-118">Vous ne serez pas en mesure d’effectuer des conférences multipostes si vous utilisez un fournisseur de messagerie instantanée publique, c’est strictement la communication P2P.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="2b1ae-119">Il s’agit strictement de communications P2P, mais les protocoles SIP (Session Initiation Protocol) et XMPP sont tous deux pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="2b1ae-120">Conférences audio/vidéo (A/V): les utilisateurs externes autorisés peuvent participer à vos conférences audio et vidéo Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="2b1ae-121">Conférences Web: vos utilisateurs externes autorisés peuvent participer à vos conférences Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="2b1ae-122">Si vous le souhaitez, vous pouvez également activer la participation à des utilisateurs distants, des utilisateurs fédérés et des utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="2b1ae-123">Les utilisateurs de messagerie instantanée publique ne peuvent pas participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="2b1ae-124">Il existe également des options permettant aux utilisateurs de participer à des applications et au partage du bureau, et même de fonctionner en tant qu’organisateurs ou présentateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="2b1ae-125">L’accès aux appareils mobiles est pris en charge, comme c’est le cas pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="2b1ae-126">Vous pouvez inviter des utilisateurs externes à participer à ces réunions si vous le souhaitez, ou encore des utilisateurs anonymes, si vous êtes disposé à leur donner les autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="2b1ae-p108">Si ce scénario peut convenir à votre organisation, la planification d’un environnement Edge facilitera considérablement son déploiement. Pour en savoir plus, consultez les rubriques ci-après.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="2b1ae-129">Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2b1ae-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2b1ae-130">Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="2b1ae-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="2b1ae-131">Rubriques concernant la planification :</span><span class="sxs-lookup"><span data-stu-id="2b1ae-131">Planning topics:</span></span>

<span data-ttu-id="2b1ae-132">Les articles consacrés à la planification sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2b1ae-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="2b1ae-133">Configuration système requise pour le serveur Edge dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2b1ae-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="2b1ae-134">Conditions préalables d’environnement pour le serveur Edge dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2b1ae-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="2b1ae-135">Scénarios de serveur Edge dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2b1ae-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

