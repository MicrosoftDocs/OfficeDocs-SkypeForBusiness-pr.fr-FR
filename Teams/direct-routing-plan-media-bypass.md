---
title: Planifier le contournement de média avec un routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment planifier la dérivation média avec Système téléphonique routage direct, ce qui vous permet de raccourcir le chemin d’accès au trafic multimédia et d’améliorer les performances.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c65cdb4ede98fbd34c39eb941aed2c582c15b37b
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264954"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="6971a-103">Planifier le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="6971a-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="6971a-104">À propos de la dérivation média avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="6971a-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="6971a-105">La dérivation média vous permet de raccourcir le chemin d’accès au trafic de médias et de réduire le nombre de sauts en transit pour de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="6971a-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="6971a-106">Avec la dérivation média, le média est conservé entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via Téléphone Microsoft système informatique.</span><span class="sxs-lookup"><span data-stu-id="6971a-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="6971a-107">Pour configurer la dérivation média, le SBC et le client doivent se trouver dans le même emplacement ou réseau.</span><span class="sxs-lookup"><span data-stu-id="6971a-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="6971a-108">Vous pouvez contrôler la dérivation média pour chaque SBC à l’aide de la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** définie sur true ou false.</span><span class="sxs-lookup"><span data-stu-id="6971a-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="6971a-109">Si vous activez la dérivation média, cela ne signifie pas que tout le trafic de médias restera au sein du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6971a-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="6971a-110">Cet article décrit le flux d’appels dans différents scénarios.</span><span class="sxs-lookup"><span data-stu-id="6971a-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="6971a-111">Les diagrammes ci-dessous illustrent la différence de flux d’appels avec et sans contournement des médias.</span><span class="sxs-lookup"><span data-stu-id="6971a-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="6971a-112">Sans contournement média, lorsqu’un client effectue ou reçoit un appel, le trafic de signalisation et le flux de médias entre le SBC, le système Téléphone Microsoft et le client Teams, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="6971a-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6971a-113">![Affiche le trafic de signalisation et le flux multimédia sans contournement média](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="6971a-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="6971a-114">Supposons toutefois qu’un utilisateur se trouve dans le même bâtiment ou le même réseau que le SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="6971a-115">Par exemple, supposons qu’un utilisateur se trouve dans un bâtiment dans Le Monde appelle un utilisateur PSTN :</span><span class="sxs-lookup"><span data-stu-id="6971a-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="6971a-116">**Sans contournement** des médias, les médias circulent via Amsterdam ou Dublin (où les centres de données Microsoft sont déployés), puis reviennent au SBC dans Le Monde.</span><span class="sxs-lookup"><span data-stu-id="6971a-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="6971a-117">Le centre de données en Europe est sélectionné, car le SBC est en Europe et Microsoft utilise le centre de données le plus proche du SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="6971a-118">Bien que cette approche n’affecte pas la qualité des appels en raison de l’optimisation du flux de trafic au sein des réseaux Microsoft dans la plupart des régions, le trafic présente une boucle inutile.</span><span class="sxs-lookup"><span data-stu-id="6971a-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="6971a-119">**Avec la dérivation** média, le média est conservé directement entre l Teams un utilisateur et le SBC, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="6971a-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="6971a-120">![Affiche le trafic de signalisation et le flux multimédia avec contournement des médias](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="6971a-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="6971a-121">La dérivation média s’appuie sur des protocoles appelés ice (Interactive Connectivity Connectivity Connectivity Connectivité) sur le client Teams et ICE sur le SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="6971a-122">Ces protocoles permettent au routage direct d’utiliser le chemin de médias le plus direct pour une qualité optimale.</span><span class="sxs-lookup"><span data-stu-id="6971a-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="6971a-123">ICE et ICE Lite sont des normes WebRTC.</span><span class="sxs-lookup"><span data-stu-id="6971a-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="6971a-124">Pour plus d’informations sur ces protocoles, voir RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="6971a-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="6971a-125">Planification du flux d’appels et du pare-feu</span><span class="sxs-lookup"><span data-stu-id="6971a-125">Call flow and firewall planning</span></span>

<span data-ttu-id="6971a-126">La planification du flux d’appels et du pare-feu varie selon que l’utilisateur a un accès direct à l’adresse IP publique du SBC et si l’utilisateur est à l’intérieur ou à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="6971a-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6971a-127">Flux d’appels si l’utilisateur dispose d’un accès direct à l’adresse IP publique du SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="6971a-128">Si l’utilisateur dispose d’un accès direct à l’adresse IP publique du SBC, le flux d’appels est le suivant :</span><span class="sxs-lookup"><span data-stu-id="6971a-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="6971a-129">Pour la dérivation média, Teams client doit avoir accès à l’adresse IP publique du SBC, même à partir d’un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="6971a-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="6971a-130">Si le média direct n’est pas souhaité, il peut être transmis via un relais de transport.</span><span class="sxs-lookup"><span data-stu-id="6971a-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="6971a-131">Il s’agit de la solution recommandée lorsqu’un utilisateur se trouve dans le même bâtiment et/ou réseau que le SBC (supprimer les composants Microsoft Cloud du chemin de médias).</span><span class="sxs-lookup"><span data-stu-id="6971a-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="6971a-132">Les signaux circulent toujours via le cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6971a-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="6971a-133">Le diagramme suivant montre le flux d’appels lorsque la dérivation média est activée, que le client est interne et que le client peut accéder à l’adresse IP publique du support SBC :</span><span class="sxs-lookup"><span data-stu-id="6971a-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="6971a-134">Les flèches et les valeurs numériques des chemins d’accès sont conformes aux [flux Microsoft Teams’appel.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="6971a-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="6971a-135">Le trafic de signalisation SIP prend toujours les chemins 4 et 4' (selon le sens de trafic).</span><span class="sxs-lookup"><span data-stu-id="6971a-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6971a-136">Les médias restent locaux et prennent le chemin 5b.</span><span class="sxs-lookup"><span data-stu-id="6971a-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6971a-137">![Présente le flux d’appels avec contournement multimédia activé, le client est interne](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="6971a-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6971a-138">Flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="6971a-139">Le tableau suivant décrit le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6971a-140">Par exemple, supposons que l’utilisateur soit externe et que l’administrateur client a décidé de ne pas ouvrir l’adresse IP publique du SBC à tous les utilisateurs d’Internet, mais uniquement au cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6971a-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="6971a-141">Les composants internes du trafic peuvent être acheminés par le biais Teams relais de transport.</span><span class="sxs-lookup"><span data-stu-id="6971a-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="6971a-142">Vous devez tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6971a-142">Consider the following:</span></span>

- <span data-ttu-id="6971a-143">Teams Les relais de transport sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="6971a-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="6971a-144">Pour la dérivation média, Microsoft utilise une version de relais de transport qui nécessite l’ouverture de ports 50 000 à 59 999 entre les relais de transport Teams et le SBC (nous prévoyons de passer à la version nécessitant uniquement 3478 et 3479 ports).</span><span class="sxs-lookup"><span data-stu-id="6971a-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="6971a-145">Le diagramme suivant illustre le flux d’appels lorsque la dérivation média est activée, que le client est externe et que le client ne peut pas accéder à l’adresse IP publique du contrôleur de session en bordure (le média est relayé par Teams Relais de transport).</span><span class="sxs-lookup"><span data-stu-id="6971a-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="6971a-146">Les flèches et les valeurs numériques des chemins d’accès sont conformes aux [flux Microsoft Teams’appel.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="6971a-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="6971a-147">Le média est relayé par les chemins d’accès 3, 3', 4 et 4'</span><span class="sxs-lookup"><span data-stu-id="6971a-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6971a-148">![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="6971a-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="6971a-149">Flux d’appels si un utilisateur se trouve en dehors du réseau et a accès à l’adresse IP publique du SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="6971a-150">Cette configuration n’est pas recommandée, car elle ne prend pas en Teams relais de transport.</span><span class="sxs-lookup"><span data-stu-id="6971a-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="6971a-151">Au lieu de cela, vous devez tenir compte du scénario précédent où l’utilisateur n’a pas accès à l’adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6971a-152">Le diagramme suivant montre le flux d’appels lorsque la dérivation média est activée, que le client est externe et que le client peut atteindre l’adresse IP publique du support SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="6971a-153">Les flèches et les valeurs numériques des chemins d’accès sont conformes à l’article [Microsoft Teams flux d’appels.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="6971a-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="6971a-154">Le trafic de signalisation SIP prend toujours les chemins 3 et 3' (selon le sens du trafic).</span><span class="sxs-lookup"><span data-stu-id="6971a-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6971a-155">Flux multimédias en utilisant le chemin d’accès 2.</span><span class="sxs-lookup"><span data-stu-id="6971a-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6971a-156">![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="6971a-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="6971a-157">Utilisation de processeurs multimédias et de relais de transport</span><span class="sxs-lookup"><span data-stu-id="6971a-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="6971a-158">Microsoft Cloud peut utiliser deux composants dans le chemin d’accès du trafic de médias : Processeurs de média et Relais de transport.</span><span class="sxs-lookup"><span data-stu-id="6971a-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="6971a-159">Le processeur de média est un composant public qui gère les éléments multimédias dans les cas qui ne contournent pas et gère les médias pour les applications vocales.</span><span class="sxs-lookup"><span data-stu-id="6971a-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="6971a-160">Les processeurs multimédias sont toujours dans le chemin pour les appels sans contournement de l’utilisateur final, mais jamais dans le chemin pour les appels contournements.</span><span class="sxs-lookup"><span data-stu-id="6971a-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="6971a-161">Les processeurs multimédias sont toujours dans le chemin d’accès de toutes les applications vocales, telles que le parc des appels, les Standard automatique de l’organisation et les files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="6971a-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="6971a-162">Le relais de transport est utilisé pour se connecter au service de transport le plus proche pour envoyer le trafic en temps réel.</span><span class="sxs-lookup"><span data-stu-id="6971a-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="6971a-163">Les relais de transport peuvent ou non se trouver dans le chemin d’accès des appels contournements (provenant ou destinés à des utilisateurs finaux), selon l’endroit où se trouve l’utilisateur et la manière dont le réseau est configuré.</span><span class="sxs-lookup"><span data-stu-id="6971a-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="6971a-164">Le diagramme suivant montre deux flux d’appels : un avec la dérivation média activée et la seconde avec la dérivation média désactivée.</span><span class="sxs-lookup"><span data-stu-id="6971a-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="6971a-165">Le diagramme illustre uniquement le trafic provenant d’utilisateurs - ou destinés à des utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="6971a-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="6971a-166">Le contrôleur de média est un microservice dans Azure qui attribue des processeurs multimédias et crée des offres SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="6971a-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="6971a-167">Le proxy SIP est un composant qui traduit le signalisation HTTP REST utilisé dans Teams en SIP.</span><span class="sxs-lookup"><span data-stu-id="6971a-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6971a-168">![Présente les flux d’appels avec la dérivation média activée et désactivée](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="6971a-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="6971a-169">Le tableau ci-dessous résume la différence entre les processeurs de média et les relais de transport.</span><span class="sxs-lookup"><span data-stu-id="6971a-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="6971a-170">Processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="6971a-170">Media Processors</span></span> | <span data-ttu-id="6971a-171">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="6971a-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="6971a-172">Chemin de médias pour les appels non contournements pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="6971a-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="6971a-173">Toujours</span><span class="sxs-lookup"><span data-stu-id="6971a-173">Always</span></span> | <span data-ttu-id="6971a-174">Si le client ne parviennent pas à joindre le processeur de média directement</span><span class="sxs-lookup"><span data-stu-id="6971a-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="6971a-175">Dans le chemin de médias pour les appels contournements pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="6971a-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="6971a-176">Jamais</span><span class="sxs-lookup"><span data-stu-id="6971a-176">Never</span></span> | <span data-ttu-id="6971a-177">Si le client ne peut pas accéder au SBC sur l’adresse IP publique</span><span class="sxs-lookup"><span data-stu-id="6971a-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="6971a-178">Dans le chemin multimédia des applications vocales</span><span class="sxs-lookup"><span data-stu-id="6971a-178">In media path for voice applications</span></span> | <span data-ttu-id="6971a-179">Toujours</span><span class="sxs-lookup"><span data-stu-id="6971a-179">Always</span></span> | <span data-ttu-id="6971a-180">Jamais</span><span class="sxs-lookup"><span data-stu-id="6971a-180">Never</span></span> | 
<span data-ttu-id="6971a-181">Can do transcoding (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="6971a-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="6971a-182">Oui</span><span class="sxs-lookup"><span data-stu-id="6971a-182">Yes</span></span> | <span data-ttu-id="6971a-183">Non, seul l’audio est relayé entre les points de terminaison</span><span class="sxs-lookup"><span data-stu-id="6971a-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="6971a-184">Nombre d’instances dans le monde et emplacement</span><span class="sxs-lookup"><span data-stu-id="6971a-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="6971a-185">10 total : 2 dans la région Est et Ouest des États-Unis ; 2 à Amsterdam et Dublin ; 2 à Hong Kong et Singapour ; 2 au Japon ; 2 en Australie de l’Est et du Sud-est</span><span class="sxs-lookup"><span data-stu-id="6971a-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="6971a-186">Multiple</span><span class="sxs-lookup"><span data-stu-id="6971a-186">Multiple</span></span>

<span data-ttu-id="6971a-187">Les plages d’adresses IP sont les plus diverses :</span><span class="sxs-lookup"><span data-stu-id="6971a-187">The IP ranges are:</span></span>
- <span data-ttu-id="6971a-188">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6971a-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="6971a-189">52.120.0.0/14 (adresses IP de 52.120.0.1 à 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="6971a-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="6971a-190">\* Explication de la transcodage :</span><span class="sxs-lookup"><span data-stu-id="6971a-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="6971a-191">Le processeur multimédia est B2BUA, ce qui signifie qu’il peut changer un codec (par exemple, SILK d’un client Teams en MP et G.711 entre MP et SBC).</span><span class="sxs-lookup"><span data-stu-id="6971a-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="6971a-192">Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n’est jamais modifié entre le client et le SBC, même si le trafic est acheminé par relais.</span><span class="sxs-lookup"><span data-stu-id="6971a-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="6971a-193">Utilisation de processeurs Teams média si la ligne est configurée pour la dérivation média</span><span class="sxs-lookup"><span data-stu-id="6971a-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="6971a-194">Teams Les processeurs multimédias sont toujours insérés dans le chemin de médias dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="6971a-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="6971a-195">L’appel est recalé de 1:1 à un appel de groupe</span><span class="sxs-lookup"><span data-stu-id="6971a-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="6971a-196">L’appel va être fédéré Teams utilisateur</span><span class="sxs-lookup"><span data-stu-id="6971a-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="6971a-197">L’appel est transféré ou transféré à un Skype Entreprise utilisateur</span><span class="sxs-lookup"><span data-stu-id="6971a-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="6971a-198">Assurez-vous que votre SBC a accès aux plages Processeurs de média et Relais de transport, comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6971a-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="6971a-199">Signalisation SIP : FQDN</span><span class="sxs-lookup"><span data-stu-id="6971a-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="6971a-200">Pour le signalisation SIP, les exigences de nom de passe (FQDN) et de pare-feu sont identiques à ceux des cas non contourné.</span><span class="sxs-lookup"><span data-stu-id="6971a-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="6971a-201">Un routage direct est proposé dans les environnements Microsoft 365 ou Office 365 suivants :</span><span class="sxs-lookup"><span data-stu-id="6971a-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="6971a-202">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="6971a-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6971a-203">Office 365 Cloud de la communauté du secteur public</span><span class="sxs-lookup"><span data-stu-id="6971a-203">Office 365 GCC</span></span>
- <span data-ttu-id="6971a-204">Office 365 Cloud de la communauté du secteur public Haute</span><span class="sxs-lookup"><span data-stu-id="6971a-204">Office 365 GCC High</span></span>
- <span data-ttu-id="6971a-205">Office 365 DoD En savoir plus [sur les environnements Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) administration publique des États-Unis, tels que Cloud de la communauté du secteur public, Cloud de la communauté du secteur public Élevé et DoD.</span><span class="sxs-lookup"><span data-stu-id="6971a-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6971a-206">Microsoft 365, Office 365 et Office 365 Cloud de la communauté du secteur public de travail</span><span class="sxs-lookup"><span data-stu-id="6971a-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="6971a-207">Les points de connexion pour le routage direct sont les trois FQDN suivants :</span><span class="sxs-lookup"><span data-stu-id="6971a-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="6971a-208">**sip.pstnhub.microsoft.com** , vous devez d’abord essayer le FQDN global.</span><span class="sxs-lookup"><span data-stu-id="6971a-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="6971a-209">Lorsque le SBC envoie une demande de résolution de ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de données Azure principal affecté au SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="6971a-210">L’affectation est basée sur les mesures de performance des centres de données et la proximité géographique par rapport au SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="6971a-211">L’adresse IP renvoyée correspond au FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="6971a-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="6971a-212">**sip2.pstnhub.microsoft.com** (FQDN secondaire) géographiquement à la région de deuxième priorité.</span><span class="sxs-lookup"><span data-stu-id="6971a-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="6971a-213">**sip3.pstnhub.microsoft.com** – FQDN de l’situation géographique de la troisième région.</span><span class="sxs-lookup"><span data-stu-id="6971a-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="6971a-214">Vous devez placer ces trois FQDN pour :</span><span class="sxs-lookup"><span data-stu-id="6971a-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="6971a-215">Offrez une expérience optimale (moins chargé et le plus proche du centre de données SBC attribué en interrogeant le premier FQDN).</span><span class="sxs-lookup"><span data-stu-id="6971a-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="6971a-216">Offrez un échec lorsqu’une connexion à partir d’un SBC est établie vers un centre de données qui rencontre un problème temporaire.</span><span class="sxs-lookup"><span data-stu-id="6971a-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="6971a-217">Pour plus d’informations, voir le mécanisme deover ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6971a-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="6971a-218">Les noms de **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** et sip3.pstnhub.microsoft.com sont  résolus avec l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="6971a-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="6971a-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="6971a-219">52.114.148.0</span></span>
- <span data-ttu-id="6971a-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="6971a-220">52.114.132.46</span></span> 
- <span data-ttu-id="6971a-221">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="6971a-221">52.114.75.24</span></span> 
- <span data-ttu-id="6971a-222">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="6971a-222">52.114.76.76</span></span> 
- <span data-ttu-id="6971a-223">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="6971a-223">52.114.7.24</span></span> 
- <span data-ttu-id="6971a-224">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="6971a-224">52.114.14.70</span></span>
- <span data-ttu-id="6971a-225">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="6971a-225">52.114.16.74</span></span>
- <span data-ttu-id="6971a-226">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="6971a-226">52.114.20.29</span></span>
- <span data-ttu-id="6971a-227">52.114.36.156</span><span class="sxs-lookup"><span data-stu-id="6971a-227">52.114.36.156</span></span> 
- <span data-ttu-id="6971a-228">52.114.32.169</span><span class="sxs-lookup"><span data-stu-id="6971a-228">52.114.32.169</span></span>

<span data-ttu-id="6971a-229">Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.</span><span class="sxs-lookup"><span data-stu-id="6971a-229">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="6971a-230">Si votre pare-feu prend en charge les noms DNS, le nom de domaine sip-all.pstnhub.microsoft.com **est** résolu pour toutes ces adresses IP.</span><span class="sxs-lookup"><span data-stu-id="6971a-230">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6971a-231">Office 365 Cloud de la communauté du secteur public Environnement DoD</span><span class="sxs-lookup"><span data-stu-id="6971a-231">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="6971a-232">Le point de connexion pour le routage direct est le FQDN suivant :</span><span class="sxs-lookup"><span data-stu-id="6971a-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6971a-233">**sip.pstnhub.dod.teams.microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="6971a-233">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6971a-234">Étant donné que l’Office 365 DoD existe uniquement dans les centres de données américains, il n’existe aucun nom de fQDN secondaire et secondaire.</span><span class="sxs-lookup"><span data-stu-id="6971a-234">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6971a-235">Les noms de noms de sip.pstnhub.dod.teams.microsoft.us seront résolus à l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="6971a-235">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6971a-236">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="6971a-236">52.127.64.33</span></span>
- <span data-ttu-id="6971a-237">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="6971a-237">52.127.68.34</span></span>

<span data-ttu-id="6971a-238">Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.</span><span class="sxs-lookup"><span data-stu-id="6971a-238">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6971a-239">Si votre pare-feu prend en charge les noms DNS, le nom de domaine sip.pstnhub.dod.teams.microsoft.us est résolu pour toutes ces adresses IP.</span><span class="sxs-lookup"><span data-stu-id="6971a-239">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6971a-240">Office 365 Cloud de la communauté du secteur public environnement élevé</span><span class="sxs-lookup"><span data-stu-id="6971a-240">Office 365 GCC High environment</span></span>

<span data-ttu-id="6971a-241">Le point de connexion pour le routage direct est le FQDN suivant :</span><span class="sxs-lookup"><span data-stu-id="6971a-241">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6971a-242">**sip.pstnhub.gov.teams.microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="6971a-242">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6971a-243">Étant donné que l Cloud de la communauté du secteur public de haute ligne existe uniquement dans les centres de données américains, il n’existe aucun nom de fQDN secondaire et secondaire.</span><span class="sxs-lookup"><span data-stu-id="6971a-243">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6971a-244">Les noms de noms de sip.pstnhub.gov.teams.microsoft.us seront résolus à l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="6971a-244">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6971a-245">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="6971a-245">52.127.88.59</span></span>
- <span data-ttu-id="6971a-246">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="6971a-246">52.127.92.64</span></span>

<span data-ttu-id="6971a-247">Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.</span><span class="sxs-lookup"><span data-stu-id="6971a-247">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6971a-248">Si votre pare-feu prend en charge les noms DNS, le nom de domaine sip.pstnhub.gov.teams.microsoft.us est résolu pour toutes ces adresses IP.</span><span class="sxs-lookup"><span data-stu-id="6971a-248">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="6971a-249">Signalisation SIP : ports</span><span class="sxs-lookup"><span data-stu-id="6971a-249">SIP Signaling: Ports</span></span>

<span data-ttu-id="6971a-250">Les exigences de port sont identiques pour tous Office 365 d’environnements de routage direct :</span><span class="sxs-lookup"><span data-stu-id="6971a-250">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="6971a-251">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="6971a-251">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6971a-252">Office 365 Cloud de la communauté du secteur public</span><span class="sxs-lookup"><span data-stu-id="6971a-252">Office 365 GCC</span></span>
- <span data-ttu-id="6971a-253">Office 365 Cloud de la communauté du secteur public Haute</span><span class="sxs-lookup"><span data-stu-id="6971a-253">Office 365 GCC High</span></span>
- <span data-ttu-id="6971a-254">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="6971a-254">Office 365 DoD</span></span>

<span data-ttu-id="6971a-255">Vous devez utiliser les ports suivants :</span><span class="sxs-lookup"><span data-stu-id="6971a-255">You must use the following ports:</span></span>

| <span data-ttu-id="6971a-256">Trafic</span><span class="sxs-lookup"><span data-stu-id="6971a-256">Traffic</span></span> | <span data-ttu-id="6971a-257">De</span><span class="sxs-lookup"><span data-stu-id="6971a-257">From</span></span> | <span data-ttu-id="6971a-258">À</span><span class="sxs-lookup"><span data-stu-id="6971a-258">To</span></span> | <span data-ttu-id="6971a-259">Port source</span><span class="sxs-lookup"><span data-stu-id="6971a-259">Source port</span></span> | <span data-ttu-id="6971a-260">Port de destination</span><span class="sxs-lookup"><span data-stu-id="6971a-260">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6971a-261">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6971a-261">SIP/TLS</span></span>| <span data-ttu-id="6971a-262">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="6971a-262">SIP Proxy</span></span> | <span data-ttu-id="6971a-263">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-263">SBC</span></span> | <span data-ttu-id="6971a-264">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="6971a-264">1024 - 65535</span></span> | <span data-ttu-id="6971a-265">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-265">Defined on the SBC</span></span> |
| <span data-ttu-id="6971a-266">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6971a-266">SIP/TLS</span></span> | <span data-ttu-id="6971a-267">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-267">SBC</span></span> | <span data-ttu-id="6971a-268">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="6971a-268">SIP Proxy</span></span> | <span data-ttu-id="6971a-269">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-269">Defined on the SBC</span></span> | <span data-ttu-id="6971a-270">5061</span><span class="sxs-lookup"><span data-stu-id="6971a-270">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="6971a-271">Trafic de médias : ip et plages de ports</span><span class="sxs-lookup"><span data-stu-id="6971a-271">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="6971a-272">Le trafic de médias circule entre le client SBC et le client Teams si une connectivité directe est disponible ou via des relais de transport Teams si le client ne peut pas accéder au SBC à l’aide de l’adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="6971a-272">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="6971a-273">Exigences pour le trafic de médias directs (entre le client Teams et le SBC)</span><span class="sxs-lookup"><span data-stu-id="6971a-273">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="6971a-274">Le client doit avoir accès aux ports spécifiés (voir tableau) sur l’adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-274">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="6971a-275">Si le client se trouve dans un réseau interne, le média passe à l’adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-275">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="6971a-276">Vous pouvez configurer l’épinglage de cheveux sur votre appareil NAT afin que le trafic ne quitte jamais l’équipement réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6971a-276">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="6971a-277">Trafic</span><span class="sxs-lookup"><span data-stu-id="6971a-277">Traffic</span></span> | <span data-ttu-id="6971a-278">De</span><span class="sxs-lookup"><span data-stu-id="6971a-278">From</span></span> | <span data-ttu-id="6971a-279">À</span><span class="sxs-lookup"><span data-stu-id="6971a-279">To</span></span> | <span data-ttu-id="6971a-280">Port source</span><span class="sxs-lookup"><span data-stu-id="6971a-280">Source port</span></span> | <span data-ttu-id="6971a-281">Port de destination</span><span class="sxs-lookup"><span data-stu-id="6971a-281">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6971a-282">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6971a-282">UDP/SRTP</span></span> | <span data-ttu-id="6971a-283">Client</span><span class="sxs-lookup"><span data-stu-id="6971a-283">Client</span></span> | <span data-ttu-id="6971a-284">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-284">SBC</span></span> | <span data-ttu-id="6971a-285">3478-3481 et 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="6971a-285">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="6971a-286">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-286">Defined on the SBC</span></span> |
| <span data-ttu-id="6971a-287">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6971a-287">UDP/SRTP</span></span> | <span data-ttu-id="6971a-288">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-288">SBC</span></span> | <span data-ttu-id="6971a-289">Client</span><span class="sxs-lookup"><span data-stu-id="6971a-289">Client</span></span> | <span data-ttu-id="6971a-290">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-290">Defined on the SBC</span></span> | <span data-ttu-id="6971a-291">3478-3481 et 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="6971a-291">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="6971a-292">Si votre périphérique réseau traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et le SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-292">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="6971a-293">Conditions requises pour l’utilisation de relais de transport</span><span class="sxs-lookup"><span data-stu-id="6971a-293">Requirements for using Transport Relays</span></span>

<span data-ttu-id="6971a-294">Les relais de transport sont dans la même plage que les processeurs multimédias (pour les cas sans contournement) :</span><span class="sxs-lookup"><span data-stu-id="6971a-294">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6971a-295">Microsoft 365, Office 365 et Office 365 Cloud de la communauté du secteur public de travail</span><span class="sxs-lookup"><span data-stu-id="6971a-295">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="6971a-296">52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6971a-296">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6971a-297">Office 365 Cloud de la communauté du secteur public Environnement DoD</span><span class="sxs-lookup"><span data-stu-id="6971a-297">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6971a-298">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6971a-298">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6971a-299">Office 365 Cloud de la communauté du secteur public environnement élevé</span><span class="sxs-lookup"><span data-stu-id="6971a-299">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6971a-300">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6971a-300">52.127.88.0/21</span></span>


<span data-ttu-id="6971a-301">La plage de ports des Teams relais de transport (applicable à tous les environnements) est indiquée dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="6971a-301">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="6971a-302">Trafic</span><span class="sxs-lookup"><span data-stu-id="6971a-302">Traffic</span></span> | <span data-ttu-id="6971a-303">De</span><span class="sxs-lookup"><span data-stu-id="6971a-303">From</span></span> | <span data-ttu-id="6971a-304">À</span><span class="sxs-lookup"><span data-stu-id="6971a-304">To</span></span> | <span data-ttu-id="6971a-305">Port source</span><span class="sxs-lookup"><span data-stu-id="6971a-305">Source port</span></span> | <span data-ttu-id="6971a-306">Port de destination</span><span class="sxs-lookup"><span data-stu-id="6971a-306">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6971a-307">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6971a-307">UDP/SRTP</span></span> | <span data-ttu-id="6971a-308">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="6971a-308">Transport Relay</span></span> | <span data-ttu-id="6971a-309">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-309">SBC</span></span> | <span data-ttu-id="6971a-310">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="6971a-310">50 000 -59 999</span></span>    | <span data-ttu-id="6971a-311">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-311">Defined on the SBC</span></span> |
| <span data-ttu-id="6971a-312">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6971a-312">UDP/SRTP</span></span> | <span data-ttu-id="6971a-313">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-313">SBC</span></span> | <span data-ttu-id="6971a-314">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="6971a-314">Transport Relay</span></span> | <span data-ttu-id="6971a-315">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-315">Defined on the SBC</span></span> | <span data-ttu-id="6971a-316">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6971a-316">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="6971a-317">Microsoft recommande au moins deux ports par appel simultané sur le SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-317">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="6971a-318">Étant donné que Microsoft dispose de deux versions de relais de transport, les suivantes sont requises :</span><span class="sxs-lookup"><span data-stu-id="6971a-318">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="6971a-319">v4, qui ne peut fonctionner qu’avec la plage de ports 50 000 à 59 999</span><span class="sxs-lookup"><span data-stu-id="6971a-319">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="6971a-320">v6, qui fonctionne avec les ports 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6971a-320">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="6971a-321">Pour l’instant, la dérivation média ne prend en charge que la version v4 des relais de transport.</span><span class="sxs-lookup"><span data-stu-id="6971a-321">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="6971a-322">Nous introduirons la prise en charge de la v6 à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="6971a-322">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="6971a-323">Vous devez ouvrir les ports 3478 et 3479 pour la transition.</span><span class="sxs-lookup"><span data-stu-id="6971a-323">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="6971a-324">Lorsque Microsoft introduit la prise en charge des relais de transport v6 avec la dérivation média, vous n’avez pas besoin de reconfigurer votre équipement réseau ou SBCS.</span><span class="sxs-lookup"><span data-stu-id="6971a-324">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="6971a-325">Exigences pour l’utilisation de processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="6971a-325">Requirements for using media processors</span></span>

<span data-ttu-id="6971a-326">Les processeurs de média sont toujours dans le chemin de médias des applications vocales et des clients web (par exemple, Teams clients dans Edge ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="6971a-326">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="6971a-327">La configuration requise est la même que pour une configuration sans contournement.</span><span class="sxs-lookup"><span data-stu-id="6971a-327">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="6971a-328">La plage IP du trafic de médias est</span><span class="sxs-lookup"><span data-stu-id="6971a-328">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6971a-329">Office 365 et Office 365 Cloud de la communauté du secteur public de travail</span><span class="sxs-lookup"><span data-stu-id="6971a-329">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="6971a-330">52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6971a-330">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6971a-331">Office 365 Cloud de la communauté du secteur public Environnement DoD</span><span class="sxs-lookup"><span data-stu-id="6971a-331">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6971a-332">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6971a-332">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6971a-333">Office 365 Cloud de la communauté du secteur public environnement élevé</span><span class="sxs-lookup"><span data-stu-id="6971a-333">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6971a-334">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6971a-334">52.127.88.0/21</span></span>

<span data-ttu-id="6971a-335">La plage de ports des processeurs multimédias (applicable à tous les environnements) est indiquée dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="6971a-335">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="6971a-336">Trafic</span><span class="sxs-lookup"><span data-stu-id="6971a-336">Traffic</span></span> | <span data-ttu-id="6971a-337">De</span><span class="sxs-lookup"><span data-stu-id="6971a-337">From</span></span> | <span data-ttu-id="6971a-338">À</span><span class="sxs-lookup"><span data-stu-id="6971a-338">To</span></span> | <span data-ttu-id="6971a-339">Port source</span><span class="sxs-lookup"><span data-stu-id="6971a-339">Source port</span></span> | <span data-ttu-id="6971a-340">Port de destination</span><span class="sxs-lookup"><span data-stu-id="6971a-340">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6971a-341">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6971a-341">UDP/SRTP</span></span> | <span data-ttu-id="6971a-342">Processeur multimédia</span><span class="sxs-lookup"><span data-stu-id="6971a-342">Media Processor</span></span> | <span data-ttu-id="6971a-343">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-343">SBC</span></span> | <span data-ttu-id="6971a-344">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6971a-344">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="6971a-345">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-345">Defined on the SBC</span></span> |
| <span data-ttu-id="6971a-346">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6971a-346">UDP/SRTP</span></span> | <span data-ttu-id="6971a-347">SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-347">SBC</span></span> | <span data-ttu-id="6971a-348">Processeur multimédia</span><span class="sxs-lookup"><span data-stu-id="6971a-348">Media Processor</span></span> | <span data-ttu-id="6971a-349">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="6971a-349">Defined on the SBC</span></span> | <span data-ttu-id="6971a-350">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6971a-350">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="6971a-351">Configurer des ligne distinctes pour la dérivation média et la dérivation non multimédia</span><span class="sxs-lookup"><span data-stu-id="6971a-351">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="6971a-352">Si vous migrez vers la dérivation média à partir d’une dérivation non multimédia et souhaitez confirmer la fonctionnalité avant de migrer toute utilisation vers la dérivation média, vous pouvez créer une ligne distincte et une stratégie de routage vocale en ligne distinctes pour router vers la ligne de dérivation média et affecter à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6971a-352">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="6971a-353">Étapes de configuration générales :</span><span class="sxs-lookup"><span data-stu-id="6971a-353">High-level configuration steps:</span></span>

- <span data-ttu-id="6971a-354">Identifiez les utilisateurs qui testent la dérivation média.</span><span class="sxs-lookup"><span data-stu-id="6971a-354">Identify users to test media bypass.</span></span>

- <span data-ttu-id="6971a-355">Créez deux ligne distinctes avec différents FQDN : l’une activée pour la dérivation média ; l’autre non.</span><span class="sxs-lookup"><span data-stu-id="6971a-355">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="6971a-356">Les deux ligne pointent vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="6971a-356">Both trunks point to the same SBC.</span></span> <span data-ttu-id="6971a-357">Les ports de signalisation SIP du TLS doivent être différents.</span><span class="sxs-lookup"><span data-stu-id="6971a-357">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="6971a-358">Les ports pour les médias doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="6971a-358">The ports for media must be the same.</span></span>

- <span data-ttu-id="6971a-359">Créez une stratégie de routage voix en ligne et affectez la ligne de dérivation média aux itinéraires correspondants à l’utilisation PSTN pour cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="6971a-359">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="6971a-360">Affectez la nouvelle stratégie de routage voix en ligne aux utilisateurs que vous avez identifiés pour tester la dérivation média.</span><span class="sxs-lookup"><span data-stu-id="6971a-360">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="6971a-361">L’exemple ci-dessous illustre cette logique.</span><span class="sxs-lookup"><span data-stu-id="6971a-361">The example below illustrates this logic.</span></span>

| <span data-ttu-id="6971a-362">Ensemble d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6971a-362">Set of users</span></span> | <span data-ttu-id="6971a-363">Nombre d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6971a-363">Number of users</span></span> | <span data-ttu-id="6971a-364">Trunk FQDN assigned in OVRP</span><span class="sxs-lookup"><span data-stu-id="6971a-364">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="6971a-365">Contournement multimédia activé</span><span class="sxs-lookup"><span data-stu-id="6971a-365">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="6971a-366">Utilisateurs avec ligne de contournement non multimédia</span><span class="sxs-lookup"><span data-stu-id="6971a-366">Users with non-media bypass trunk</span></span> | <span data-ttu-id="6971a-367">980</span><span class="sxs-lookup"><span data-stu-id="6971a-367">980</span></span> | <span data-ttu-id="6971a-368">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="6971a-368">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="6971a-369">false</span><span class="sxs-lookup"><span data-stu-id="6971a-369">false</span></span> |
<span data-ttu-id="6971a-370">Utilisateurs avec ligne de dérivation média</span><span class="sxs-lookup"><span data-stu-id="6971a-370">Users with media bypass trunk</span></span> | <span data-ttu-id="6971a-371">20</span><span class="sxs-lookup"><span data-stu-id="6971a-371">20</span></span> | <span data-ttu-id="6971a-372">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="6971a-372">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="6971a-373">true</span><span class="sxs-lookup"><span data-stu-id="6971a-373">true</span></span> | 

<span data-ttu-id="6971a-374">Les deux ligne peuvent pointer vers le même SBC avec la même adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="6971a-374">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="6971a-375">Les ports de signalisation TLS sur le SBC doivent être différents, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="6971a-375">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="6971a-376">Notez que vous devez vous assurer que votre certificat prend en charge les deux ligne.</span><span class="sxs-lookup"><span data-stu-id="6971a-376">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="6971a-377">En san san, vous devez avoir deux noms **(sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="6971a-377">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6971a-378">![Affiche les deux ligne peut pointer vers le même SBC avec la même adresse IP publique](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="6971a-378">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="6971a-379">Pour plus d’informations sur la configuration de deux ligne sur le même SBC, consultez la documentation fournie par votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="6971a-379">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="6971a-380">Documentation sur le déploiement de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="6971a-380">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="6971a-381">Documentation sur le déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="6971a-381">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="6971a-382">Documentation de déploiement de Communications du ruban</span><span class="sxs-lookup"><span data-stu-id="6971a-382">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="6971a-383">Documentation sur le déploiement des systèmes TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="6971a-383">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="6971a-384">Points de terminaison clients pris en charge avec la dérivation média</span><span class="sxs-lookup"><span data-stu-id="6971a-384">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="6971a-385">La dérivation média est prise en charge avec tous les clients Teams bureau, les clients Android et iOS et les Teams Téléphone périphériques.</span><span class="sxs-lookup"><span data-stu-id="6971a-385">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="6971a-386">Pour tous les autres points de terminaison qui ne supportent pas la dérivation média, nous convertirons l’appel en appel sans contournement, même s’il a été démarré en tant qu’appel de contournement.</span><span class="sxs-lookup"><span data-stu-id="6971a-386">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="6971a-387">Cette situation se produit automatiquement et ne nécessite aucune action de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6971a-387">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="6971a-388">Cela inclut Skype Entreprise téléphones 3PIP et les clients web Teams qui supportent l’appel de routage direct (clients WebRTC s’exécutant sur Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="6971a-388">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="6971a-389">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6971a-389">See also</span></span>

[<span data-ttu-id="6971a-390">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="6971a-390">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
