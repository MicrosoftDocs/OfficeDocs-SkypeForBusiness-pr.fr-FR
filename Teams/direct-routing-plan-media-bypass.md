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
description: Découvrez comment planifier la dérivation média avec le routage direct du système téléphonique, ce qui vous permet de raccourcir le chemin d'accès du trafic de médias et d'améliorer les performances.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2cbe739a567588b44bef87f7b852ed8de965ad3
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899095"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="06e28-103">Planifier le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="06e28-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="06e28-104">À propos de la dérivation média avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="06e28-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="06e28-105">La dérivation média vous permet de raccourcir le chemin d'accès au trafic de médias et de réduire le nombre de sauts en transit pour de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="06e28-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="06e28-106">Avec la dérivation média, le média est conservé entre le contrôleur de bordure de session (SBC) et le client au lieu de l'envoyer via le système téléphonique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06e28-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="06e28-107">Pour configurer la dérivation média, le SBC et le client doivent se trouver dans le même emplacement ou réseau.</span><span class="sxs-lookup"><span data-stu-id="06e28-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="06e28-108">Vous pouvez contrôler la dérivation média pour chaque SBC à l'aide de la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** définie sur true ou false.</span><span class="sxs-lookup"><span data-stu-id="06e28-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="06e28-109">Si vous activez la dérivation média, cela ne signifie pas que tout le trafic de médias restera au sein du réseau d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="06e28-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="06e28-110">Cet article décrit le flux d'appels dans différents scénarios.</span><span class="sxs-lookup"><span data-stu-id="06e28-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="06e28-111">Les diagrammes ci-dessous illustrent la différence de flux d'appels avec et sans contournement des médias.</span><span class="sxs-lookup"><span data-stu-id="06e28-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="06e28-112">Sans contournement multimédia, lorsqu'un client effectue ou reçoit un appel, le trafic de signalisation et le flux de médias entre le SBC, le système téléphonique Microsoft et le client Teams, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="06e28-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06e28-113">![Affiche le trafic de signalisation et le flux multimédia sans contournement média](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="06e28-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="06e28-114">Supposons toutefois qu'un utilisateur se trouve dans le même bâtiment ou le même réseau que le SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="06e28-115">Par exemple, supposons qu'un utilisateur se trouve dans un bâtiment dans Le Monde appelle un utilisateur PSTN :</span><span class="sxs-lookup"><span data-stu-id="06e28-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="06e28-116">**Sans contournement** des médias, les médias circulent via Amsterdam ou Dublin (où les centres de données Microsoft sont déployés), puis reviennent au SBC dans Le Monde.</span><span class="sxs-lookup"><span data-stu-id="06e28-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="06e28-117">Le centre de données en Europe est sélectionné, car le SBC est en Europe et Microsoft utilise le centre de données le plus proche du SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="06e28-118">Bien que cette approche n'affecte pas la qualité des appels en raison de l'optimisation du flux de trafic au sein des réseaux Microsoft dans la plupart des régions, le trafic présente une boucle inutile.</span><span class="sxs-lookup"><span data-stu-id="06e28-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="06e28-119">**Avec la dérivation** média, les médias sont conservés directement entre l'utilisateur Teams et le SBC, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="06e28-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="06e28-120">![Affiche le trafic de signalisation et le flux multimédia avec contournement des médias](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="06e28-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="06e28-121">La dérivation multimédia s'appuie sur des protocoles appelés ice (Interactive Connectivity Connectivity Connectivité) sur le client Teams et ICE sur le SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="06e28-122">Ces protocoles permettent au routage direct d'utiliser le chemin de médias le plus direct pour une qualité optimale.</span><span class="sxs-lookup"><span data-stu-id="06e28-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="06e28-123">ICE et ICE Lite sont des normes WebRTC.</span><span class="sxs-lookup"><span data-stu-id="06e28-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="06e28-124">Pour plus d'informations sur ces protocoles, voir RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="06e28-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="06e28-125">Planification du flux d'appels et du pare-feu</span><span class="sxs-lookup"><span data-stu-id="06e28-125">Call flow and firewall planning</span></span>

<span data-ttu-id="06e28-126">La planification du flux d'appels et du pare-feu varie selon que l'utilisateur a un accès direct à l'adresse IP publique du SBC et si l'utilisateur est à l'intérieur ou à l'extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="06e28-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="06e28-127">Flux d'appels si l'utilisateur dispose d'un accès direct à l'adresse IP publique du SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="06e28-128">Si l'utilisateur dispose d'un accès direct à l'adresse IP publique du SBC, le flux d'appels est le suivant :</span><span class="sxs-lookup"><span data-stu-id="06e28-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="06e28-129">Pour la dérivation média, le client Teams doit avoir accès à l'adresse IP publique du SBC, même à partir d'un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="06e28-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="06e28-130">Si le média direct n'est pas souhaité, il peut être transmis via un relais de transport.</span><span class="sxs-lookup"><span data-stu-id="06e28-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="06e28-131">Il s'agit de la solution recommandée lorsqu'un utilisateur se trouve dans le même bâtiment et/ou réseau que le SBC (supprimer les composants Microsoft Cloud du chemin de médias).</span><span class="sxs-lookup"><span data-stu-id="06e28-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="06e28-132">Les signaux circulent toujours via le cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06e28-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="06e28-133">Le diagramme suivant montre le flux d'appels lorsque la dérivation média est activée, que le client est interne et que le client peut accéder à l'adresse IP publique du support SBC :</span><span class="sxs-lookup"><span data-stu-id="06e28-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="06e28-134">Les flèches et les valeurs numériques des chemins d'accès sont conformes aux flux [d'appels de Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="06e28-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="06e28-135">Le trafic de signalisation SIP prend toujours les chemins 4 et 4' (selon le sens de trafic).</span><span class="sxs-lookup"><span data-stu-id="06e28-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="06e28-136">Les médias restent locaux et prennent le chemin 5b.</span><span class="sxs-lookup"><span data-stu-id="06e28-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06e28-137">![Présente le flux d'appels avec contournement multimédia activé, le client est interne](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="06e28-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="06e28-138">Flux d'appels si l'utilisateur n'a pas accès à l'adresse IP publique du SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="06e28-139">Le tableau suivant décrit le flux d'appels si l'utilisateur n'a pas accès à l'adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="06e28-140">Par exemple, supposons que l'utilisateur soit externe et que l'administrateur client a décidé de ne pas ouvrir l'adresse IP publique du SBC à tous les utilisateurs d'Internet, mais uniquement au cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06e28-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="06e28-141">Les composants internes du trafic peuvent être acheminés via les relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="06e28-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="06e28-142">Vous devez tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="06e28-142">Consider the following:</span></span>

- <span data-ttu-id="06e28-143">Les relais de transport Teams sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="06e28-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="06e28-144">Pour la dérivation média, Microsoft utilise une version de relais de transport qui nécessite l'ouverture de ports 50 000 à 59 999 entre les relais de transport Teams et le SBC (à l'avenir, nous prévoyons de passer à la version qui nécessite uniquement 3478 et 3479 ports).</span><span class="sxs-lookup"><span data-stu-id="06e28-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="06e28-145">Le diagramme suivant illustre le flux d'appels lorsque la dérivation média est activée, que le client est externe et que le client ne peut pas accéder à l'adresse IP publique du contrôleur de session en bordure (les médias sont relayés par le relais de transport Teams).</span><span class="sxs-lookup"><span data-stu-id="06e28-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="06e28-146">Les flèches et les valeurs numériques des chemins d'accès sont conformes aux flux [d'appels de Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="06e28-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="06e28-147">Le média est relayé par les chemins d'accès 3, 3', 4 et 4'</span><span class="sxs-lookup"><span data-stu-id="06e28-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06e28-148">![Affiche le flux d'appels si l'utilisateur n'a pas accès à l'adresse IP publique du SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="06e28-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="06e28-149">Flux d'appels si un utilisateur se trouve en dehors du réseau et a accès à l'adresse IP publique du SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="06e28-150">Cette configuration n'est pas recommandée, car elle ne prend pas en compte les relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="06e28-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="06e28-151">Au lieu de cela, vous devez tenir compte du scénario précédent où l'utilisateur n'a pas accès à l'adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="06e28-152">Le diagramme suivant montre le flux d'appels lorsque la dérivation média est activée, que le client est externe et que le client peut atteindre l'adresse IP publique du support SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="06e28-153">Les flèches et les valeurs numériques des chemins d'accès sont conformes à l'article sur les flux d'appels [de Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="06e28-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="06e28-154">Le trafic de signalisation SIP prend toujours les chemins 3 et 3' (selon le sens du trafic).</span><span class="sxs-lookup"><span data-stu-id="06e28-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="06e28-155">Flux multimédias en utilisant le chemin d'accès 2.</span><span class="sxs-lookup"><span data-stu-id="06e28-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06e28-156">![Affiche le flux d'appels si l'utilisateur n'a pas accès à l'adresse IP publique du SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="06e28-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="06e28-157">Utilisation de processeurs multimédias et de relais de transport</span><span class="sxs-lookup"><span data-stu-id="06e28-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="06e28-158">Microsoft Cloud peut utiliser deux composants dans le chemin d'accès du trafic de médias : Processeurs de média et Relais de transport.</span><span class="sxs-lookup"><span data-stu-id="06e28-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="06e28-159">Le processeur de média est un composant public qui gère les éléments multimédias dans les cas qui ne contournent pas et gère les médias pour les applications vocales.</span><span class="sxs-lookup"><span data-stu-id="06e28-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="06e28-160">Les processeurs multimédias sont toujours dans le chemin pour les appels sans contournement de l'utilisateur final, mais jamais dans le chemin pour les appels contournements.</span><span class="sxs-lookup"><span data-stu-id="06e28-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="06e28-161">Les processeurs multimédias sont toujours dans le chemin d'accès de toutes les applications vocales, telles que le parc des appels, les Standard automatique de l'organisation et les files d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="06e28-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="06e28-162">Le relais de transport est utilisé pour se connecter au service de transport le plus proche pour envoyer le trafic en temps réel.</span><span class="sxs-lookup"><span data-stu-id="06e28-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="06e28-163">Les relais de transport peuvent ou non se trouver dans le chemin d'accès des appels contournements (provenant ou destinés à des utilisateurs finaux), selon l'endroit où se trouve l'utilisateur et la manière dont le réseau est configuré.</span><span class="sxs-lookup"><span data-stu-id="06e28-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="06e28-164">Le diagramme suivant montre deux flux d'appels : un avec la dérivation média activée et la seconde avec la dérivation média désactivée.</span><span class="sxs-lookup"><span data-stu-id="06e28-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="06e28-165">Le diagramme illustre uniquement le trafic provenant d'utilisateurs - ou destinés à des utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="06e28-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="06e28-166">Le contrôleur de média est un microservice dans Azure qui attribue des processeurs multimédias et crée des offres SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="06e28-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="06e28-167">Le proxy SIP est un composant qui traduit le signalisation HTTP REST utilisé dans Teams en SIP.</span><span class="sxs-lookup"><span data-stu-id="06e28-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06e28-168">![Présente les flux d'appels avec la dérivation média activée et désactivée](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="06e28-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="06e28-169">Le tableau ci-dessous résume la différence entre les processeurs de média et les relais de transport.</span><span class="sxs-lookup"><span data-stu-id="06e28-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="06e28-170">Processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="06e28-170">Media Processors</span></span> | <span data-ttu-id="06e28-171">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="06e28-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="06e28-172">Chemin de médias pour les appels non contournements pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="06e28-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="06e28-173">Toujours</span><span class="sxs-lookup"><span data-stu-id="06e28-173">Always</span></span> | <span data-ttu-id="06e28-174">Si le client ne parviennent pas à joindre le processeur de média directement</span><span class="sxs-lookup"><span data-stu-id="06e28-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="06e28-175">Dans le chemin de médias pour les appels contournements pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="06e28-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="06e28-176">Jamais</span><span class="sxs-lookup"><span data-stu-id="06e28-176">Never</span></span> | <span data-ttu-id="06e28-177">Si le client ne peut pas accéder au SBC sur l'adresse IP publique</span><span class="sxs-lookup"><span data-stu-id="06e28-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="06e28-178">Dans le chemin multimédia des applications vocales</span><span class="sxs-lookup"><span data-stu-id="06e28-178">In media path for voice applications</span></span> | <span data-ttu-id="06e28-179">Toujours</span><span class="sxs-lookup"><span data-stu-id="06e28-179">Always</span></span> | <span data-ttu-id="06e28-180">Jamais</span><span class="sxs-lookup"><span data-stu-id="06e28-180">Never</span></span> | 
<span data-ttu-id="06e28-181">Can do transcoding (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="06e28-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="06e28-182">Oui</span><span class="sxs-lookup"><span data-stu-id="06e28-182">Yes</span></span> | <span data-ttu-id="06e28-183">Non, seul l'audio est relayé entre les points de terminaison</span><span class="sxs-lookup"><span data-stu-id="06e28-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="06e28-184">Nombre d'instances dans le monde et emplacement</span><span class="sxs-lookup"><span data-stu-id="06e28-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="06e28-185">10 total : 2 dans la région Est et Ouest des États-Unis ; 2 à Amsterdam et Dublin ; 2 à Hong Kong et Singapour ; 2 au Japon ; 2 en Australie de l'Est et du Sud-est</span><span class="sxs-lookup"><span data-stu-id="06e28-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="06e28-186">Multiple</span><span class="sxs-lookup"><span data-stu-id="06e28-186">Multiple</span></span>

<span data-ttu-id="06e28-187">Les plages d'adresses IP sont les plus diverses :</span><span class="sxs-lookup"><span data-stu-id="06e28-187">The IP ranges are:</span></span>
- <span data-ttu-id="06e28-188">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="06e28-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="06e28-189">52.120.0.0/14 (adresses IP de 52.120.0.1 à 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="06e28-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="06e28-190">\* Explication de la transcodage :</span><span class="sxs-lookup"><span data-stu-id="06e28-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="06e28-191">Le processeur multimédia est B2BUA, ce qui signifie qu'il peut changer un codec (par exemple, SILK du client Teams en MP et G.711 entre MP et SBC).</span><span class="sxs-lookup"><span data-stu-id="06e28-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="06e28-192">Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n'est jamais modifié entre le client et le SBC, même si le trafic est acheminé par relais.</span><span class="sxs-lookup"><span data-stu-id="06e28-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="06e28-193">Utilisation de processeurs multimédias Teams si la ligne est configurée pour la dérivation média</span><span class="sxs-lookup"><span data-stu-id="06e28-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="06e28-194">Les processeurs multimédias Teams sont toujours insérés dans le chemin de médias dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="06e28-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="06e28-195">L'appel est recalé de 1:1 à un appel de groupe</span><span class="sxs-lookup"><span data-stu-id="06e28-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="06e28-196">L'appel va être reçu par un utilisateur fédéré de Teams</span><span class="sxs-lookup"><span data-stu-id="06e28-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="06e28-197">L'appel est transféré à un utilisateur Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="06e28-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="06e28-198">Assurez-vous que votre SBC a accès aux plages Processeurs de média et Relais de transport, comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="06e28-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="06e28-199">Signalisation SIP : FQDN</span><span class="sxs-lookup"><span data-stu-id="06e28-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="06e28-200">Pour le signalisation SIP, les exigences de nom de passe (FQDN) et de pare-feu sont identiques à ceux des cas non contourné.</span><span class="sxs-lookup"><span data-stu-id="06e28-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="06e28-201">Le routage direct est proposé dans les environnements Microsoft 365 ou Office 365 suivants :</span><span class="sxs-lookup"><span data-stu-id="06e28-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="06e28-202">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="06e28-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="06e28-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="06e28-203">Office 365 GCC</span></span>
- <span data-ttu-id="06e28-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="06e28-204">Office 365 GCC High</span></span>
- <span data-ttu-id="06e28-205">Office 365 DoD En savoir plus sur les [environnements Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) et us Government, tels que GCC, GCC High et DoD.</span><span class="sxs-lookup"><span data-stu-id="06e28-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="06e28-206">Environnements Microsoft 365, Office 365 et GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="06e28-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="06e28-207">Les points de connexion pour le routage direct sont les trois FQDN suivants :</span><span class="sxs-lookup"><span data-stu-id="06e28-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="06e28-208">**sip.pstnhub.microsoft.com** , vous devez d'abord essayer le FQDN global.</span><span class="sxs-lookup"><span data-stu-id="06e28-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="06e28-209">Lorsque le SBC envoie une demande de résolution de ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de données Azure principal affecté au SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="06e28-210">L'affectation est basée sur les mesures de performance des centres de données et la proximité géographique par rapport au SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="06e28-211">L'adresse IP renvoyée correspond au FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="06e28-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="06e28-212">**sip2.pstnhub.microsoft.com** (FQDN secondaire) géographiquement à la région de deuxième priorité.</span><span class="sxs-lookup"><span data-stu-id="06e28-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="06e28-213">**sip3.pstnhub.microsoft.com** – FQDN de l'situation géographique de la troisième région.</span><span class="sxs-lookup"><span data-stu-id="06e28-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="06e28-214">Vous devez placer ces trois FQDN pour :</span><span class="sxs-lookup"><span data-stu-id="06e28-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="06e28-215">Offrez une expérience optimale (moins chargé et le plus proche du centre de données SBC attribué en interrogeant le premier FQDN).</span><span class="sxs-lookup"><span data-stu-id="06e28-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="06e28-216">Offrez un échec lorsqu'une connexion à partir d'un SBC est établie vers un centre de données qui rencontre un problème temporaire.</span><span class="sxs-lookup"><span data-stu-id="06e28-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="06e28-217">Pour plus d'informations, voir le mécanisme deover ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="06e28-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="06e28-218">Les noms de **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** et sip3.pstnhub.microsoft.com sont  résolus avec l'une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="06e28-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="06e28-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="06e28-219">52.114.148.0</span></span>
- <span data-ttu-id="06e28-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="06e28-220">52.114.132.46</span></span>
- <span data-ttu-id="06e28-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="06e28-221">52.114.16.74</span></span>
- <span data-ttu-id="06e28-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="06e28-222">52.114.20.29</span></span>
- <span data-ttu-id="06e28-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="06e28-223">52.114.75.24</span></span>
- <span data-ttu-id="06e28-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="06e28-224">52.114.76.76</span></span>
- <span data-ttu-id="06e28-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="06e28-225">52.114.7.24</span></span>
- <span data-ttu-id="06e28-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="06e28-226">52.114.14.70</span></span>

<span data-ttu-id="06e28-227">Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.</span><span class="sxs-lookup"><span data-stu-id="06e28-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="06e28-228">Si votre pare-feu prend en charge les noms DNS, le nom de domaine sip-all.pstnhub.microsoft.com **est** résolu pour toutes ces adresses IP.</span><span class="sxs-lookup"><span data-stu-id="06e28-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="06e28-229">Environnement Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="06e28-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="06e28-230">Le point de connexion pour le routage direct est le FQDN suivant :</span><span class="sxs-lookup"><span data-stu-id="06e28-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="06e28-231">**sip.pstnhub.dod.teams.microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="06e28-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="06e28-232">Étant donné que l'environnement Office 365 DoD existe uniquement dans les centres de données américains, il n'existe aucun nom de fQDN secondaire et secondaire.</span><span class="sxs-lookup"><span data-stu-id="06e28-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="06e28-233">Les noms de noms de sip.pstnhub.dod.teams.microsoft.us seront résolus à l'une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="06e28-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="06e28-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="06e28-234">52.127.64.33</span></span>
- <span data-ttu-id="06e28-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="06e28-235">52.127.68.34</span></span>

<span data-ttu-id="06e28-236">Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.</span><span class="sxs-lookup"><span data-stu-id="06e28-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="06e28-237">Si votre pare-feu prend en charge les noms DNS, le nom de domaine sip.pstnhub.dod.teams.microsoft.us est résolu pour toutes ces adresses IP.</span><span class="sxs-lookup"><span data-stu-id="06e28-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="06e28-238">Environnement Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="06e28-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="06e28-239">Le point de connexion pour le routage direct est le FQDN suivant :</span><span class="sxs-lookup"><span data-stu-id="06e28-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="06e28-240">**sip.pstnhub.gov.teams.microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="06e28-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="06e28-241">Étant donné que l'environnement GCC High existe uniquement dans les centres de données américains, il n'existe aucun nom de fQDN secondaire et secondaire secondaire.</span><span class="sxs-lookup"><span data-stu-id="06e28-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="06e28-242">Les noms de noms de sip.pstnhub.gov.teams.microsoft.us seront résolus à l'une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="06e28-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="06e28-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="06e28-243">52.127.88.59</span></span>
- <span data-ttu-id="06e28-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="06e28-244">52.127.92.64</span></span>

<span data-ttu-id="06e28-245">Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.</span><span class="sxs-lookup"><span data-stu-id="06e28-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="06e28-246">Si votre pare-feu prend en charge les noms DNS, le nom de domaine sip.pstnhub.gov.teams.microsoft.us est résolu pour toutes ces adresses IP.</span><span class="sxs-lookup"><span data-stu-id="06e28-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="06e28-247">Signalisation SIP : ports</span><span class="sxs-lookup"><span data-stu-id="06e28-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="06e28-248">La demande de port est la même pour tous les environnements Office 365 pour lequel un routage direct est proposé :</span><span class="sxs-lookup"><span data-stu-id="06e28-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="06e28-249">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="06e28-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="06e28-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="06e28-250">Office 365 GCC</span></span>
- <span data-ttu-id="06e28-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="06e28-251">Office 365 GCC High</span></span>
- <span data-ttu-id="06e28-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="06e28-252">Office 365 DoD</span></span>

<span data-ttu-id="06e28-253">Vous devez utiliser les ports suivants :</span><span class="sxs-lookup"><span data-stu-id="06e28-253">You must use the following ports:</span></span>

| <span data-ttu-id="06e28-254">Trafic</span><span class="sxs-lookup"><span data-stu-id="06e28-254">Traffic</span></span> | <span data-ttu-id="06e28-255">De</span><span class="sxs-lookup"><span data-stu-id="06e28-255">From</span></span> | <span data-ttu-id="06e28-256">À</span><span class="sxs-lookup"><span data-stu-id="06e28-256">To</span></span> | <span data-ttu-id="06e28-257">Port source</span><span class="sxs-lookup"><span data-stu-id="06e28-257">Source port</span></span> | <span data-ttu-id="06e28-258">Port de destination</span><span class="sxs-lookup"><span data-stu-id="06e28-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="06e28-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="06e28-259">SIP/TLS</span></span>| <span data-ttu-id="06e28-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="06e28-260">SIP Proxy</span></span> | <span data-ttu-id="06e28-261">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-261">SBC</span></span> | <span data-ttu-id="06e28-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="06e28-262">1024 - 65535</span></span> | <span data-ttu-id="06e28-263">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-263">Defined on the SBC</span></span> |
| <span data-ttu-id="06e28-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="06e28-264">SIP/TLS</span></span> | <span data-ttu-id="06e28-265">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-265">SBC</span></span> | <span data-ttu-id="06e28-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="06e28-266">SIP Proxy</span></span> | <span data-ttu-id="06e28-267">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-267">Defined on the SBC</span></span> | <span data-ttu-id="06e28-268">5061</span><span class="sxs-lookup"><span data-stu-id="06e28-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="06e28-269">Trafic de médias : ip et plages de ports</span><span class="sxs-lookup"><span data-stu-id="06e28-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="06e28-270">Le trafic de médias circule entre le client SBC et le client Teams si une connectivité directe est disponible ou via des relais de transport Teams si le client ne peut pas accéder au SBC à l’aide de l’adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="06e28-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="06e28-271">Conditions requises pour le trafic multimédia direct (entre le client Teams et le SBC)</span><span class="sxs-lookup"><span data-stu-id="06e28-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="06e28-272">Le client doit avoir accès aux ports spécifiés (voir tableau) sur l’adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="06e28-273">Si le client se trouve dans un réseau interne, le média passe à l’adresse IP publique du SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-273">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="06e28-274">Vous pouvez configurer l’épinglage de cheveux sur votre appareil NAT afin que le trafic ne quitte jamais l’équipement réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="06e28-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="06e28-275">Trafic</span><span class="sxs-lookup"><span data-stu-id="06e28-275">Traffic</span></span> | <span data-ttu-id="06e28-276">De</span><span class="sxs-lookup"><span data-stu-id="06e28-276">From</span></span> | <span data-ttu-id="06e28-277">À</span><span class="sxs-lookup"><span data-stu-id="06e28-277">To</span></span> | <span data-ttu-id="06e28-278">Port source</span><span class="sxs-lookup"><span data-stu-id="06e28-278">Source port</span></span> | <span data-ttu-id="06e28-279">Port de destination</span><span class="sxs-lookup"><span data-stu-id="06e28-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="06e28-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="06e28-280">UDP/SRTP</span></span> | <span data-ttu-id="06e28-281">Client</span><span class="sxs-lookup"><span data-stu-id="06e28-281">Client</span></span> | <span data-ttu-id="06e28-282">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-282">SBC</span></span> | <span data-ttu-id="06e28-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="06e28-283">50 000 – 50 019</span></span>  | <span data-ttu-id="06e28-284">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-284">Defined on the SBC</span></span> |
| <span data-ttu-id="06e28-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="06e28-285">UDP/SRTP</span></span> | <span data-ttu-id="06e28-286">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-286">SBC</span></span> | <span data-ttu-id="06e28-287">Client</span><span class="sxs-lookup"><span data-stu-id="06e28-287">Client</span></span> | <span data-ttu-id="06e28-288">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-288">Defined on the SBC</span></span> | <span data-ttu-id="06e28-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="06e28-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="06e28-290">Si votre périphérique réseau traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et le SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="06e28-291">Conditions requises pour l’utilisation de relais de transport</span><span class="sxs-lookup"><span data-stu-id="06e28-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="06e28-292">Les relais de transport sont dans la même plage que les processeurs multimédias (pour les cas sans contournement) :</span><span class="sxs-lookup"><span data-stu-id="06e28-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="06e28-293">Environnements Microsoft 365, Office 365 et GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="06e28-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="06e28-294">52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="06e28-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="06e28-295">Environnement Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="06e28-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="06e28-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="06e28-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="06e28-297">Environnement Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="06e28-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="06e28-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="06e28-298">52.127.88.0/21</span></span>


<span data-ttu-id="06e28-299">La plage de ports des relais de transport Teams (applicable à tous les environnements) est indiquée dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="06e28-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="06e28-300">Trafic</span><span class="sxs-lookup"><span data-stu-id="06e28-300">Traffic</span></span> | <span data-ttu-id="06e28-301">De</span><span class="sxs-lookup"><span data-stu-id="06e28-301">From</span></span> | <span data-ttu-id="06e28-302">À</span><span class="sxs-lookup"><span data-stu-id="06e28-302">To</span></span> | <span data-ttu-id="06e28-303">Port source</span><span class="sxs-lookup"><span data-stu-id="06e28-303">Source port</span></span> | <span data-ttu-id="06e28-304">Port de destination</span><span class="sxs-lookup"><span data-stu-id="06e28-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="06e28-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="06e28-305">UDP/SRTP</span></span> | <span data-ttu-id="06e28-306">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="06e28-306">Transport Relay</span></span> | <span data-ttu-id="06e28-307">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-307">SBC</span></span> | <span data-ttu-id="06e28-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="06e28-308">50 000 -59 999</span></span>    | <span data-ttu-id="06e28-309">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-309">Defined on the SBC</span></span> |
| <span data-ttu-id="06e28-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="06e28-310">UDP/SRTP</span></span> | <span data-ttu-id="06e28-311">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-311">SBC</span></span> | <span data-ttu-id="06e28-312">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="06e28-312">Transport Relay</span></span> | <span data-ttu-id="06e28-313">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-313">Defined on the SBC</span></span> | <span data-ttu-id="06e28-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="06e28-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="06e28-315">Microsoft recommande au moins deux ports par appel simultané sur le SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="06e28-316">Étant donné que Microsoft dispose de deux versions de relais de transport, les suivantes sont requises :</span><span class="sxs-lookup"><span data-stu-id="06e28-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="06e28-317">v4, qui ne peut fonctionner qu’avec la plage de ports 50 000 à 59 999</span><span class="sxs-lookup"><span data-stu-id="06e28-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="06e28-318">v6, qui fonctionne avec les ports 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="06e28-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="06e28-319">Pour l’instant, la dérivation média ne prend en charge que la version v4 des relais de transport.</span><span class="sxs-lookup"><span data-stu-id="06e28-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="06e28-320">Nous introduirons la prise en charge de la v6 à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="06e28-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="06e28-321">Vous devez ouvrir les ports 3478 et 3479 pour la transition.</span><span class="sxs-lookup"><span data-stu-id="06e28-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="06e28-322">Lorsque Microsoft introduit la prise en charge des relais de transport v6 avec la dérivation média, vous n’avez pas besoin de reconfigurer votre équipement réseau ou SBCS.</span><span class="sxs-lookup"><span data-stu-id="06e28-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="06e28-323">Exigences pour l’utilisation de processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="06e28-323">Requirements for using media processors</span></span>

<span data-ttu-id="06e28-324">Les processeurs multimédias sont toujours dans le chemin de médias des applications vocales et des clients Web (par exemple, les clients Teams dans Edge ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="06e28-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="06e28-325">La configuration requise est la même que pour une configuration sans contournement.</span><span class="sxs-lookup"><span data-stu-id="06e28-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="06e28-326">La plage IP du trafic de médias est</span><span class="sxs-lookup"><span data-stu-id="06e28-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="06e28-327">Environnements Office 365 et GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="06e28-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="06e28-328">52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="06e28-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="06e28-329">Environnement Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="06e28-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="06e28-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="06e28-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="06e28-331">Environnement Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="06e28-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="06e28-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="06e28-332">52.127.88.0/21</span></span>

<span data-ttu-id="06e28-333">La plage de ports des processeurs multimédias (applicable à tous les environnements) est indiquée dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="06e28-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="06e28-334">Trafic</span><span class="sxs-lookup"><span data-stu-id="06e28-334">Traffic</span></span> | <span data-ttu-id="06e28-335">De</span><span class="sxs-lookup"><span data-stu-id="06e28-335">From</span></span> | <span data-ttu-id="06e28-336">À</span><span class="sxs-lookup"><span data-stu-id="06e28-336">To</span></span> | <span data-ttu-id="06e28-337">Port source</span><span class="sxs-lookup"><span data-stu-id="06e28-337">Source port</span></span> | <span data-ttu-id="06e28-338">Port de destination</span><span class="sxs-lookup"><span data-stu-id="06e28-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="06e28-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="06e28-339">UDP/SRTP</span></span> | <span data-ttu-id="06e28-340">Processeur multimédia</span><span class="sxs-lookup"><span data-stu-id="06e28-340">Media Processor</span></span> | <span data-ttu-id="06e28-341">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-341">SBC</span></span> | <span data-ttu-id="06e28-342">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="06e28-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="06e28-343">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-343">Defined on the SBC</span></span> |
| <span data-ttu-id="06e28-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="06e28-344">UDP/SRTP</span></span> | <span data-ttu-id="06e28-345">SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-345">SBC</span></span> | <span data-ttu-id="06e28-346">Processeur multimédia</span><span class="sxs-lookup"><span data-stu-id="06e28-346">Media Processor</span></span> | <span data-ttu-id="06e28-347">Défini sur le SBC</span><span class="sxs-lookup"><span data-stu-id="06e28-347">Defined on the SBC</span></span> | <span data-ttu-id="06e28-348">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="06e28-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="06e28-349">Configurer des ligne distinctes pour la dérivation média et la dérivation non multimédia</span><span class="sxs-lookup"><span data-stu-id="06e28-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="06e28-350">Si vous migrez vers la dérivation média à partir d’une dérivation non multimédia et souhaitez confirmer la fonctionnalité avant de migrer toute utilisation vers la dérivation média, vous pouvez créer une ligne distincte et une stratégie de routage vocale en ligne distinctes pour router vers la ligne de dérivation média et affecter à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="06e28-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="06e28-351">Étapes de configuration générales :</span><span class="sxs-lookup"><span data-stu-id="06e28-351">High-level configuration steps:</span></span>

- <span data-ttu-id="06e28-352">Identifiez les utilisateurs qui testent la dérivation média.</span><span class="sxs-lookup"><span data-stu-id="06e28-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="06e28-353">Créez deux ligne distinctes avec différents FQDN : l’une activée pour la dérivation média ; l’autre non.</span><span class="sxs-lookup"><span data-stu-id="06e28-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="06e28-354">Les deux ligne pointent vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="06e28-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="06e28-355">Les ports de signalisation SIP du TLS doivent être différents.</span><span class="sxs-lookup"><span data-stu-id="06e28-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="06e28-356">Les ports pour les médias doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="06e28-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="06e28-357">Créez une stratégie de routage voix en ligne et affectez la ligne de dérivation média aux itinéraires correspondants à l’utilisation PSTN pour cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="06e28-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="06e28-358">Affectez la nouvelle stratégie de routage voix en ligne aux utilisateurs que vous avez identifiés pour tester la dérivation média.</span><span class="sxs-lookup"><span data-stu-id="06e28-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="06e28-359">L'exemple ci-dessous illustre cette logique.</span><span class="sxs-lookup"><span data-stu-id="06e28-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="06e28-360">Ensemble d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="06e28-360">Set of users</span></span> | <span data-ttu-id="06e28-361">Nombre d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="06e28-361">Number of users</span></span> | <span data-ttu-id="06e28-362">Trunk FQDN assigned in OVRP</span><span class="sxs-lookup"><span data-stu-id="06e28-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="06e28-363">Contournement multimédia activé</span><span class="sxs-lookup"><span data-stu-id="06e28-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="06e28-364">Utilisateurs avec ligne de contournement non multimédia</span><span class="sxs-lookup"><span data-stu-id="06e28-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="06e28-365">980</span><span class="sxs-lookup"><span data-stu-id="06e28-365">980</span></span> | <span data-ttu-id="06e28-366">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="06e28-366">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="06e28-367">false</span><span class="sxs-lookup"><span data-stu-id="06e28-367">false</span></span> |
<span data-ttu-id="06e28-368">Utilisateurs avec ligne de dérivation média</span><span class="sxs-lookup"><span data-stu-id="06e28-368">Users with media bypass trunk</span></span> | <span data-ttu-id="06e28-369">20</span><span class="sxs-lookup"><span data-stu-id="06e28-369">20</span></span> | <span data-ttu-id="06e28-370">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="06e28-370">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="06e28-371">true</span><span class="sxs-lookup"><span data-stu-id="06e28-371">true</span></span> | 

<span data-ttu-id="06e28-372">Les deux ligne peuvent pointer vers le même SBC avec la même adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="06e28-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="06e28-373">Les ports de signalisation TLS sur le SBC doivent être différents, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="06e28-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="06e28-374">Notez que vous devez vous assurer que votre certificat prend en charge les deux ligne.</span><span class="sxs-lookup"><span data-stu-id="06e28-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="06e28-375">En san san, vous devez avoir deux noms **(sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="06e28-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06e28-376">![Affiche les deux ligne peut pointer vers le même SBC avec la même adresse IP publique](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="06e28-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="06e28-377">Pour plus d'informations sur la configuration de deux ligne sur le même SBC, consultez la documentation fournie par votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="06e28-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="06e28-378">Documentation sur le déploiement de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="06e28-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="06e28-379">Documentation sur le déploiement d'Oracle</span><span class="sxs-lookup"><span data-stu-id="06e28-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="06e28-380">Documentation de déploiement de Communications du ruban</span><span class="sxs-lookup"><span data-stu-id="06e28-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="06e28-381">Documentation sur le déploiement des systèmes TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="06e28-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="06e28-382">Points de terminaison clients pris en charge avec la dérivation média</span><span class="sxs-lookup"><span data-stu-id="06e28-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="06e28-383">La dérivation média est prise en charge avec tous les clients de bureau Teams autonomes, les clients Android et iOS et les appareils Teams Phone.</span><span class="sxs-lookup"><span data-stu-id="06e28-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="06e28-384">Pour tous les autres points de terminaison qui ne supportent pas la dérivation média, nous convertirons l'appel en appel sans contournement, même s'il a été démarré en tant qu'appel de contournement.</span><span class="sxs-lookup"><span data-stu-id="06e28-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="06e28-385">Cette situation se produit automatiquement et ne nécessite aucune action de l'administrateur.</span><span class="sxs-lookup"><span data-stu-id="06e28-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="06e28-386">Cela inclut les téléphones 3PIP Skype Entreprise et les clients Web Teams qui supportent l'appel de routage direct (clients WebRTC s'exécutant sur Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="06e28-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="06e28-387">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06e28-387">See also</span></span>

[<span data-ttu-id="06e28-388">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="06e28-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
