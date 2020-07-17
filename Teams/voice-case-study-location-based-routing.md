---
title: Étude de cas de voix contoso teams
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
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786008"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="50c14-103">Étude de cas contoso : routage sur site</span><span class="sxs-lookup"><span data-stu-id="50c14-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="50c14-104">Le routage de géolocalisation (LBR) est une fonctionnalité qui limite le contournement du péage en fonction de la stratégie et de l’emplacement physique de l’utilisateur au moment du placement ou de la réception d’un appel.</span><span class="sxs-lookup"><span data-stu-id="50c14-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="50c14-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="50c14-105">Overview</span></span>

<span data-ttu-id="50c14-106">Contoso possède deux bureaux dans un pays où il est illégal d’ignorer le fournisseur de réseau téléphonique commuté (PSTN) pour réduire les frais d’appel longue distance.</span><span class="sxs-lookup"><span data-stu-id="50c14-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="50c14-107">Le bureau principal dispose d’une connexion Internet utilisée par le siège social et par le second bureau.</span><span class="sxs-lookup"><span data-stu-id="50c14-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="50c14-108">Chaque bureau possède son propre contrôleur de bordure de session (SBC) connecté à un opérateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="50c14-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="50c14-109">Dans ce pays, contoso avait configuré LBR pour son déploiement Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="50c14-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="50c14-110">Pour savoir comment configurer LBR pour Teams, le routage en fonction de l' [emplacement du plan de lecture pour le routage direct](location-based-routing-plan.md)est défini par contoso.</span><span class="sxs-lookup"><span data-stu-id="50c14-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="50c14-111">Contoso a déterminé que les équipes et Skype entreprise suivent les mêmes scénarios dans le cas où un appel peut être placé, lorsqu’il peut être reçu, qu’un appel RTC peut être transféré à un utilisateur de teams et que vous pouvez transférer un autre utilisateur de teams à l’appel RTC.</span><span class="sxs-lookup"><span data-stu-id="50c14-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="50c14-112">Pour Skype entreprise, LBR a été configuré à l’aide du SIP (session Border Controller) SIP Trunk qui se connecte à l’opérateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="50c14-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="50c14-113">Pour cette SBC, Contoso a examiné la [liste de SBCS certifiés](direct-routing-border-controllers.md) et déterminé que le SBC déployé est certifié pour le routage direct, mais qu’il n’est pas certifié pour la dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="50c14-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="50c14-114">Pour prendre en charge LBR, le routage direct doit être configuré pour l’SBC sur le site, il doit s’agir d’une sortie Internet locale et l’SBC doit être configuré pour la dérivation de média.</span><span class="sxs-lookup"><span data-stu-id="50c14-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="50c14-115">En fonction de ces informations, Contoso a décidé ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="50c14-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="50c14-116">Pour retarder l’activation de teams LBR, jusqu’à ce que le SBC actuel soit certifié pour la dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="50c14-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="50c14-117">Contoso a décidé d’utiliser l’SBC site principal pour le routage direct vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="50c14-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="50c14-118">L’SBC du site principal sera le proxy SBC pour le site distant.</span><span class="sxs-lookup"><span data-stu-id="50c14-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="50c14-119">Contoso a utilisé un consultant tiers basé en Inde pour vous aider à certifier la configuration LBR avec la société de téléphonie dans le pays.</span><span class="sxs-lookup"><span data-stu-id="50c14-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="50c14-120">Pour permettre aux utilisateurs travaillant en dehors du Bureau d’effectuer des appels RTC, le numéro de téléphone mobile émis par la société a été fourni à ses employés.</span><span class="sxs-lookup"><span data-stu-id="50c14-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="50c14-121">Les schémas suivants montrent les déploiements avant et après pour un pays avec des réglementations de téléphonie qui nécessitent un routage sur site :</span><span class="sxs-lookup"><span data-stu-id="50c14-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="50c14-122">**Déploiement d’origine**</span><span class="sxs-lookup"><span data-stu-id="50c14-122">**Original deployment**</span></span>

![Diagramme dont l’État est antérieur](media/voice-case-study-5.png)

<span data-ttu-id="50c14-124">**Déploiement avec le routage direct**</span><span class="sxs-lookup"><span data-stu-id="50c14-124">**Deployment with Direct Routing**</span></span>

![Diagramme dont l’État est antérieur](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="50c14-126">Configurations</span><span class="sxs-lookup"><span data-stu-id="50c14-126">Configuration:</span></span> 

<span data-ttu-id="50c14-127">Pour configurer les composants réseau dans Teams, Contoso a suivi les instructions dans [gérer la topologie de votre réseau pour les fonctionnalités vocales de Cloud](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="50c14-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="50c14-128">Contoso a effectué les étapes ci-dessous pour configurer le routage sur site :</span><span class="sxs-lookup"><span data-stu-id="50c14-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="50c14-129">Définissez les zones du réseau : une région du réseau a été définie.</span><span class="sxs-lookup"><span data-stu-id="50c14-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="50c14-130">Définir les sites réseau-deux sites réseau ont été définis.</span><span class="sxs-lookup"><span data-stu-id="50c14-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="50c14-131">Un site pour chaque emplacement du bureau dans la région.</span><span class="sxs-lookup"><span data-stu-id="50c14-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="50c14-132">Définir des sous-réseaux réseau : chaque étage au sein d’un bureau possède son propre sous-réseau pour le réseau filaire et sans fil.</span><span class="sxs-lookup"><span data-stu-id="50c14-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="50c14-133">Cette configuration a donné lieu à 20 sous-réseaux pour contoso.</span><span class="sxs-lookup"><span data-stu-id="50c14-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="50c14-134">Définir des adresses IP approuvées-les adresses IP externes pour les SBC ont été ajoutées à l’adresse IP de confiance.</span><span class="sxs-lookup"><span data-stu-id="50c14-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

