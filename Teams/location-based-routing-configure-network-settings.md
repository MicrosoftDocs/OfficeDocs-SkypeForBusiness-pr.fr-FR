---
title: Configurer les paramètres réseau-routage en fonction de l’emplacement
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer des zones, des sites et des sous-réseaux réseau pour le routage direct.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f63ff0191518acf72fd3e4c33abe80b819c3db28
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141277"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="4f498-103">Configurer les paramètres de réseau pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="4f498-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="4f498-104">Si vous ne l’avez pas encore fait, lisez [la section routage en fonction de l’emplacement pour le routage direct](location-based-routing-plan.md) pour réviser les autres étapes que vous devez effectuer avant de configurer les paramètres réseau pour le routage en fonction de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="4f498-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="4f498-105">Cet article décrit comment configurer les paramètres réseau pour le routage sur site.</span><span class="sxs-lookup"><span data-stu-id="4f498-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="4f498-106">Après avoir déployé le routage direct du système téléphonique au sein de votre organisation, les étapes suivantes permettent de créer et de configurer les zones du réseau, les sites réseau et les sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="4f498-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="4f498-107">Définir des régions réseau</span><span class="sxs-lookup"><span data-stu-id="4f498-107">Define network regions</span></span>

<span data-ttu-id="4f498-108">Une région réseau contient une collection de sites du réseau et interconnecte diverses parties d’un réseau à différentes zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="4f498-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4f498-109">Pour plus d’informations sur la configuration des zones du réseau, voir [gérer la topologie de votre réseau pour les fonctionnalités du Cloud dans teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4f498-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="4f498-110">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="4f498-110">Define network sites</span></span>

<span data-ttu-id="4f498-111">Un site réseau correspond à un emplacement où votre organisation a une place physique, par exemple un bureau, un ensemble de bâtiments ou un campus.</span><span class="sxs-lookup"><span data-stu-id="4f498-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="4f498-112">Vous devez associer chaque site réseau dans votre topologie à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="4f498-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="4f498-113">Pour plus d’informations sur la façon de configurer les sites réseau, voir [gérer les fonctionnalités de réseau pour le Cloud dans teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4f498-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="4f498-114">Il est recommandé de créer un site distinct pour chaque emplacement ayant une connectivité PSTN unique.</span><span class="sxs-lookup"><span data-stu-id="4f498-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="4f498-115">Vous pouvez créer un site activé pour le routage de géolocalisation ou un site qui n’est pas activé pour le routage sur site.</span><span class="sxs-lookup"><span data-stu-id="4f498-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="4f498-116">Par exemple, vous souhaiterez peut-être créer un site qui n’est pas activé pour le routage géolocalisation pour permettre aux utilisateurs qui sont activés pour le routage de l’emplacement d’effectuer des appels RTC lors de l’itinérance de ce site.</span><span class="sxs-lookup"><span data-stu-id="4f498-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="4f498-117">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="4f498-117">Define network subnets</span></span>

<span data-ttu-id="4f498-118">Chaque sous-réseau doit être associé à un site réseau spécifique.</span><span class="sxs-lookup"><span data-stu-id="4f498-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="4f498-119">Vous pouvez associer plusieurs sous-réseaux avec le même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="4f498-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="4f498-120">Pour plus d’informations sur la configuration des sous-réseaux du réseau, voir [gérer la topologie de votre réseau pour les fonctionnalités du Cloud dans teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4f498-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="4f498-121">Pour le routage basé sur l’emplacement, les sous-réseaux IP situés à l’emplacement où les points de terminaison d’équipe peuvent se connecter au réseau doivent être définis et associés à un réseau défini pour l’application du contournement du numéro.</span><span class="sxs-lookup"><span data-stu-id="4f498-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="4f498-122">Cette association de sous-réseaux permet le routage de géolocalisation pour localiser les points de terminaison géographiquement pour déterminer si un appel RTC donné doit être autorisé.</span><span class="sxs-lookup"><span data-stu-id="4f498-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="4f498-123">Les sous-réseaux IPv6 et IPv4 sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4f498-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="4f498-124">Lorsque vous déterminez si un point de terminaison d’équipes est situé sur un site, le routage en fonction de l’emplacement vérifie une adresse IPv6 correspondante.</span><span class="sxs-lookup"><span data-stu-id="4f498-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="4f498-125">Si aucune adresse IPv6 n’est présente, le routage sur la base de l’emplacement vérifie la présence d’une adresse IPv4.</span><span class="sxs-lookup"><span data-stu-id="4f498-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="4f498-126">Définir des adresses IP approuvées (sous-réseaux externes)</span><span class="sxs-lookup"><span data-stu-id="4f498-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="4f498-127">Les adresses IP approuvées correspondent aux adresses IP externes Internet du réseau d’entreprise et permettent de déterminer si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4f498-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="4f498-128">Pour plus d’informations sur la configuration des adresses IP approuvées, voir [gérer la topologie de votre réseau pour les fonctionnalités du Cloud dans teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4f498-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="4f498-129">Si l’adresse IP de l’utilisateur correspond à une adresse IP figurant dans la liste d’adresses IP autorisées, le routage sur la base de l’emplacement vérifie le sous-réseau interne sur lequel se trouve le point de terminaison de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f498-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="4f498-130">Si l’adresse IP de l’utilisateur ne correspond pas à une adresse IP définie dans la liste d’adresses IP autorisées, le point de terminaison est considéré comme qui se trouve à un emplacement inconnu et tout appel RTC à ou à partir d’un utilisateur qui est autorisé à utiliser le routage de géolocalisation est bloqué.</span><span class="sxs-lookup"><span data-stu-id="4f498-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4f498-131">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="4f498-131">Next steps</span></span>

<span data-ttu-id="4f498-132">Accédez à [activer le routage en fonction de l’emplacement pour le routage direct](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="4f498-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4f498-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f498-133">Related topics</span></span>

- [<span data-ttu-id="4f498-134">Paramètres réseau pour les fonctionnalités vocales de Cloud dans teams</span><span class="sxs-lookup"><span data-stu-id="4f498-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
