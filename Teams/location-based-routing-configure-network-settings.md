---
title: Configurer les paramètres réseau - Routage basé sur l’emplacement
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer des régions, des sites et des sous-réseaux réseau pour Location-Based routage direct.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822944"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="e9cda-103">Configurer les paramètres de réseau pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="e9cda-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="e9cda-104">Si vous ne l’avez pas déjà fait, lisez [Plan Location-Based Routage](location-based-routing-plan.md) du routage direct pour examiner les autres étapes à suivre avant de configurer les paramètres réseau pour Location-Based routage.</span><span class="sxs-lookup"><span data-stu-id="e9cda-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="e9cda-105">Cet article décrit comment configurer les paramètres réseau pour le Location-Based routage.</span><span class="sxs-lookup"><span data-stu-id="e9cda-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="e9cda-106">Après avoir déployé Système téléphonique routage direct dans votre organisation, les étapes suivantes sont la création et la création de régions réseau, de sites réseau et de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="e9cda-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="e9cda-107">Définir les régions réseau</span><span class="sxs-lookup"><span data-stu-id="e9cda-107">Define network regions</span></span>

<span data-ttu-id="e9cda-108">Une région réseau contient un ensemble de sites réseau et interconnecte différentes parties d’un réseau sur plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="e9cda-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e9cda-109">Pour savoir comment configurer les régions réseau, voir Gérer votre topologie de réseau pour les fonctionnalités [cloud dans Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e9cda-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="e9cda-110">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="e9cda-110">Define network sites</span></span>

<span data-ttu-id="e9cda-111">Un site réseau représente un emplacement où votre organisation dispose d’un lieu physique, tel qu’un bureau, un ensemble de bâtiments ou un campus.</span><span class="sxs-lookup"><span data-stu-id="e9cda-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="e9cda-112">Vous devez associer chaque site réseau de votre topologie à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="e9cda-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="e9cda-113">Pour savoir comment configurer des sites réseau, voir Gérer votre topologie de réseau pour les fonctionnalités [cloud dans Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e9cda-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="e9cda-114">Une meilleure pratique en matière Location-Based routage des réseaux consiste à créer un site distinct pour chaque emplacement qui dispose d’une connectivité RSTN unique.</span><span class="sxs-lookup"><span data-stu-id="e9cda-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="e9cda-115">Vous pouvez créer un site activé pour le Location-Based routage ou un site non activé pour l'Location-Based routage.</span><span class="sxs-lookup"><span data-stu-id="e9cda-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="e9cda-116">Par exemple, vous pouvez créer un site non activé pour le routage Location-Based afin d’autoriser les utilisateurs activés pour le routage Location-Based à effectuer des appels RSTN lorsqu’ils sont en itinérance sur ce site.</span><span class="sxs-lookup"><span data-stu-id="e9cda-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="e9cda-117">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="e9cda-117">Define network subnets</span></span>

<span data-ttu-id="e9cda-118">Chaque sous-réseau doit être associé à un site réseau spécifique.</span><span class="sxs-lookup"><span data-stu-id="e9cda-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="e9cda-119">Vous pouvez associer plusieurs sous-réseaux au même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="e9cda-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="e9cda-120">Pour savoir comment configurer des sous-réseaux, voir Gérer votre topologie de réseau pour les fonctionnalités cloud dans [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e9cda-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="e9cda-121">Pour Location-Based routage, les sous-réseaux IP à l’emplacement où les points de terminaison Teams peuvent se connecter au réseau doivent être définis et associés à un réseau défini pour appliquer une dérivation toll.</span><span class="sxs-lookup"><span data-stu-id="e9cda-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="e9cda-122">Cette association de sous-réseaux permet Location-Based routage des points de terminaison pour localiser les points de terminaison géographiquement et déterminer si un appel PSTN donné doit être autorisé.</span><span class="sxs-lookup"><span data-stu-id="e9cda-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="e9cda-123">Les sous-réseaux IPv6 et IPv4 sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e9cda-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="e9cda-124">Pour déterminer si un point de terminaison Teams est situé sur un site, l'Location-Based routage vérifie d’abord la recherche d’une adresse IPv6 correspondante.</span><span class="sxs-lookup"><span data-stu-id="e9cda-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="e9cda-125">Si une adresse IPv6 n’est pas présente, Location-Based routage recherche une adresse IPv4.</span><span class="sxs-lookup"><span data-stu-id="e9cda-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="e9cda-126">Définir des adresses IP fiables (sous-réseaux externes)</span><span class="sxs-lookup"><span data-stu-id="e9cda-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="e9cda-127">Les adresses IP fiables sont les adresses IP externes Internet du réseau d’entreprise et sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e9cda-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="e9cda-128">Pour savoir comment configurer des adresses IP fiables, voir Gérer votre topologie de réseau pour les fonctionnalités cloud dans [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e9cda-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="e9cda-129">Si l’adresse IP externe de l’utilisateur correspond à une adresse IP qui se trouve dans la liste d’adresses IP fiables, le routage Location-Based vérifie le sous-réseau interne où se trouve le point de terminaison de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e9cda-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="e9cda-130">Si l’adresse IP externe de l’utilisateur ne correspond à aucune adresse IP définie dans la liste d’adresses IP de confiance, le point de terminaison est considéré comme étant à un emplacement inconnu et tous les appels PSTN entre un utilisateur activé pour le routage Location-Based sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="e9cda-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9cda-131">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="e9cda-131">Next steps</span></span>

<span data-ttu-id="e9cda-132">Allez à [Activer Location-Based routage pour le routage direct.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="e9cda-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9cda-133">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e9cda-133">Related topics</span></span>

- [<span data-ttu-id="e9cda-134">Paramètres réseau pour les fonctionnalités vocales cloud dans Teams</span><span class="sxs-lookup"><span data-stu-id="e9cda-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
