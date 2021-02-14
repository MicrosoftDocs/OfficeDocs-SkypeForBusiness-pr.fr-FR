---
title: Scénarios de serveur Edge dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Résumé : Examinez ces scénarios pour vous aider à planifier votre topologie de serveur Edge dans Skype Entreprise Server.'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813790"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="533f3-103">Scénarios de serveur Edge dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="533f3-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="533f3-104">**Résumé :** Examinez ces scénarios pour vous aider à planifier votre topologie de serveur Edge dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="533f3-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="533f3-105">Nous avons des diagrammes de scénarios pour vous aider à visualiser et à choisir la topologie de serveur Edge Skype Entreprise Server que vous souhaitez implémenter.</span><span class="sxs-lookup"><span data-stu-id="533f3-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="533f3-106">Une fois que vous avez choisi un bon candidat, vous pouvez consulter les exigences environnementales que vous devrez répondre.</span><span class="sxs-lookup"><span data-stu-id="533f3-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="533f3-107">Les exemples suivants s’appliquent à tous les scénarios, c’est pourquoi nous le mentionnons en premier.</span><span class="sxs-lookup"><span data-stu-id="533f3-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="533f3-108">Ces chiffres, qui sont affichés à titre d’exemple uniquement (et qui contiennent des exemples de données IPv4 et IPv6), ne représentent pas le flux de communication réel, mais plutôt une vue d’ensemble de votre trafic possible.</span><span class="sxs-lookup"><span data-stu-id="533f3-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="533f3-109">Les détails des ports sont également visibles dans les diagrammes de port pour chaque scénario ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="533f3-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="533f3-110">Les diagrammes montrent .com pour l’interface externe et .net pour l’interface interne, qui est également un exemple de matériel ; Bien entendu, vos propres entrées peuvent être assez différentes lorsque vous rassemblez votre propre plan Edge final.</span><span class="sxs-lookup"><span data-stu-id="533f3-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="533f3-111">Nous n’incluons pas le directeur (qui est un composant facultatif) dans l’un des diagrammes, mais vous pouvez en savoir plus séparément (il est mentionné dans d’autres rubriques de planification).</span><span class="sxs-lookup"><span data-stu-id="533f3-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="533f3-112">Comme indiqué ci-dessus, il existe des exemples de données IPv6 dans les diagrammes.</span><span class="sxs-lookup"><span data-stu-id="533f3-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="533f3-113">La majeure partie de la documentation de plan pour les [déploiements de](edge-server-deployments.md) serveurs Edge dans Skype Entreprise Server fait référence à IPv4, mais vous êtes certainement pris en charge si vous souhaitez utiliser IPv6.</span><span class="sxs-lookup"><span data-stu-id="533f3-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="533f3-114">Notez que vous aurez besoin d’adresses IPv6 dans votre espace d’adressare affecté et qu’elles devront fonctionner avec l’adressare interne et externe, comme avec les adresses IP IPv4.</span><span class="sxs-lookup"><span data-stu-id="533f3-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="533f3-115">Grâce à Windows, vous pouvez utiliser la fonctionnalité double pile, qui est une pile réseau distincte pour IPv4 et IPv6.</span><span class="sxs-lookup"><span data-stu-id="533f3-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="533f3-116">Cela vous permettra, si nécessaire, d’affecter simultanément des adresses IPv4 et IPv6.</span><span class="sxs-lookup"><span data-stu-id="533f3-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="533f3-117">Il existe des périphériques NAT qui autorisent NAT64 (IPv6 vers IPv4) et NAT66 (IPv6 vers IPv6)), et cela est valide pour une utilisation avec Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="533f3-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="533f3-118">Si vous utilisez le contrôle d’admission des appels (CAC), vous devez utiliser IPv4 sur l’interface interne pour qu’il fonctionne.</span><span class="sxs-lookup"><span data-stu-id="533f3-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="533f3-119">Serveur Edge Skype Entreprise Server consolidé unique avec adresses IP privées et NAT</span><span class="sxs-lookup"><span data-stu-id="533f3-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="533f3-120">Avec ce scénario, il n’existe aucune option pour la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="533f3-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="533f3-121">Cela signifie que vous dépensez moins sur le matériel et que vous avez un déploiement plus simple.</span><span class="sxs-lookup"><span data-stu-id="533f3-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="533f3-122">Si la haute disponibilité est une valeur à prendre en compte, consultez les scénarios consolidés à l’échelle ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="533f3-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scénario edge pour un seul edge consolidé avec une adresse IP privée à l’aide de nat](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="533f3-124">Diagramme de port</span><span class="sxs-lookup"><span data-stu-id="533f3-124">Port diagram</span></span>

