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
description: Pour plus d’informations sur l’utilisation de la méthode de contournement multimédia avec le routage direct du système téléphonique, lisez cette rubrique.
ms.openlocfilehash: c40840e2169a67172f006a0f0910c715feb40253
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265639"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="86ee5-103">Planifier le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="86ee5-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="86ee5-104">À propos du contournement de média avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="86ee5-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="86ee5-105">La dérivation de médias vous permet d’abréger le chemin du trafic multimédia et de réduire le nombre de tronçons en transit pour de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="86ee5-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="86ee5-106">Par le biais du contournement du contenu multimédia, le contenu multimédia est maintenu entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via le système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="86ee5-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="86ee5-107">Pour configurer la dérivation multimédia, l’SBC et le client doivent se trouver dans le même emplacement ou réseau.</span><span class="sxs-lookup"><span data-stu-id="86ee5-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="86ee5-108">Vous pouvez contrôler la dérivation multimédia pour chaque SBC en utilisant la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** défini sur true ou false.</span><span class="sxs-lookup"><span data-stu-id="86ee5-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="86ee5-109">Cela ne signifie pas que le trafic multimédia restera dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="86ee5-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="86ee5-110">Cet article décrit le flux d’appels dans différents scénarios.</span><span class="sxs-lookup"><span data-stu-id="86ee5-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="86ee5-111">Les diagrammes ci-dessous montrent la différence de flux d’appels avec et sans dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="86ee5-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="86ee5-112">Sans dérivation multimédia, quand un client effectue ou reçoit un appel, la signalisation et le flux multimédia entre le SBC, le système Microsoft Phone et le client Teams, comme indiqué dans le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="86ee5-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Affiche la signalisation et le flux multimédia sans contournement du support multimédia](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="86ee5-114">Par exemple, supposons qu’un utilisateur se trouve dans le même bâtiment ou réseau que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="86ee5-115">Par exemple, supposons qu’un utilisateur participant à un bâtiment à Francfort effectue un appel vers un utilisateur RTC :</span><span class="sxs-lookup"><span data-stu-id="86ee5-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="86ee5-116">**Sans dérivation multimédia**, le contenu multimédia sera transmis par l’intermédiaire d’Amsterdam ou de Dublin (sur lequel sont déployés les centres de connaissances Microsoft) et de retour vers l’SBC à Francfort.</span><span class="sxs-lookup"><span data-stu-id="86ee5-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="86ee5-117">Le centre de donnees en Europe est sélectionné, car le SBC est en Europe et Microsoft utilise le centre de donne le plus proche de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="86ee5-118">Même si cette approche n’a aucun impact sur la qualité des appels en raison de l’optimisation du flux de trafic au sein de réseaux Microsoft dans la plupart des zones géographiques, le trafic comporte une boucle inutile.</span><span class="sxs-lookup"><span data-stu-id="86ee5-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="86ee5-119">Par le biais du **contournement du contenu multimédia**, le média est maintenu directement entre l’utilisateur teams et l’élément SBC, comme illustré dans le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="86ee5-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Affiche le signalement et le flux multimédia avec une dérivation multimédia](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="86ee5-121">La fonction de contournement de média utilise des protocoles appelés interactifs (ICE) sur le client teams et ICE Lite sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="86ee5-122">Ces protocoles permettent le routage direct pour utiliser le chemin multimédia le plus direct pour une qualité optimale.</span><span class="sxs-lookup"><span data-stu-id="86ee5-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="86ee5-123">ICE et ICE Lite sont des normes WebRTC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="86ee5-124">Pour plus d’informations sur ces protocoles, voir RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="86ee5-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="86ee5-125">Planification de flux d’appels et de pare-feu</span><span class="sxs-lookup"><span data-stu-id="86ee5-125">Call flow and firewall planning</span></span>

<span data-ttu-id="86ee5-126">Le flux d’appels et la planification de pare-feu varient selon que l’utilisateur a un accès direct à l’adresse IP publique de l’SBC et que l’utilisateur se trouve à l’intérieur ou à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="86ee5-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="86ee5-127">Flux d’appels si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="86ee5-128">Si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC, le flux des appels est le suivant :</span><span class="sxs-lookup"><span data-stu-id="86ee5-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="86ee5-129">Pour le contournement du média multimédia, le client teams doit avoir accès à l’adresse IP publique de la SBC même à partir d’un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="86ee5-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="86ee5-130">Si les médias directs ne sont pas souhaités, le média peut circuler via des relais de transport.</span><span class="sxs-lookup"><span data-stu-id="86ee5-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="86ee5-131">Il s’agit de la solution recommandée quand un utilisateur se trouve dans la même construction et/ou le même réseau que l’SBC : supprimer les composants Cloud Microsoft du chemin multimédia.</span><span class="sxs-lookup"><span data-stu-id="86ee5-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="86ee5-132">Le signalement est toujours transmis via le Cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="86ee5-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="86ee5-133">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est interne et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media) :</span><span class="sxs-lookup"><span data-stu-id="86ee5-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="86ee5-134">Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="86ee5-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="86ee5-135">Le signalement SIP accepte toujours les chemins 4 et 4 (selon la direction du trafic).</span><span class="sxs-lookup"><span data-stu-id="86ee5-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="86ee5-136">Le contenu multimédia reste local et prend le chemin 5b.</span><span class="sxs-lookup"><span data-stu-id="86ee5-136">Media stays local and takes path 5b.</span></span>

