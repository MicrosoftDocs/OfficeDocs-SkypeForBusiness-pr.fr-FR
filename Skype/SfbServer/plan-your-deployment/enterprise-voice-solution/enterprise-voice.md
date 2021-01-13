---
title: Planifier la Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Voix Entreprise base de la planification dans Skype Entreprise Server, notamment les sites, les régions, les liens réseau entre les sites et l’estimation du trafic d’utilisation vocale.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825674"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="8135e-103">Planifier la Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8135e-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="8135e-104">Voix Entreprise base de la planification dans Skype Entreprise Server, notamment les sites, les régions, les liens réseau entre les sites et l’estimation du trafic d’utilisation vocale.</span><span class="sxs-lookup"><span data-stu-id="8135e-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="8135e-105">Le processus de déploiement Voix Entreprise dépend de votre topologie, de votre infrastructure et de la Voix Entreprise que vous souhaitez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="8135e-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="8135e-106">Les procédures requises dépendront des fonctionnalités que vous choisirez, mais vous devrez tenir compte d’autres facteurs pour la planification à un niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="8135e-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="8135e-107">En règle générale, tenez compte du type et du nombre de sites que vous voulez déployer et de leur emplacement géographique, du volume d’appels sur chaque site, des types de liens réseaux qui relient les sites, si vous souhaitez offrir la redondance et le basculement pour la fonctionnalité voix pour chaque site, et enfin si vous voulez utiliser l’équipement PBX existant.</span><span class="sxs-lookup"><span data-stu-id="8135e-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="8135e-108">Il existe certaines considérations, telles que la haute disponibilité, que vous devez prendre en considération lorsque vous planifiez Skype Entreprise Server dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="8135e-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="8135e-109">Ces considérations sont traitées dans les rubriques de cette section, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="8135e-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="8135e-110">Sites et régions</span><span class="sxs-lookup"><span data-stu-id="8135e-110">Sites and regions</span></span>

<span data-ttu-id="8135e-111">Tout d’abord, identifiez les sites de votre topologie où vous allez déployer Voix Entreprise et les régions réseau à laquelle ces sites appartiennent.</span><span class="sxs-lookup"><span data-stu-id="8135e-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="8135e-112">En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site.</span><span class="sxs-lookup"><span data-stu-id="8135e-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="8135e-113">Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant.</span><span class="sxs-lookup"><span data-stu-id="8135e-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="8135e-114">Décidez où les passerelles seront déployées localement, où les Survivable Branch Appliances (SBA) seront déployés et où vous pouvez configurer des trunks SIP (localement ou sur le site central) vers un fournisseur de services de téléphonie Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="8135e-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="8135e-115">Liaisons réseau entre les sites</span><span class="sxs-lookup"><span data-stu-id="8135e-115">Network links between sites</span></span>

<span data-ttu-id="8135e-116">Vous devez également prendre en compte l’utilisation de la bande passante que vous attendez sur les liaisons réseau entre votre site central et ses sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="8135e-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="8135e-117">Si vous avez ou envisagez de déployer des liaisons wan résilientes entre des sites, nous vous recommandons de déployer une passerelle sur chaque site de succursale pour fournir un arrêt SDN (direct inward dial) local pour les utilisateurs de ces sites.</span><span class="sxs-lookup"><span data-stu-id="8135e-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="8135e-118">Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="8135e-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="8135e-119">Si vous ne disposez pas de liaisons réseau wan résistantes, si vous hébergez moins de 1 000 utilisateurs sur votre site de succursale et que vous n’avez pas d’administrateurs Skype Entreprise Server formés en local, nous vous recommandons de déployer un Survivable Branch Appliance sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="8135e-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="8135e-120">Si vous hébergez entre 1 000 et 5 000 utilisateurs sur votre site de succursale, que vous ne disposez pas d’une connexion WAN résiliente et que des administrateurs Skype Entreprise Server formés sont disponibles, nous vous recommandons de déployer un serveur Survivable Branch Server avec une petite passerelle sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="8135e-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="8135e-121">Envisagez aussi d’activer le contournement de média sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="8135e-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="8135e-122">Estimation de l’utilisation et du trafic des voix</span><span class="sxs-lookup"><span data-stu-id="8135e-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="8135e-123">L’outil de planification Microsoft Lync Server 2013 utilise la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.</span><span class="sxs-lookup"><span data-stu-id="8135e-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="8135e-124">Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="8135e-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="8135e-125">Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="8135e-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="8135e-126">Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="8135e-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="8135e-127">Le nombre de ports détermine à son tour le nombre de serveurs de médiation et de passerelles qui seront requis.</span><span class="sxs-lookup"><span data-stu-id="8135e-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="8135e-128">La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports.</span><span class="sxs-lookup"><span data-stu-id="8135e-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="8135e-129">(Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)</span><span class="sxs-lookup"><span data-stu-id="8135e-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="8135e-p106">Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.</span><span class="sxs-lookup"><span data-stu-id="8135e-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="8135e-132">Composants, fonctionnalités et options de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="8135e-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="8135e-133">Consultez les sections suivantes pour plus d’informations sur la planification de Voix Entreprise déploiement.</span><span class="sxs-lookup"><span data-stu-id="8135e-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="8135e-134">Composants requis pour Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8135e-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="8135e-135">Planifier la connectivité PSTN dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8135e-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="8135e-136">Paramètres réseau pour les fonctionnalités Voix Entreprise avancées dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8135e-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="8135e-137">Planifier le contrôle d’admission des appels dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8135e-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="8135e-138">Planifier les services d’urgence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8135e-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="8135e-139">Planifier le contournement de média dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="8135e-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="8135e-140">Planifier des lignes téléphoniques privées avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="8135e-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="8135e-141">Planifier le Location-Based routage des appels dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="8135e-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="8135e-142">Planifier les fonctionnalités de gestion des appels dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="8135e-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="8135e-143">Planifier la résilience Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8135e-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