<span data-ttu-id="533f3-125">Nous avons également un diagramme pour les ports pour les serveurs Edge consolidés.</span><span class="sxs-lookup"><span data-stu-id="533f3-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Périmètre réseau pour le périmètre consolidé unique du scénario Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="533f3-127">Serveur Edge Skype Entreprise Server consolidé unique avec adresses IP publiques</span><span class="sxs-lookup"><span data-stu-id="533f3-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="533f3-128">Avec ce scénario, il n’existe aucune option pour la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="533f3-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="533f3-129">Cela signifie que vous dépensez moins sur le matériel et que vous avez un déploiement plus simple.</span><span class="sxs-lookup"><span data-stu-id="533f3-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="533f3-130">Si la haute disponibilité est une valeur à prendre en compte, consultez les scénarios consolidés à l’échelle ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="533f3-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scénario edge pour un seul edge consolidé avec une adresse IP publique](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="533f3-132">Diagramme de port</span><span class="sxs-lookup"><span data-stu-id="533f3-132">Port diagram</span></span>

<span data-ttu-id="533f3-133">Nous avons également un diagramme pour les ports pour les serveurs Edge consolidés.</span><span class="sxs-lookup"><span data-stu-id="533f3-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Périmètre réseau pour le périmètre consolidé unique du scénario Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="533f3-135">Pool Edge Skype Entreprise Server consolidé à l’échelle, avec équilibrage de charge DNS, adresses IP privées et NAT</span><span class="sxs-lookup"><span data-stu-id="533f3-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="533f3-136">Avec ce scénario, vous pouvez bénéficier d’une haute disponibilité dans votre déploiement Edge, ce qui vous offre les avantages de l’évolutivité et de la prise en charge duover.</span><span class="sxs-lookup"><span data-stu-id="533f3-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scénario Edge pour edge consolidé à l’échelle, DNS LB avec ip privée à l’aide de nat](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="533f3-138">Diagramme de port</span><span class="sxs-lookup"><span data-stu-id="533f3-138">Port diagram</span></span>

<span data-ttu-id="533f3-139">Nous avons également un diagramme pour les pools Edge consolidés à l’échelle avec équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="533f3-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Périmètre réseau pour le périmètre consolidé mis à l’échelle à l’aide de la base de données DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="533f3-141">Pool Edge Skype Entreprise Server consolidé à l’échelle, avec équilibrage de charge DNS et adresses IP publiques</span><span class="sxs-lookup"><span data-stu-id="533f3-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="533f3-142">Avec ce scénario, vous pouvez bénéficier d’une haute disponibilité dans votre déploiement Edge, ce qui vous offre les avantages de l’évolutivité et de la prise en charge duover.</span><span class="sxs-lookup"><span data-stu-id="533f3-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scénario Edge pour le service Edge consolidé à l’échelle, DNS LB avec ip publique](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="533f3-144">Diagramme de port</span><span class="sxs-lookup"><span data-stu-id="533f3-144">Port diagram</span></span>

<span data-ttu-id="533f3-145">Nous avons également un diagramme pour les pools Edge consolidés à l’échelle avec équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="533f3-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Périmètre réseau pour le périmètre consolidé mis à l’échelle à l’aide de la base de données DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="533f3-147">Pool Edge Skype Entreprise Server consolidé à l’échelle, avec équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="533f3-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="533f3-148">Avec ce scénario, vous pouvez bénéficier d’une haute disponibilité dans votre déploiement Edge, ce qui vous offre les avantages de l’évolutivité et de la prise en charge duover.</span><span class="sxs-lookup"><span data-stu-id="533f3-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scénario edge pour le edge consolidé à l’échelle avec hLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
