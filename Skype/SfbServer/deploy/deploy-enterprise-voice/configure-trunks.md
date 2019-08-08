---
title: Configuration de Trunks dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé: Découvrez comment configurer un Trunk entre un serveur de médiation et des homologues pour voix entreprise dans Skype entreprise Server.'
ms.openlocfilehash: 714c712816709e8f2211e752f87d20c8d2067c7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233656"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="877d8-103">Configuration de Trunks dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="877d8-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="877d8-104">**Résumé:** Apprenez à configurer une Trunk entre un serveur de médiation et des pairs pour l’entreprise voix dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="877d8-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="877d8-105">Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques vocaux d’entreprise au sein de votre organisation:</span><span class="sxs-lookup"><span data-stu-id="877d8-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="877d8-106">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="877d8-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="877d8-107">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="877d8-107">PSTN gateway</span></span>
    
- <span data-ttu-id="877d8-108">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="877d8-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="877d8-109">Pour plus d’informations, reportez-vous à la rubrique [planification de la connectivité PSTN dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="877d8-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="877d8-110">La fonctionnalité Skype entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="877d8-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="877d8-111">Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="877d8-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="877d8-112">Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).</span><span class="sxs-lookup"><span data-stu-id="877d8-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="877d8-113">Pour attribuer ou supprimer un Trunk dans Skype entreprise Server, vous devez commencer par définir un Trunk dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="877d8-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="877d8-114">Un Trunk est composé de l’Association suivante: nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="877d8-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="877d8-115">Pour configurer plusieurs Trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="877d8-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="877d8-116">Cela fournit une résilience supplémentaire à l’infrastructure voix entreprise, qui est particulièrement utile dans les scénarios d’interopération de PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="877d8-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="877d8-117">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="877d8-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="877d8-118">Pour associer un Trunk à un itinéraire, vous devez définir un nom simple pour le Trunk dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="877d8-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="877d8-119">Ce nom simple sert de nom de Trunk dans le panneau de configuration Skype entreprise Server, où les Trunks peuvent être associés à des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="877d8-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="877d8-120">Le nom simple de Trunk est utilisé comme nom de la passerelle de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="877d8-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="877d8-121">L’administrateur doit sélectionner une Trunk par défaut associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="877d8-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="877d8-122">Dans le générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="877d8-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="877d8-123">Spécifiez la passerelle par défaut du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="877d8-123">Specify the default gateway for the Mediation Server.</span></span> 
  

