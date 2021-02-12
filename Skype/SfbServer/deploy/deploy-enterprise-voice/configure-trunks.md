---
title: Configurer des trunks dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Découvrez comment configurer une trunk entre un serveur de médiation et des homologues pour Voix Entreprise dans Skype Entreprise Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824954"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="6c152-103">Configurer des trunks dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6c152-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="6c152-104">**Résumé :** Découvrez comment configurer une trunk entre un serveur de médiation et des homologues pour Voix Entreprise dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6c152-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="6c152-105">Dans le cadre d’un déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs des homologues suivants afin de fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="6c152-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="6c152-106">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="6c152-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="6c152-107">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="6c152-107">PSTN gateway</span></span>
    
- <span data-ttu-id="6c152-108">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="6c152-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="6c152-109">Pour plus d’informations, voir [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="6c152-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="6c152-110">La fonctionnalité Skype Entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="6c152-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="6c152-111">Ces associations sont réalisées en définissant une trunk, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur SBC (Session Border Controller) ou un SYSTÈME IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="6c152-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="6c152-112">Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (c’est-à-dire, des trunks).</span><span class="sxs-lookup"><span data-stu-id="6c152-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="6c152-113">Pour affecter ou supprimer une trunk dans Skype Entreprise Server, vous devez d’abord définir une trunk dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6c152-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="6c152-114">Une trunk se compose de l’association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="6c152-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="6c152-115">Pour configurer plusieurs trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="6c152-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="6c152-116">Cela offre une résilience supplémentaire à l’infrastructure Voix Entreprise, ce qui est particulièrement utile dans les scénarios interopérationnels PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="6c152-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="6c152-117">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="6c152-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="6c152-118">Pour associer une liaison à un itinéraire, vous définissez un nom simple pour la liaison dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="6c152-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="6c152-119">Ce nom simple est utilisé comme nom de la trunk dans le Panneau de contrôle Skype Entreprise Server, où les liaisons peuvent être associées à des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="6c152-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="6c152-120">Le nom de la simple passerelle est utilisé comme nom de passerelle à partir de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6c152-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="6c152-121">L’administrateur doit sélectionner une trunk par défaut associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="6c152-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="6c152-122">Dans le Générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés.**</span><span class="sxs-lookup"><span data-stu-id="6c152-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="6c152-123">Spécifiez la passerelle par défaut pour le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="6c152-123">Specify the default gateway for the Mediation Server.</span></span> 
  

