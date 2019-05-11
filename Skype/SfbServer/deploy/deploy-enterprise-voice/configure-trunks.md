---
title: Configurer des jonctions Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Découvrez comment configurer une jonction entre un serveur de médiation et des homologues pour Enterprise Voice dans Skype pour Business Server.'
ms.openlocfilehash: 503d9da7b0a2680cd784c3d3c495bed7bfd50dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893027"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="8562b-103">Configurer des jonctions Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8562b-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="8562b-104">**Résumé :** Découvrez comment configurer une jonction entre un serveur de médiation et des homologues pour Enterprise Voice dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="8562b-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="8562b-105">Dans le cadre du déploiement d’Enterprise Voice, vous pouvez configurer une jonction entre un serveur de médiation et un ou plusieurs des homologues suivantes pour fournir un réseau téléphonique commuté (RTC) pour les clients Enterprise Voice et les périphériques de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="8562b-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="8562b-106">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="8562b-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="8562b-107">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="8562b-107">PSTN gateway</span></span>
    
- <span data-ttu-id="8562b-108">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="8562b-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="8562b-109">Pour plus d’informations, voir [planifier la connectivité PSTN dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="8562b-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="8562b-110">Skype pour la fonctionnalité Business Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="8562b-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="8562b-111">Ces associations sont effectuées en définissant une jonction, qui est une association entre un pool de serveurs de médiation et une passerelle réseau téléphonique commuté, contrôleur de Session en périphérie (SBC) ou IP-PBX logique.</span><span class="sxs-lookup"><span data-stu-id="8562b-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="8562b-112">Utilisez le Générateur de topologies pour associer les passerelles avec les serveurs de médiation (c'est-à-dire, jonctions).</span><span class="sxs-lookup"><span data-stu-id="8562b-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="8562b-113">Pour affecter ou supprimer une jonction dans Skype pour Business Server, vous devez d’abord définir une jonction dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8562b-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="8562b-114">Une jonction se compose de l’association suivante : serveur de médiation complet nom de domaine (FQDN), le port d’écoute du serveur de médiation, la nom de domaine complet de la passerelle et le port d’écoute de passerelle.</span><span class="sxs-lookup"><span data-stu-id="8562b-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="8562b-115">Pour configurer plusieurs jonctions, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="8562b-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="8562b-116">Cela offre une résilience supplémentaire à l’infrastructure Enterprise Voice, qui est particulièrement utile dans les scénarios d’interoperational autocommutateur privé (PBX) exchange.</span><span class="sxs-lookup"><span data-stu-id="8562b-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="8562b-117">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="8562b-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="8562b-118">Pour associer une jonction à un itinéraire, vous définissez un nom simple pour la jonction dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8562b-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="8562b-119">Ce nom simple est utilisé comme nom de jonction dans le Skype pour Business Server Control Panel, où les jonctions peuvent être associées à des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="8562b-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="8562b-120">Le nom de la jonction simple est utilisé en tant que le nom de la passerelle à partir de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8562b-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="8562b-121">L’administrateur doit sélectionner une jonction par défaut associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="8562b-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="8562b-122">Dans le Générateur de commandes, cliquez sur le serveur de médiation associé, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8562b-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="8562b-123">Spécifiez la passerelle par défaut pour le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="8562b-123">Specify the default gateway for the Mediation Server.</span></span> 
  