![Flux d’appels avec contournement de média activé, le client est interne](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="86ee5-138">Flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="86ee5-139">La description suivante décrit le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="86ee5-140">Par exemple, supposons que l’utilisateur est externe et que l’administrateur client a décidé de ne pas ouvrir l’adresse IP publique de l’SBC auprès de tout le monde sur Internet, mais uniquement dans Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="86ee5-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="86ee5-141">Les composants internes du trafic peuvent être acheminés par le biais des relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="86ee5-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="86ee5-142">Il s’agit de la configuration recommandée pour les utilisateurs en dehors du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="86ee5-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="86ee5-143">Dans ce cas, tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="86ee5-143">Consider the following:</span></span>

- <span data-ttu-id="86ee5-144">Des relais de transport d’équipes sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="86ee5-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="86ee5-145">Dans le cas d’une dérivation de média, Microsoft utilise une version de relais de transport qui nécessite l’ouverture des ports 50 000 à 59 999 entre les relais de transport d’équipe et l’SBC (à l’avenir, nous envisageons de migrer vers la version qui ne nécessite que les ports 3478 et 3479).</span><span class="sxs-lookup"><span data-stu-id="86ee5-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="86ee5-146">À des fins d’optimisation des éléments multimédias, Microsoft recommande l’ouverture de l’adresse IP publique de l’SBC uniquement aux relais de transport d’équipes.</span><span class="sxs-lookup"><span data-stu-id="86ee5-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="86ee5-147">Pour les clients en dehors du réseau d’entreprise, Microsoft recommande l’utilisation de relais de transport au lieu de joindre directement l’adresse IP publique de la SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="86ee5-148">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client ne peut pas accéder à l’adresse IP publique du contrôleur de bordure de session (le contenu multimédia est relayée par teams Relay Relay).</span><span class="sxs-lookup"><span data-stu-id="86ee5-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="86ee5-149">Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="86ee5-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="86ee5-150">Les médias sont relayés par le biais de chemins d’accès 3, 3, 4 et 4 '</span><span class="sxs-lookup"><span data-stu-id="86ee5-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="86ee5-152">Flux d’appels s’il se trouve hors du réseau et a accès à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="86ee5-153">Il ne s’agit pas d’une configuration recommandée, car elle ne tire aucunement parti des relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="86ee5-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="86ee5-154">Au lieu de cela, vous devez prendre en considération le scénario précédent dans lequel l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="86ee5-155">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media).</span><span class="sxs-lookup"><span data-stu-id="86ee5-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="86ee5-156">Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="86ee5-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="86ee5-157">Le signalement SIP accepte toujours les chemins 3 et 3 (selon la direction du trafic).</span><span class="sxs-lookup"><span data-stu-id="86ee5-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="86ee5-158">Flux multimédias utilisant Path 2.</span><span class="sxs-lookup"><span data-stu-id="86ee5-158">Media flows using path 2.</span></span>

![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="86ee5-160">Utilisation de processeurs multimédias et de relais de transport</span><span class="sxs-lookup"><span data-stu-id="86ee5-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="86ee5-161">Il existe deux composants dans le Cloud Microsoft qui peuvent se trouver dans le chemin d’accès au média : processeurs multimédias et relais de transport.</span><span class="sxs-lookup"><span data-stu-id="86ee5-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="86ee5-162">Le processeur de média est un composant public qui gère le contenu multimédia en cas de non-contournement et gère le contenu multimédia pour les applications vocales.</span><span class="sxs-lookup"><span data-stu-id="86ee5-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="86ee5-163">Les processeurs multimédias sont toujours dans le chemin d’accès pour les utilisateurs finaux sans ignorer les appels, mais jamais dans le chemin d’accès pour les appels ignorés.</span><span class="sxs-lookup"><span data-stu-id="86ee5-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="86ee5-164">Les processeurs multimédias sont toujours dans le chemin d’accès de toutes les applications vocales, telles que le parc d’appels, le standard automatique d’entreprise et les files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="86ee5-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="86ee5-165">Le relais de transport est utilisé pour se connecter au service de transport le plus proche pour envoyer du trafic en temps réel.</span><span class="sxs-lookup"><span data-stu-id="86ee5-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="86ee5-166">Les relais de transport peuvent être ou ne pas se trouver dans le chemin d’accès pour les appels passés (provenant de ou destinés aux utilisateurs finaux), en fonction de l’endroit où se trouve l’utilisateur et du mode de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="86ee5-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="86ee5-167">Le schéma suivant montre deux flux d’appels : l’un avec la dérivation multimédia est activée et le second avec contournement de média désactivé.</span><span class="sxs-lookup"><span data-stu-id="86ee5-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="86ee5-168">Remarque le diagramme ne montre que le trafic provenant de--ou destinés aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="86ee5-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="86ee5-169">La manette de média est un microservice dans Azure qui affecte des processeurs de média et crée des offres SDP.</span><span class="sxs-lookup"><span data-stu-id="86ee5-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="86ee5-170">Le proxy SIP est un composant qui convertit la signalisation HTTP REST utilisée dans teams pour SIP.</span><span class="sxs-lookup"><span data-stu-id="86ee5-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Flux d’appels avec contournement de média activé et désactivé](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="86ee5-172">Le tableau ci-dessous résume la différence entre les processeurs multimédias et les relais de transport.</span><span class="sxs-lookup"><span data-stu-id="86ee5-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="86ee5-173">Processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="86ee5-173">Media Processors</span></span> | <span data-ttu-id="86ee5-174">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="86ee5-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="86ee5-175">Chemin multimédia pour les appels sans contournement pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="86ee5-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="86ee5-176">Toujours</span><span class="sxs-lookup"><span data-stu-id="86ee5-176">Always</span></span> | <span data-ttu-id="86ee5-177">Interdire</span><span class="sxs-lookup"><span data-stu-id="86ee5-177">Never</span></span> | 
<span data-ttu-id="86ee5-178">Dans le chemin multimédia pour les appels ignorés pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="86ee5-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="86ee5-179">Interdire</span><span class="sxs-lookup"><span data-stu-id="86ee5-179">Never</span></span> | <span data-ttu-id="86ee5-180">Si le client ne peut pas accéder à l’SBC sur l’adresse IP publique</span><span class="sxs-lookup"><span data-stu-id="86ee5-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="86ee5-181">Dans le chemin multimédia pour les applications vocales</span><span class="sxs-lookup"><span data-stu-id="86ee5-181">In media path for voice applications</span></span> | <span data-ttu-id="86ee5-182">Toujours</span><span class="sxs-lookup"><span data-stu-id="86ee5-182">Always</span></span> | <span data-ttu-id="86ee5-183">Interdire</span><span class="sxs-lookup"><span data-stu-id="86ee5-183">Never</span></span> | 
<span data-ttu-id="86ee5-184">Peut faire un transcodage (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="86ee5-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="86ee5-185">Oui</span><span class="sxs-lookup"><span data-stu-id="86ee5-185">Yes</span></span> | <span data-ttu-id="86ee5-186">Non, ne relaye le son qu’entre les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="86ee5-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="86ee5-187">Nombre d’instances dans le monde et emplacement</span><span class="sxs-lookup"><span data-stu-id="86ee5-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="86ee5-188">8 au total : 2 aux États-Unis et en ouest ; 2 dans Amsterdam et Dublin ; 2 à Hong Kong et Singapour ; 2 au Japon</span><span class="sxs-lookup"><span data-stu-id="86ee5-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan</span></span>  | <span data-ttu-id="86ee5-189">Multiples</span><span class="sxs-lookup"><span data-stu-id="86ee5-189">Multiple</span></span>

<span data-ttu-id="86ee5-190">La plage d’adresses IP est 52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="86ee5-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="86ee5-191">\*Explication du transcodage :</span><span class="sxs-lookup"><span data-stu-id="86ee5-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="86ee5-192">Le processeur de média est B2BUA, ce qui signifie qu’il peut changer un codec (par exemple, soie du client teams vers MP et G. 711 entre MP et SBC).</span><span class="sxs-lookup"><span data-stu-id="86ee5-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="86ee5-193">Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n’est jamais changé entre le client et l’SBC, même si le trafic est transmis via des relais.</span><span class="sxs-lookup"><span data-stu-id="86ee5-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="86ee5-194">Utilisation de médias multimédias teams si Trunk est configuré pour la dérivation multimédia</span><span class="sxs-lookup"><span data-stu-id="86ee5-194">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="86ee5-195">Les processeurs multimédias teams sont toujours insérés dans le chemin multimédia dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="86ee5-195">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="86ee5-196">Appel transféré de 1:1 vers un appel de groupe</span><span class="sxs-lookup"><span data-stu-id="86ee5-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="86ee5-197">Appel vers un utilisateur d’équipes fédérées</span><span class="sxs-lookup"><span data-stu-id="86ee5-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="86ee5-198">Appel transféré ou transféré vers un utilisateur Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="86ee5-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="86ee5-199">Assurez-vous que votre SBC a accès aux processeurs multimédias et aux plages de relais de transport comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="86ee5-199">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="86ee5-200">Signalisation SIP : noms de domaine complets</span><span class="sxs-lookup"><span data-stu-id="86ee5-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="86ee5-201">Pour la signalisation SIP, les exigences en matière de nom de domaine complet et de pare-feu sont les mêmes que pour les cas sans contournement.</span><span class="sxs-lookup"><span data-stu-id="86ee5-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="86ee5-202">Le routage direct est fourni dans les environnements Office 365 suivants :</span><span class="sxs-lookup"><span data-stu-id="86ee5-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="86ee5-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-203">Office 365</span></span>
- <span data-ttu-id="86ee5-204">GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-204">Office 365 GCC</span></span>
- <span data-ttu-id="86ee5-205">Office 365 (GCC High)</span><span class="sxs-lookup"><span data-stu-id="86ee5-205">Office 365 GCC High</span></span>
- <span data-ttu-id="86ee5-206">Office 365 DoD en savoir plus sur les [environnements d’administration des États-Unis et d’office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.</span><span class="sxs-lookup"><span data-stu-id="86ee5-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="86ee5-207">Environnements Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="86ee5-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="86ee5-208">Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :</span><span class="sxs-lookup"><span data-stu-id="86ee5-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="86ee5-209">**SIP.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) global, doit d’abord être essayé.</span><span class="sxs-lookup"><span data-stu-id="86ee5-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="86ee5-210">Lorsque le SBC envoie une demande pour résoudre ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de noms principal Azure attribué à l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="86ee5-211">Cette affectation est basée sur les métriques de performance des centres de donnes et de proximité géographique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="86ee5-212">L’adresse IP renvoyée correspond au FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="86ee5-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="86ee5-213">**sip2.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) : il correspond à la deuxième région de priorité.</span><span class="sxs-lookup"><span data-stu-id="86ee5-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="86ee5-214">nom de domaine complet (FQDN) **sip3.pstnhub.Microsoft.com** : il correspond géographiquement à la troisième région de priorité.</span><span class="sxs-lookup"><span data-stu-id="86ee5-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="86ee5-215">Pour pouvoir effectuer les opérations suivantes, vous devez placer ces trois noms de domaine complets :</span><span class="sxs-lookup"><span data-stu-id="86ee5-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="86ee5-216">Offrir une plus meilleure version (moins chargée et la plus proche du centre de divertissement SBC attribué en interrogeant le premier nom de domaine complet).</span><span class="sxs-lookup"><span data-stu-id="86ee5-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="86ee5-217">Fournir un basculement lorsqu’une connexion à partir d’un SBC est établie à un centre de donne qui rencontre un problème temporaire.</span><span class="sxs-lookup"><span data-stu-id="86ee5-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="86ee5-218">Pour plus d’informations, consultez la section mécanisme de basculement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="86ee5-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="86ee5-219">Les noms de domaine complets **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**et **sip3.pstnhub.Microsoft.com** seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="86ee5-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="86ee5-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="86ee5-220">52.114.148.0</span></span>
- <span data-ttu-id="86ee5-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="86ee5-221">52.114.132.46</span></span>
- <span data-ttu-id="86ee5-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="86ee5-222">52.114.75.24</span></span>
- <span data-ttu-id="86ee5-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="86ee5-223">52.114.76.76</span></span>
- <span data-ttu-id="86ee5-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="86ee5-224">52.114.7.24</span></span>
- <span data-ttu-id="86ee5-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="86ee5-225">52.114.14.70</span></span>

<span data-ttu-id="86ee5-226">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="86ee5-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="86ee5-227">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet **SIP-All.pstnhub.Microsoft.com** est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="86ee5-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="86ee5-228">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="86ee5-229">Le point de connexion pour le routage direct est le nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="86ee5-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="86ee5-230">**SIP.pstnhub.DoD.Teams.Microsoft.us** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="86ee5-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="86ee5-231">Comme l’environnement Office 365 DoD existe uniquement dans les centres de données américains, il n’existe pas de noms de domaine complets secondaires et tertiaires.</span><span class="sxs-lookup"><span data-stu-id="86ee5-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="86ee5-232">Les noms de domaine complets (FQDN) – sip.pstnhub.dod.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="86ee5-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="86ee5-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="86ee5-233">52.127.64.33</span></span>
- <span data-ttu-id="86ee5-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="86ee5-234">52.127.68.34</span></span>

<span data-ttu-id="86ee5-235">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="86ee5-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="86ee5-236">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="86ee5-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="86ee5-237">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="86ee5-238">Le point de connexion pour le routage direct est le nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="86ee5-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="86ee5-239">**SIP.pstnhub.gov.Teams.Microsoft.us** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="86ee5-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="86ee5-240">Dans la mesure où l’environnement de grande qualité n’existe qu’aux centres de données américains, il n’y a pas de noms de domaine complets secondaires et tertiaires.</span><span class="sxs-lookup"><span data-stu-id="86ee5-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="86ee5-241">Les noms de domaine complets (FQDN) – sip.pstnhub.gov.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="86ee5-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="86ee5-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="86ee5-242">52.127.88.59</span></span>
- <span data-ttu-id="86ee5-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="86ee5-243">52.127.92.64</span></span>

<span data-ttu-id="86ee5-244">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="86ee5-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="86ee5-245">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="86ee5-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="86ee5-246">Signalisation SIP : ports</span><span class="sxs-lookup"><span data-stu-id="86ee5-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="86ee5-247">La configuration requise pour les ports est identique pour tous les environnements Office 365 dans lesquels le routage direct est disponible :</span><span class="sxs-lookup"><span data-stu-id="86ee5-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="86ee5-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-248">Office 365</span></span>
- <span data-ttu-id="86ee5-249">GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-249">Office 365 GCC</span></span>
- <span data-ttu-id="86ee5-250">Office 365 (GCC High)</span><span class="sxs-lookup"><span data-stu-id="86ee5-250">Office 365 GCC High</span></span>
- <span data-ttu-id="86ee5-251">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="86ee5-251">Office 365 DoD</span></span>

<span data-ttu-id="86ee5-252">Vous devez utiliser les ports suivants :</span><span class="sxs-lookup"><span data-stu-id="86ee5-252">You must use the following ports:</span></span>

| <span data-ttu-id="86ee5-253">Trafic</span><span class="sxs-lookup"><span data-stu-id="86ee5-253">Traffic</span></span> | <span data-ttu-id="86ee5-254">De</span><span class="sxs-lookup"><span data-stu-id="86ee5-254">From</span></span> | <span data-ttu-id="86ee5-255">À</span><span class="sxs-lookup"><span data-stu-id="86ee5-255">To</span></span> | <span data-ttu-id="86ee5-256">Port source</span><span class="sxs-lookup"><span data-stu-id="86ee5-256">Source port</span></span> | <span data-ttu-id="86ee5-257">Port de destination</span><span class="sxs-lookup"><span data-stu-id="86ee5-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="86ee5-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="86ee5-258">SIP/TLS</span></span>| <span data-ttu-id="86ee5-259">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="86ee5-259">SIP Proxy</span></span> | <span data-ttu-id="86ee5-260">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-260">SBC</span></span> | <span data-ttu-id="86ee5-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="86ee5-261">1024 - 65535</span></span> | <span data-ttu-id="86ee5-262">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-262">Defined on the SBC</span></span> |
| <span data-ttu-id="86ee5-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="86ee5-263">SIP/TLS</span></span> | <span data-ttu-id="86ee5-264">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-264">SBC</span></span> | <span data-ttu-id="86ee5-265">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="86ee5-265">SIP Proxy</span></span> | <span data-ttu-id="86ee5-266">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-266">Defined on the SBC</span></span> | <span data-ttu-id="86ee5-267">5061</span><span class="sxs-lookup"><span data-stu-id="86ee5-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="86ee5-268">Trafic multimédia : plages d’adresses IP et de ports</span><span class="sxs-lookup"><span data-stu-id="86ee5-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="86ee5-269">Le trafic multimédia entre le client SBC et teams est disponible si la connectivité directe est disponible ou par le biais de relais de transport d’équipes si le client ne peut pas accéder à l’SBC en utilisant l’adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="86ee5-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="86ee5-270">Configuration requise pour le trafic multimédia direct (entre le client teams et l’SBC)</span><span class="sxs-lookup"><span data-stu-id="86ee5-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="86ee5-271">Le client doit avoir accès aux ports spécifiés (voir table) sur l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="86ee5-272">Remarque : si le client se trouve dans un réseau interne, le média est transmis à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="86ee5-273">Vous pouvez configurer l’épinglage des cheveux sur votre appareil NAT pour que le trafic ne reste jamais sur l’équipement réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="86ee5-273">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="86ee5-274">Trafic</span><span class="sxs-lookup"><span data-stu-id="86ee5-274">Traffic</span></span> | <span data-ttu-id="86ee5-275">De</span><span class="sxs-lookup"><span data-stu-id="86ee5-275">From</span></span> | <span data-ttu-id="86ee5-276">À</span><span class="sxs-lookup"><span data-stu-id="86ee5-276">To</span></span> | <span data-ttu-id="86ee5-277">Port source</span><span class="sxs-lookup"><span data-stu-id="86ee5-277">Source port</span></span> | <span data-ttu-id="86ee5-278">Port de destination</span><span class="sxs-lookup"><span data-stu-id="86ee5-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="86ee5-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="86ee5-279">UDP/SRTP</span></span> | <span data-ttu-id="86ee5-280">Client</span><span class="sxs-lookup"><span data-stu-id="86ee5-280">Client</span></span> | <span data-ttu-id="86ee5-281">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-281">SBC</span></span> | <span data-ttu-id="86ee5-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="86ee5-282">50 000 – 50 019</span></span>  | <span data-ttu-id="86ee5-283">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-283">Defined on the SBC</span></span> |
| <span data-ttu-id="86ee5-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="86ee5-284">UDP/SRTP</span></span> | <span data-ttu-id="86ee5-285">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-285">SBC</span></span> | <span data-ttu-id="86ee5-286">Client</span><span class="sxs-lookup"><span data-stu-id="86ee5-286">Client</span></span> | <span data-ttu-id="86ee5-287">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-287">Defined on the SBC</span></span> | <span data-ttu-id="86ee5-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="86ee5-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="86ee5-289">Remarque : Si vous disposez d’un appareil réseau qui traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="86ee5-290">Configuration requise pour l’utilisation des relais de transport</span><span class="sxs-lookup"><span data-stu-id="86ee5-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="86ee5-291">Les relais de transport sont dans la même plage que les processeurs de médias (pour les cas de non-contournement) :</span><span class="sxs-lookup"><span data-stu-id="86ee5-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="86ee5-292">Environnements Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="86ee5-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="86ee5-293">-52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="86ee5-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="86ee5-294">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="86ee5-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="86ee5-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="86ee5-296">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="86ee5-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="86ee5-297">52.127.88.0/21</span></span>


<span data-ttu-id="86ee5-298">Le tableau suivant indique la plage de ports des relais de transport Teams (applicables à tous les environnements) :</span><span class="sxs-lookup"><span data-stu-id="86ee5-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="86ee5-299">Trafic</span><span class="sxs-lookup"><span data-stu-id="86ee5-299">Traffic</span></span> | <span data-ttu-id="86ee5-300">De</span><span class="sxs-lookup"><span data-stu-id="86ee5-300">From</span></span> | <span data-ttu-id="86ee5-301">À</span><span class="sxs-lookup"><span data-stu-id="86ee5-301">To</span></span> | <span data-ttu-id="86ee5-302">Port source</span><span class="sxs-lookup"><span data-stu-id="86ee5-302">Source port</span></span> | <span data-ttu-id="86ee5-303">Port de destination</span><span class="sxs-lookup"><span data-stu-id="86ee5-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="86ee5-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="86ee5-304">UDP/SRTP</span></span> | <span data-ttu-id="86ee5-305">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="86ee5-305">Transport Relay</span></span> | <span data-ttu-id="86ee5-306">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-306">SBC</span></span> | <span data-ttu-id="86ee5-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="86ee5-307">50 000 -59 999</span></span>    | <span data-ttu-id="86ee5-308">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-308">Defined on the SBC</span></span> |
| <span data-ttu-id="86ee5-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="86ee5-309">UDP/SRTP</span></span> | <span data-ttu-id="86ee5-310">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-310">SBC</span></span> | <span data-ttu-id="86ee5-311">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="86ee5-311">Transport Relay</span></span> | <span data-ttu-id="86ee5-312">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-312">Defined on the SBC</span></span> | <span data-ttu-id="86ee5-313">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="86ee5-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="86ee5-314">Remarque : Microsoft recommande au moins deux ports par appel simultané sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="86ee5-315">Microsoft étant doté de deux versions de relais de transport, les informations suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="86ee5-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="86ee5-316">v4, qui peut uniquement utiliser la plage de ports 50 000 à 59 999</span><span class="sxs-lookup"><span data-stu-id="86ee5-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="86ee5-317">V6, qui est compatible avec les ports 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="86ee5-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="86ee5-318">Pour le moment, le contournement de média ne prend en charge que la version v4 de relais de transport.</span><span class="sxs-lookup"><span data-stu-id="86ee5-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="86ee5-319">La prise en charge de la version V6 sera bientôt prise en charge.</span><span class="sxs-lookup"><span data-stu-id="86ee5-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="86ee5-320">Vous avez besoin d’ouvrir les ports 3478 et 3479 pour la transition.</span><span class="sxs-lookup"><span data-stu-id="86ee5-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="86ee5-321">Lorsque Microsoft présente la prise en charge des relais de transport V6 avec le contournement de média, vous n’aurez pas besoin de reconfigurer votre équipement réseau ou SBCs.</span><span class="sxs-lookup"><span data-stu-id="86ee5-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="86ee5-322">Configuration requise pour l’utilisation de processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="86ee5-322">Requirements for using media processors</span></span>

<span data-ttu-id="86ee5-323">Les processeurs multimédias sont toujours dans le chemin multimédia pour les applications vocales et pour les clients Web (par exemple, les clients teams dans Microsoft Edge ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="86ee5-323">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="86ee5-324">Les exigences sont les mêmes que pour la configuration sans contournement.</span><span class="sxs-lookup"><span data-stu-id="86ee5-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="86ee5-325">La plage d’adresses IP du trafic multimédia est</span><span class="sxs-lookup"><span data-stu-id="86ee5-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="86ee5-326">Environnements Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="86ee5-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="86ee5-327">-52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="86ee5-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="86ee5-328">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="86ee5-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="86ee5-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="86ee5-330">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="86ee5-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="86ee5-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="86ee5-331">52.127.88.0/21</span></span>

<span data-ttu-id="86ee5-332">Le tableau suivant indique la portée de port des processeurs multimédias (applicables à tous les environnements) :</span><span class="sxs-lookup"><span data-stu-id="86ee5-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="86ee5-333">Trafic</span><span class="sxs-lookup"><span data-stu-id="86ee5-333">Traffic</span></span> | <span data-ttu-id="86ee5-334">De</span><span class="sxs-lookup"><span data-stu-id="86ee5-334">From</span></span> | <span data-ttu-id="86ee5-335">À</span><span class="sxs-lookup"><span data-stu-id="86ee5-335">To</span></span> | <span data-ttu-id="86ee5-336">Port source</span><span class="sxs-lookup"><span data-stu-id="86ee5-336">Source port</span></span> | <span data-ttu-id="86ee5-337">Port de destination</span><span class="sxs-lookup"><span data-stu-id="86ee5-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="86ee5-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="86ee5-338">UDP/SRTP</span></span> | <span data-ttu-id="86ee5-339">Processeur de média</span><span class="sxs-lookup"><span data-stu-id="86ee5-339">Media Processor</span></span> | <span data-ttu-id="86ee5-340">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-340">SBC</span></span> | <span data-ttu-id="86ee5-341">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="86ee5-341">49 152 – 53 247</span></span>    | <span data-ttu-id="86ee5-342">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-342">Defined on the SBC</span></span> |
| <span data-ttu-id="86ee5-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="86ee5-343">UDP/SRTP</span></span> | <span data-ttu-id="86ee5-344">SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-344">SBC</span></span> | <span data-ttu-id="86ee5-345">Processeur de média</span><span class="sxs-lookup"><span data-stu-id="86ee5-345">Media Processor</span></span> | <span data-ttu-id="86ee5-346">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="86ee5-346">Defined on the SBC</span></span> | <span data-ttu-id="86ee5-347">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="86ee5-347">49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="86ee5-348">Configurer des Trunks séparés pour le contournement du contenu multimédia et l’exclusion de médias non multimédias</span><span class="sxs-lookup"><span data-stu-id="86ee5-348">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="86ee5-349">Si vous effectuez une migration vers une dérivation multimédia à partir d’une dérivation non multimédia et que vous voulez vérifier la fonctionnalité avant de migrer toute utilisation en dérivation de média, vous pouvez créer une stratégie de routage en ligne distincte et séparée pour diriger vers le Trunk de contournement du média et l’affecter à des éléments spécifiques. ont.</span><span class="sxs-lookup"><span data-stu-id="86ee5-349">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="86ee5-350">Étapes de configuration de haut niveau :</span><span class="sxs-lookup"><span data-stu-id="86ee5-350">High-level configuration steps:</span></span>

- <span data-ttu-id="86ee5-351">Identifiez les utilisateurs pour tester le contournement du contenu multimédia.</span><span class="sxs-lookup"><span data-stu-id="86ee5-351">Identify users to test media bypass.</span></span>

- <span data-ttu-id="86ee5-352">Créez deux Trunks distinctes avec différents noms de domaine complets : l’un est activé pour la dérivation multimédia ; l’autre non.</span><span class="sxs-lookup"><span data-stu-id="86ee5-352">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="86ee5-353">Les deux Trunks pointent vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="86ee5-353">Both trunks point to the same SBC.</span></span> <span data-ttu-id="86ee5-354">Les ports pour le signalement SIP TLS doivent être différents.</span><span class="sxs-lookup"><span data-stu-id="86ee5-354">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="86ee5-355">Les ports pour le média doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="86ee5-355">The ports for media must be the same.</span></span>

- <span data-ttu-id="86ee5-356">Créez une nouvelle stratégie de routage de la voix en ligne et attribuez la ligne de contournement du support multimédia aux itinéraires correspondants associés à l’utilisation RTC de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="86ee5-356">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="86ee5-357">Affectez la nouvelle stratégie de routage vocale en ligne aux utilisateurs que vous avez identifiés pour tester le contournement du contenu multimédia.</span><span class="sxs-lookup"><span data-stu-id="86ee5-357">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="86ee5-358">L’exemple ci-dessous illustre cette logique.</span><span class="sxs-lookup"><span data-stu-id="86ee5-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="86ee5-359">Ensemble d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="86ee5-359">Set of users</span></span> | <span data-ttu-id="86ee5-360">Nombre d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="86ee5-360">Number of users</span></span> | <span data-ttu-id="86ee5-361">Nom de domaine complet du Trunk affecté dans OVRP</span><span class="sxs-lookup"><span data-stu-id="86ee5-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="86ee5-362">Contournement de média activé</span><span class="sxs-lookup"><span data-stu-id="86ee5-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="86ee5-363">Utilisateurs dotés d’une ligne de contournement non multimédia</span><span class="sxs-lookup"><span data-stu-id="86ee5-363">Users with non-media bypass trunk</span></span> | <span data-ttu-id="86ee5-364">980</span><span class="sxs-lookup"><span data-stu-id="86ee5-364">980</span></span> | <span data-ttu-id="86ee5-365">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="86ee5-365">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="86ee5-366">true</span><span class="sxs-lookup"><span data-stu-id="86ee5-366">true</span></span>
<span data-ttu-id="86ee5-367">Utilisateurs avec relais multimédia</span><span class="sxs-lookup"><span data-stu-id="86ee5-367">Users with media bypass trunk</span></span> | <span data-ttu-id="86ee5-368">CX3-20</span><span class="sxs-lookup"><span data-stu-id="86ee5-368">20</span></span> | <span data-ttu-id="86ee5-369">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="86ee5-369">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="86ee5-370">false</span><span class="sxs-lookup"><span data-stu-id="86ee5-370">false</span></span> | 

<span data-ttu-id="86ee5-371">Les deux Trunks peuvent pointer sur la même SBC avec la même adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="86ee5-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="86ee5-372">Les ports de signalisation TLS de l’SBC doivent être différents, comme indiqué dans le schéma suivant.</span><span class="sxs-lookup"><span data-stu-id="86ee5-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="86ee5-373">Remarque vous devrez vous assurer que votre certificat prend en charge les deux Trunks.</span><span class="sxs-lookup"><span data-stu-id="86ee5-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="86ee5-374">Dans SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="86ee5-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Affiche les deux liaisons peuvent pointer sur le même SBC avec la même adresse IP publique](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="86ee5-376">Pour plus d’informations sur la configuration de deux lignes sur le même SBC, voir la documentation fournie par votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="86ee5-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="86ee5-377">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="86ee5-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="86ee5-378">Documentation relative au déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="86ee5-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="86ee5-379">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="86ee5-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="86ee5-380">Documentation sur le déploiement de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="86ee5-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="86ee5-381">Points de terminaison client pris en charge avec l’exclusion de média</span><span class="sxs-lookup"><span data-stu-id="86ee5-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="86ee5-382">La dérivation de média est prise en charge par tous les clients teams et les appareils de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="86ee5-382">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="86ee5-383">Pour tous les autres points de terminaison qui ne prennent pas en charge la dérivation multimédia, nous allons aborder l’appel sans contournement, même s’il a démarré en tant qu’appel de contournement.</span><span class="sxs-lookup"><span data-stu-id="86ee5-383">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="86ee5-384">Ce problème se produit automatiquement et ne nécessite aucune action de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="86ee5-384">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="86ee5-385">Cela inclut les téléphones 3PIP Skype entreprise et les clients Web teams qui prennent en charge l’appel de routage direct (nouveau Microsoft Edge basé sur chrome, Google Chrome et Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="86ee5-385">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="86ee5-386">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86ee5-386">See also</span></span>

[<span data-ttu-id="86ee5-387">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="86ee5-387">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



