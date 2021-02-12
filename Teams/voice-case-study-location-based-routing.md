---
title: Étude de cas Teams voix Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786008"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="23db7-103">Étude de cas Contoso : Location-Based routage</span><span class="sxs-lookup"><span data-stu-id="23db7-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="23db7-104">Location-Based routage des appels (LBR) est une fonctionnalité qui restreint la dérivation contre les frais en fonction d’une stratégie et de l’emplacement physique de l’utilisateur au moment du placement ou de la réception d’un appel.</span><span class="sxs-lookup"><span data-stu-id="23db7-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="23db7-105">Présentation</span><span class="sxs-lookup"><span data-stu-id="23db7-105">Overview</span></span>

<span data-ttu-id="23db7-106">Contoso a deux bureaux dans un pays où il n’est pas illégal d’ignorer le fournisseur de réseau téléphonique commuté (PSTN) afin de diminuer les coûts des appels longue distance.</span><span class="sxs-lookup"><span data-stu-id="23db7-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="23db7-107">Le bureau principal dispose d’une connexion Internet qui est utilisée par le bureau principal et par le deuxième bureau.</span><span class="sxs-lookup"><span data-stu-id="23db7-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="23db7-108">Chaque bureau possède son propre contrôleur de session en bordure (SBC) connecté à un opérateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="23db7-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="23db7-109">Dans ce pays, Contoso avait la cdN configurée pour leur déploiement de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="23db7-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="23db7-110">Pour déterminer comment configurer la CBR pour Teams, Contoso lit le plan Location-Based routage pour le [routage direct.](location-based-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="23db7-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="23db7-111">Contoso a déterminé que Teams et Skype Entreprise suivent les mêmes scénarios pour le moment où un appel peut être passé, le moment où il peut être reçu, lorsqu’un appel PSTN peut être transféré à un utilisateur de Teams et lorsque vous pouvez transférer un autre utilisateur teams vers l’appel PSTN.</span><span class="sxs-lookup"><span data-stu-id="23db7-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="23db7-112">Pour Skype Entreprise, la connexion SIP du contrôleur de session (SBC) à l’opérateur PSTN a été configurée avec la ligne SIP du contrôleur de session.</span><span class="sxs-lookup"><span data-stu-id="23db7-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="23db7-113">Pour ce SBC, Contoso a examiné la liste des [SBC](direct-routing-border-controllers.md) certifiés et déterminé que le déploiement SBC est certifié pour le routage direct, mais n’est pas certifié pour la dérivation média.</span><span class="sxs-lookup"><span data-stu-id="23db7-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="23db7-114">Pour prendre en charge LBR, le routage direct doit être configuré vers le site SBC, il doit y avoir une sortie Internet locale et le SBC doit être configuré pour la dérivation média.</span><span class="sxs-lookup"><span data-stu-id="23db7-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="23db7-115">Sur la base de ces informations, Contoso a décidé des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="23db7-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="23db7-116">Pour retarder l’enablement de Teams LBR jusqu’à ce que le SBC existant soit certifié pour la dérivation média.</span><span class="sxs-lookup"><span data-stu-id="23db7-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="23db7-117">Contoso a décidé d’utiliser le site SBC principal pour l’itinéraire direct vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="23db7-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="23db7-118">Le SBC de site principal sera le SBC proxy pour le site distant.</span><span class="sxs-lookup"><span data-stu-id="23db7-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="23db7-119">Contoso a utilisé un consultant tiers basé en Inde pour participer à la certification de la configuration de la fonction LBR auprès de l’entreprise téléphonique dans le pays.</span><span class="sxs-lookup"><span data-stu-id="23db7-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="23db7-120">Pour aider les utilisateurs extérieurs au bureau à émettre des appels PSTN, le téléphone mobile émis par l’entreprise a été fourni à leurs employés.</span><span class="sxs-lookup"><span data-stu-id="23db7-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="23db7-121">Les diagrammes suivants montrent les déploiements avant et après pour un pays avec des réglementations téléphoniques nécessitant Location-Based routage :</span><span class="sxs-lookup"><span data-stu-id="23db7-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="23db7-122">**Déploiement d’origine**</span><span class="sxs-lookup"><span data-stu-id="23db7-122">**Original deployment**</span></span>

![Diagramme montrant l’état avant](media/voice-case-study-5.png)

<span data-ttu-id="23db7-124">**Déploiement avec routage direct**</span><span class="sxs-lookup"><span data-stu-id="23db7-124">**Deployment with Direct Routing**</span></span>

![Diagramme montrant l’état avant](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="23db7-126">Configuration :</span><span class="sxs-lookup"><span data-stu-id="23db7-126">Configuration:</span></span> 

<span data-ttu-id="23db7-127">Pour configurer les composants réseau dans Teams, Contoso a suivi les instructions de la commande Gérer votre topologie de réseau pour les fonctionnalités [vocales cloud.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="23db7-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="23db7-128">Contoso a suivi les étapes ci-dessous pour configurer Location-Based routage :</span><span class="sxs-lookup"><span data-stu-id="23db7-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="23db7-129">Définir les régions réseau : une région réseau a été définie.</span><span class="sxs-lookup"><span data-stu-id="23db7-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="23db7-130">Définir les sites réseau - Deux sites réseau ont été définis.</span><span class="sxs-lookup"><span data-stu-id="23db7-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="23db7-131">Un site pour chaque emplacement de bureau dans la région.</span><span class="sxs-lookup"><span data-stu-id="23db7-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="23db7-132">Définir des sous-réseaux : chaque étage d’un emplacement de bureau possède son propre sous-réseau pour le réseau câblé et sans fil.</span><span class="sxs-lookup"><span data-stu-id="23db7-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="23db7-133">Cette configuration a permis d’obtenir 20 sous-réseaux pour Contoso.</span><span class="sxs-lookup"><span data-stu-id="23db7-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="23db7-134">Définir des adresses IP fiables : les adresses IP pour le SBC ont été ajoutées à l’adresse IP de confiance.</span><span class="sxs-lookup"><span data-stu-id="23db7-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

