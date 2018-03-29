---
title: Scénarios de serveur Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Résumé : Passez en revue ces scénarios pour vous aider à planifier votre topologie de serveur de transport Edge dans Skype Business Server 2015.'
ms.openlocfilehash: 30bce96e1764a608bf7bc8daeec3d918b9e5912c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-scenarios-in-skype-for-business-server-2015"></a><span data-ttu-id="110d5-103">Scénarios de serveur Edge dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="110d5-103">Edge Server scenarios in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="110d5-104">**Résumé :** Passez en revue ces scénarios pour vous aider à planifier votre topologie de serveur de transport Edge dans Skype Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="110d5-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server 2015 .</span></span>
  
<span data-ttu-id="110d5-105">Nous avons certains diagrammes des scénarios pour vous aider à visualiser et à décider sur quel Skype pour la topologie de serveur de transport Edge Server entreprise vous souhaitez implémenter.</span><span class="sxs-lookup"><span data-stu-id="110d5-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="110d5-106">Une fois le scénario idéal sélectionné, vous pouvez effectuer des recherches sur les exigences environnementales devant être prises en compte.</span><span class="sxs-lookup"><span data-stu-id="110d5-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="110d5-107">Nous allons commencer par les informations suivantes, applicables à tous les scénarios.</span><span class="sxs-lookup"><span data-stu-id="110d5-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="110d5-p102">Ces chiffres, affichés à titre d’exemple uniquement (et contenant de ce fait des exemples de données IPv4 et IPv6), ne représentent pas le flux de communication réel, mais plutôt une vue d’ensemble du trafic potentiel. Les diagrammes des ports incluent également les détails des ports pour chaque scénario ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="110d5-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="110d5-110">Les diagrammes indiquent .com pour l’interface externe et .net pour l’interface interne. Il s’agit également d’un exemple, et vos entrées peuvent bien sûr être entièrement différentes lors de la planification finale de votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="110d5-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="110d5-111">Nous ne pas inclure le directeur (qui est un composant facultatif) dans un des diagrammes, mais vous pouvez lire à ce sujet séparément (il est mentionné dans les autres rubriques de planification).</span><span class="sxs-lookup"><span data-stu-id="110d5-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="110d5-112">Comme indiqué ci-dessus, donnée exemple IPv6 dans les diagrammes.</span><span class="sxs-lookup"><span data-stu-id="110d5-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="110d5-113">La plupart de la documentation dans le [Plan de déploiement de serveur de transport Edge dans Skype pour Business Server 2015](edge-server-deployments.md) fera référence à IPv4, mais vous sont certainement pris en charge si vous souhaitez utiliser IPv6.</span><span class="sxs-lookup"><span data-stu-id="110d5-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server 2015](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="110d5-114">Notez que vous aurez besoin des adresses IPv6 dans votre espace d’adresse attribué, et doit utiliser l’adressage interne et externe, comme avec IPv4 IPs.</span><span class="sxs-lookup"><span data-stu-id="110d5-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="110d5-115">Vous pouvez, grâce à Windows, utilisent la fonctionnalité de double pile, qui est une pile réseau distinctes pour IPv4 et IPv6.</span><span class="sxs-lookup"><span data-stu-id="110d5-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="110d5-116">Ce sera, si vous avez besoin, vous permettent d’affecter IPv4 et des adresses IPv6 simultanément.</span><span class="sxs-lookup"><span data-stu-id="110d5-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="110d5-117">Il existe des périphériques NAT qui permettent de NAT64 (IPv6 à IPv4) et NAT66 (IPv6 sur IPv6)), ce qui est valide pour une utilisation avec Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="110d5-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="110d5-118">Si vous utilisez le contrôle d’admission des appels (CAC), vous devez utiliser IPv4 sur l’interface interne pour que celui-ci fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="110d5-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="110d5-119">Unique consolidée Skype pour le serveur de transport Edge Server entreprise privée des adresses IP et NAT</span><span class="sxs-lookup"><span data-stu-id="110d5-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="110d5-p104">Dans ce scénario, il n’existe pas d’option de haute disponibilité. Ainsi, votre matériel sera moins coûteux et votre déploiement sera plus simple. Si la haute disponibilité est requise, reportez-vous aux scénarios de serveurs consolidés mis à l’échelle ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="110d5-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scénario de serveur Edge pour serveur Edge consolidé unique avec avec IP privée à l’aide de NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="110d5-124">Diagramme des ports</span><span class="sxs-lookup"><span data-stu-id="110d5-124">Port diagram</span></span>

<span data-ttu-id="110d5-125">Nous avons également un diagramme des ports pour des serveurs Edge consolidée unique.</span><span class="sxs-lookup"><span data-stu-id="110d5-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé unique](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="110d5-127">Unique consolidée Skype pour le serveur de transport Edge Server Business avec des adresses IP publiques</span><span class="sxs-lookup"><span data-stu-id="110d5-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="110d5-p105">Dans ce scénario, il n’existe pas d’option de haute disponibilité. Ainsi, votre matériel sera moins coûteux et votre déploiement sera plus simple. Si la haute disponibilité est requise, reportez-vous aux scénarios de serveurs consolidés mis à l’échelle ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="110d5-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scénario de serveur Edge pour serveur Edge consolidé unique avec avec IP publique](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="110d5-132">Diagramme des ports</span><span class="sxs-lookup"><span data-stu-id="110d5-132">Port diagram</span></span>

<span data-ttu-id="110d5-133">Nous avons également un diagramme des ports pour des serveurs Edge consolidée unique.</span><span class="sxs-lookup"><span data-stu-id="110d5-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé unique](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="110d5-135">Skype consolidé à l’échelle pour le pool d’entreprise serveur Edge, avec DNS charge équilibrage et privés des adresses IP et NAT</span><span class="sxs-lookup"><span data-stu-id="110d5-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="110d5-136">Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.</span><span class="sxs-lookup"><span data-stu-id="110d5-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance, équilibrage de charge DNS avec IP privée à l’aide de NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="110d5-138">Diagramme des ports</span><span class="sxs-lookup"><span data-stu-id="110d5-138">Port diagram</span></span>

<span data-ttu-id="110d5-139">Nous avons également un diagramme pour les pools de bord consolidés à l’échelle avec l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="110d5-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé avec montée en puissance à l’aide d’équilibrage de charge DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="110d5-141">Skype consolidé à l’échelle pour le pool d’entreprise serveur Edge, avec DNS charge les adresses IP publiques et équilibrage</span><span class="sxs-lookup"><span data-stu-id="110d5-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="110d5-142">Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.</span><span class="sxs-lookup"><span data-stu-id="110d5-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance, équilibrage de charge DNS avec IP publique](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="110d5-144">Diagramme des ports</span><span class="sxs-lookup"><span data-stu-id="110d5-144">Port diagram</span></span>

<span data-ttu-id="110d5-145">Nous avons également un diagramme pour les pools de bord consolidés à l’échelle avec l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="110d5-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé avec montée en puissance à l’aide d’équilibrage de charge DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="110d5-147">Mise à l’échelle de Skype consolidée pour le pool d’entreprise serveur Edge, avec équilibrage de charge matériel</span><span class="sxs-lookup"><span data-stu-id="110d5-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="110d5-148">Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.</span><span class="sxs-lookup"><span data-stu-id="110d5-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance avec HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="110d5-150">Diagramme des ports</span><span class="sxs-lookup"><span data-stu-id="110d5-150">Port diagram</span></span>

<span data-ttu-id="110d5-151">Nous avons également un diagramme pour les pools de bord consolidés à l’échelle avec l’équilibrage de charge matériel</span><span class="sxs-lookup"><span data-stu-id="110d5-151">We also have a diagram for scaled consolidated Edge pools with hardware load balancing</span></span>
  
![Ports et protocoles du réseau de périmètre du serveur Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

