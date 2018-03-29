---
title: Configuration des jonctions dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Apprenez à configurer un tronc d’un serveur de médiation et d’homologues de Voix Entreprise dans Skype pour Business Server 2015.'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="3c00f-103">Configuration des jonctions dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c00f-103">Configure trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3c00f-104">**Résumé :** Apprenez à configurer un tronc d’un serveur de médiation et d’homologues de Voix Entreprise dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3c00f-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3c00f-105">Dans le cadre du déploiement de Voix Entreprise, vous pouvez configurer un tronc d’un serveur de médiation et un ou plusieurs des homologues suivants pour fournir un réseau téléphonique public commuté (RTPC) pour les clients de Voix Entreprise et périphériques de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="3c00f-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="3c00f-106">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="3c00f-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="3c00f-107">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="3c00f-107">PSTN gateway</span></span>
    
- <span data-ttu-id="3c00f-108">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="3c00f-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="3c00f-109">Pour plus de détails, reportez-vous à la section [planifier la connectivité RTPC dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="3c00f-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="3c00f-110">Skype pour les fonctionnalités de Business Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="3c00f-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="3c00f-111">Ces associations sont effectuées en définissant un tronc, qui est une association entre un pool de serveur de médiation et une public commuté (RTPC) passerelle, contrôleur de Session en périphérie (SBC) ou IP-PBX de logique.</span><span class="sxs-lookup"><span data-stu-id="3c00f-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="3c00f-112">Utilisez le Générateur de topologie pour associer des passerelles avec les serveurs de médiation (autrement dit, les trunks).</span><span class="sxs-lookup"><span data-stu-id="3c00f-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="3c00f-113">Pour affecter ou supprimer une ligne dans Skype pour Business Server, vous devez d’abord définir un tronc dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="3c00f-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="3c00f-114">Un tronc se compose de l’association suivante : serveur de médiation qualifié le nom de domaine (FQDN), le port d’écoute de serveur de médiation, la nom de domaine complet de la passerelle et le port d’écoute de passerelle.</span><span class="sxs-lookup"><span data-stu-id="3c00f-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="3c00f-115">Pour configurer plusieurs troncs, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3c00f-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="3c00f-116">Cela fournit des capacités supplémentaires de résistance à l’infrastructure de Voix Entreprise, ce qui est particulièrement utile dans les scénarios d’interoperational private branch exchange (PBX).</span><span class="sxs-lookup"><span data-stu-id="3c00f-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="3c00f-117">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="3c00f-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="3c00f-118">Pour associer un tronc d’un itinéraire, vous définissez un nom simple pour le tronc dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="3c00f-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="3c00f-119">Ce nom simple est utilisé comme nom de tronc dans le Skype pour panneau de commande de serveur Business, où les puits peuvent être associés à des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="3c00f-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="3c00f-120">Le nom de jonction simple est utilisé comme nom de passerelle de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3c00f-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="3c00f-121">L’administrateur doit sélectionner un tronc par défaut associé à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3c00f-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="3c00f-122">Dans le Générateur de topologie, sélectionnez le serveur de médiation associé et puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3c00f-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="3c00f-123">Spécifiez la passerelle par défaut pour le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3c00f-123">Specify the default gateway for the Mediation Server.</span></span> 
  

