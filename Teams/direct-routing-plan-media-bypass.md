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
description: Découvrez comment planifier la dérivation multimédia avec le routage direct du système téléphonique, qui vous permet de raccourcir le chemin du trafic multimédia et d’améliorer les performances.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a4f8995c3972da8fd2d060b7083edb61138b97ac
ms.sourcegitcommit: f63cf7fdde333a7cb36c39e9b6cdc33afd2b4601
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44338244"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="a1637-103">Planifier le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="a1637-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="a1637-104">À propos du contournement de média avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="a1637-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="a1637-105">La dérivation de médias vous permet d’abréger le chemin du trafic multimédia et de réduire le nombre de tronçons en transit pour de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="a1637-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="a1637-106">Par le biais du contournement du contenu multimédia, le contenu multimédia est maintenu entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via le système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="a1637-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="a1637-107">Pour configurer la dérivation multimédia, l’SBC et le client doivent se trouver dans le même emplacement ou réseau.</span><span class="sxs-lookup"><span data-stu-id="a1637-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="a1637-108">Vous pouvez contrôler la dérivation multimédia pour chaque SBC en utilisant la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** défini sur true ou false.</span><span class="sxs-lookup"><span data-stu-id="a1637-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="a1637-109">Cela ne signifie pas que le trafic multimédia restera dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1637-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="a1637-110">Cet article décrit le flux d’appels dans différents scénarios.</span><span class="sxs-lookup"><span data-stu-id="a1637-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="a1637-111">Les diagrammes ci-dessous montrent la différence de flux d’appels avec et sans dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="a1637-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="a1637-112">Sans dérivation multimédia, quand un client effectue ou reçoit un appel, la signalisation et le flux multimédia entre le SBC, le système Microsoft Phone et le client Teams, comme indiqué dans le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="a1637-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Affiche la signalisation et le flux multimédia sans contournement du support multimédia](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="a1637-114">Par exemple, supposons qu’un utilisateur se trouve dans le même bâtiment ou réseau que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="a1637-115">Par exemple, supposons qu’un utilisateur participant à un bâtiment à Francfort effectue un appel vers un utilisateur RTC :</span><span class="sxs-lookup"><span data-stu-id="a1637-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="a1637-116">**Sans dérivation multimédia**, le contenu multimédia sera transmis par l’intermédiaire d’Amsterdam ou de Dublin (sur lequel sont déployés les centres de connaissances Microsoft) et de retour vers l’SBC à Francfort.</span><span class="sxs-lookup"><span data-stu-id="a1637-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="a1637-117">Le centre de donnees en Europe est sélectionné, car le SBC est en Europe et Microsoft utilise le centre de donne le plus proche de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="a1637-118">Même si cette approche n’a aucun impact sur la qualité des appels en raison de l’optimisation du flux de trafic au sein de réseaux Microsoft dans la plupart des zones géographiques, le trafic comporte une boucle inutile.</span><span class="sxs-lookup"><span data-stu-id="a1637-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="a1637-119">Par le biais du **contournement du contenu multimédia**, le média est maintenu directement entre l’utilisateur teams et l’élément SBC, comme illustré dans le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="a1637-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Affiche le signalement et le flux multimédia avec une dérivation multimédia](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="a1637-121">La fonction de contournement de média utilise des protocoles appelés interactifs (ICE) sur le client teams et ICE Lite sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="a1637-122">Ces protocoles permettent le routage direct pour utiliser le chemin multimédia le plus direct pour une qualité optimale.</span><span class="sxs-lookup"><span data-stu-id="a1637-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="a1637-123">ICE et ICE Lite sont des normes WebRTC.</span><span class="sxs-lookup"><span data-stu-id="a1637-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="a1637-124">Pour plus d’informations sur ces protocoles, voir RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="a1637-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="a1637-125">Planification de flux d’appels et de pare-feu</span><span class="sxs-lookup"><span data-stu-id="a1637-125">Call flow and firewall planning</span></span>

<span data-ttu-id="a1637-126">Le flux d’appels et la planification de pare-feu varient selon que l’utilisateur a un accès direct à l’adresse IP publique de l’SBC et que l’utilisateur se trouve à l’intérieur ou à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="a1637-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a1637-127">Flux d’appels si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="a1637-128">Si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC, le flux des appels est le suivant :</span><span class="sxs-lookup"><span data-stu-id="a1637-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="a1637-129">Pour le contournement du média multimédia, le client teams doit avoir accès à l’adresse IP publique de la SBC même à partir d’un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="a1637-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="a1637-130">Si les médias directs ne sont pas souhaités, le média peut circuler via des relais de transport.</span><span class="sxs-lookup"><span data-stu-id="a1637-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="a1637-131">Il s’agit de la solution recommandée quand un utilisateur se trouve dans la même construction et/ou le même réseau que l’SBC : supprimer les composants Cloud Microsoft du chemin multimédia.</span><span class="sxs-lookup"><span data-stu-id="a1637-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="a1637-132">Le signalement est toujours transmis via le Cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1637-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="a1637-133">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est interne et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media) :</span><span class="sxs-lookup"><span data-stu-id="a1637-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="a1637-134">Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="a1637-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="a1637-135">Le signalement SIP accepte toujours les chemins 4 et 4 (selon la direction du trafic).</span><span class="sxs-lookup"><span data-stu-id="a1637-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="a1637-136">Le contenu multimédia reste local et prend le chemin 5b.</span><span class="sxs-lookup"><span data-stu-id="a1637-136">Media stays local and takes path 5b.</span></span>

![Flux d’appels avec contournement de média activé, le client est interne](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a1637-138">Flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="a1637-139">La description suivante décrit le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a1637-140">Par exemple, supposons que l’utilisateur est externe et que l’administrateur client a décidé de ne pas ouvrir l’adresse IP publique de l’SBC auprès de tout le monde sur Internet, mais uniquement dans Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="a1637-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="a1637-141">Les composants internes du trafic peuvent être acheminés par le biais des relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="a1637-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="a1637-142">Il s’agit de la configuration recommandée pour les utilisateurs en dehors du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1637-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="a1637-143">Vous devez tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a1637-143">Consider the following:</span></span>

- <span data-ttu-id="a1637-144">Des relais de transport d’équipes sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="a1637-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="a1637-145">Dans le cas d’une dérivation de média, Microsoft utilise une version de relais de transport qui nécessite l’ouverture des ports 50 000 à 59 999 entre les relais de transport d’équipe et l’SBC (à l’avenir, nous envisageons de migrer vers la version qui ne nécessite que les ports 3478 et 3479).</span><span class="sxs-lookup"><span data-stu-id="a1637-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="a1637-146">À des fins d’optimisation des éléments multimédias, Microsoft recommande l’ouverture de l’adresse IP publique de l’SBC uniquement aux relais de transport d’équipes.</span><span class="sxs-lookup"><span data-stu-id="a1637-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="a1637-147">Pour les clients en dehors du réseau d’entreprise, Microsoft recommande l’utilisation de relais de transport au lieu de joindre directement l’adresse IP publique de la SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="a1637-148">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client ne peut pas accéder à l’adresse IP publique du contrôleur de bordure de session (le contenu multimédia est relayée par teams Relay Relay).</span><span class="sxs-lookup"><span data-stu-id="a1637-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="a1637-149">Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="a1637-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="a1637-150">Les médias sont relayés par le biais de chemins d’accès 3, 3, 4 et 4 '</span><span class="sxs-lookup"><span data-stu-id="a1637-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="a1637-152">Flux d’appels s’il se trouve hors du réseau et a accès à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="a1637-153">Il ne s’agit pas d’une configuration recommandée, car elle ne tire aucunement parti des relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="a1637-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="a1637-154">Au lieu de cela, vous devez prendre en considération le scénario précédent dans lequel l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a1637-155">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media).</span><span class="sxs-lookup"><span data-stu-id="a1637-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="a1637-156">Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="a1637-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="a1637-157">Le signalement SIP accepte toujours les chemins 3 et 3 (selon la direction du trafic).</span><span class="sxs-lookup"><span data-stu-id="a1637-157">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="a1637-158">Flux multimédias utilisant Path 2.</span><span class="sxs-lookup"><span data-stu-id="a1637-158">Media flows using path 2.</span></span>

![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="a1637-160">Utilisation de processeurs multimédias et de relais de transport</span><span class="sxs-lookup"><span data-stu-id="a1637-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="a1637-161">Il existe deux composants dans le Cloud Microsoft qui peuvent se trouver dans le chemin d’accès au média : processeurs multimédias et relais de transport.</span><span class="sxs-lookup"><span data-stu-id="a1637-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="a1637-162">Le processeur de média est un composant public qui gère le contenu multimédia en cas de non-contournement et gère le contenu multimédia pour les applications vocales.</span><span class="sxs-lookup"><span data-stu-id="a1637-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="a1637-163">Les processeurs multimédias sont toujours dans le chemin d’accès pour les utilisateurs finaux sans ignorer les appels, mais jamais dans le chemin d’accès pour les appels ignorés.</span><span class="sxs-lookup"><span data-stu-id="a1637-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="a1637-164">Les processeurs multimédias sont toujours dans le chemin d’accès de toutes les applications vocales, telles que le parc d’appels, le standard automatique d’entreprise et les files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="a1637-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="a1637-165">Le relais de transport est utilisé pour se connecter au service de transport le plus proche pour envoyer du trafic en temps réel.</span><span class="sxs-lookup"><span data-stu-id="a1637-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="a1637-166">Les relais de transport peuvent être ou ne pas se trouver dans le chemin d’accès pour les appels passés (provenant de ou destinés aux utilisateurs finaux), en fonction de l’endroit où se trouve l’utilisateur et du mode de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="a1637-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="a1637-167">Le schéma suivant montre deux flux d’appels : l’un avec la dérivation multimédia est activée et le second avec contournement de média désactivé.</span><span class="sxs-lookup"><span data-stu-id="a1637-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="a1637-168">Remarque le diagramme ne montre que le trafic provenant de--ou destinés aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="a1637-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="a1637-169">La manette de média est un microservice dans Azure qui affecte des processeurs de média et crée des offres SDP.</span><span class="sxs-lookup"><span data-stu-id="a1637-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="a1637-170">Le proxy SIP est un composant qui convertit la signalisation HTTP REST utilisée dans teams pour SIP.</span><span class="sxs-lookup"><span data-stu-id="a1637-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Flux d’appels avec contournement de média activé et désactivé](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="a1637-172">Le tableau ci-dessous résume la différence entre les processeurs multimédias et les relais de transport.</span><span class="sxs-lookup"><span data-stu-id="a1637-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="a1637-173">Processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="a1637-173">Media Processors</span></span> | <span data-ttu-id="a1637-174">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="a1637-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="a1637-175">Chemin multimédia pour les appels sans contournement pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="a1637-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="a1637-176">Toujours</span><span class="sxs-lookup"><span data-stu-id="a1637-176">Always</span></span> | <span data-ttu-id="a1637-177">Interdire</span><span class="sxs-lookup"><span data-stu-id="a1637-177">Never</span></span> | 
<span data-ttu-id="a1637-178">Dans le chemin multimédia pour les appels ignorés pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="a1637-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="a1637-179">Interdire</span><span class="sxs-lookup"><span data-stu-id="a1637-179">Never</span></span> | <span data-ttu-id="a1637-180">Si le client ne peut pas accéder à l’SBC sur l’adresse IP publique</span><span class="sxs-lookup"><span data-stu-id="a1637-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="a1637-181">Dans le chemin multimédia pour les applications vocales</span><span class="sxs-lookup"><span data-stu-id="a1637-181">In media path for voice applications</span></span> | <span data-ttu-id="a1637-182">Toujours</span><span class="sxs-lookup"><span data-stu-id="a1637-182">Always</span></span> | <span data-ttu-id="a1637-183">Interdire</span><span class="sxs-lookup"><span data-stu-id="a1637-183">Never</span></span> | 
<span data-ttu-id="a1637-184">Peut faire un transcodage (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="a1637-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="a1637-185">Oui</span><span class="sxs-lookup"><span data-stu-id="a1637-185">Yes</span></span> | <span data-ttu-id="a1637-186">Non, ne relaye le son qu’entre les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="a1637-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="a1637-187">Nombre d’instances dans le monde et emplacement</span><span class="sxs-lookup"><span data-stu-id="a1637-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="a1637-188">8 au total : 2 aux États-Unis et en ouest ; 2 dans Amsterdam et Dublin ; 2 à Hong Kong et Singapour ; 2 au Japon</span><span class="sxs-lookup"><span data-stu-id="a1637-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan</span></span>  | <span data-ttu-id="a1637-189">Multiples</span><span class="sxs-lookup"><span data-stu-id="a1637-189">Multiple</span></span>

<span data-ttu-id="a1637-190">Les plages d’adresses IP sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1637-190">The IP ranges are:</span></span>
- <span data-ttu-id="a1637-191">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="a1637-191">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="a1637-192">52.120.0.0/14 (adresses IP de 52.120.0.1 à 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="a1637-192">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="a1637-193">\*Explication du transcodage :</span><span class="sxs-lookup"><span data-stu-id="a1637-193">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="a1637-194">Le processeur de média est B2BUA, ce qui signifie qu’il peut changer un codec (par exemple, soie du client teams vers MP et G. 711 entre MP et SBC).</span><span class="sxs-lookup"><span data-stu-id="a1637-194">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="a1637-195">Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n’est jamais changé entre le client et l’SBC, même si le trafic est transmis via des relais.</span><span class="sxs-lookup"><span data-stu-id="a1637-195">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="a1637-196">Utilisation de médias multimédias teams si Trunk est configuré pour la dérivation multimédia</span><span class="sxs-lookup"><span data-stu-id="a1637-196">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="a1637-197">Les processeurs multimédias teams sont toujours insérés dans le chemin multimédia dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="a1637-197">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="a1637-198">Appel transféré de 1:1 vers un appel de groupe</span><span class="sxs-lookup"><span data-stu-id="a1637-198">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="a1637-199">Appel vers un utilisateur d’équipes fédérées</span><span class="sxs-lookup"><span data-stu-id="a1637-199">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="a1637-200">Appel transféré ou transféré vers un utilisateur Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a1637-200">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="a1637-201">Assurez-vous que votre SBC a accès aux processeurs multimédias et aux plages de relais de transport comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a1637-201">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="a1637-202">Signalisation SIP : noms de domaine complets</span><span class="sxs-lookup"><span data-stu-id="a1637-202">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="a1637-203">Pour la signalisation SIP, les exigences en matière de nom de domaine complet et de pare-feu sont les mêmes que pour les cas sans contournement.</span><span class="sxs-lookup"><span data-stu-id="a1637-203">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="a1637-204">Le routage direct est fourni dans les environnements Office 365 suivants :</span><span class="sxs-lookup"><span data-stu-id="a1637-204">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="a1637-205">Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-205">Office 365</span></span>
- <span data-ttu-id="a1637-206">GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-206">Office 365 GCC</span></span>
- <span data-ttu-id="a1637-207">Office 365 (GCC High)</span><span class="sxs-lookup"><span data-stu-id="a1637-207">Office 365 GCC High</span></span>
- <span data-ttu-id="a1637-208">Office 365 DoD en savoir plus sur les [environnements d’administration des États-Unis et d’office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.</span><span class="sxs-lookup"><span data-stu-id="a1637-208">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a1637-209">Environnements Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a1637-209">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="a1637-210">Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :</span><span class="sxs-lookup"><span data-stu-id="a1637-210">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="a1637-211">**SIP.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) global, doit d’abord être essayé.</span><span class="sxs-lookup"><span data-stu-id="a1637-211">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="a1637-212">Lorsque le SBC envoie une demande pour résoudre ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de noms principal Azure attribué à l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-212">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="a1637-213">Cette affectation est basée sur les métriques de performance des centres de donnes et de proximité géographique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-213">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="a1637-214">L’adresse IP renvoyée correspond au FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="a1637-214">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="a1637-215">**sip2.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) : il correspond à la deuxième région de priorité.</span><span class="sxs-lookup"><span data-stu-id="a1637-215">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="a1637-216">nom de domaine complet (FQDN) **sip3.pstnhub.Microsoft.com** : il correspond géographiquement à la troisième région de priorité.</span><span class="sxs-lookup"><span data-stu-id="a1637-216">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="a1637-217">Pour pouvoir effectuer les opérations suivantes, vous devez placer ces trois noms de domaine complets :</span><span class="sxs-lookup"><span data-stu-id="a1637-217">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="a1637-218">Offrir une plus meilleure version (moins chargée et la plus proche du centre de divertissement SBC attribué en interrogeant le premier nom de domaine complet).</span><span class="sxs-lookup"><span data-stu-id="a1637-218">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="a1637-219">Fournir un basculement lorsqu’une connexion à partir d’un SBC est établie à un centre de donne qui rencontre un problème temporaire.</span><span class="sxs-lookup"><span data-stu-id="a1637-219">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="a1637-220">Pour plus d’informations, consultez la section mécanisme de basculement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a1637-220">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="a1637-221">Les noms de domaine complets **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**et **sip3.pstnhub.Microsoft.com** seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1637-221">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="a1637-222">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="a1637-222">52.114.148.0</span></span>
- <span data-ttu-id="a1637-223">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="a1637-223">52.114.132.46</span></span>
- <span data-ttu-id="a1637-224">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="a1637-224">52.114.75.24</span></span>
- <span data-ttu-id="a1637-225">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="a1637-225">52.114.76.76</span></span>
- <span data-ttu-id="a1637-226">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="a1637-226">52.114.7.24</span></span>
- <span data-ttu-id="a1637-227">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="a1637-227">52.114.14.70</span></span>

<span data-ttu-id="a1637-228">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="a1637-228">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="a1637-229">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet **SIP-All.pstnhub.Microsoft.com** est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="a1637-229">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a1637-230">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-230">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="a1637-231">Le point de connexion pour le routage direct est le nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="a1637-231">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a1637-232">**SIP.pstnhub.DoD.Teams.Microsoft.us** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="a1637-232">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a1637-233">Comme l’environnement Office 365 DoD existe uniquement dans les centres de données américains, il n’existe pas de noms de domaine complets secondaires et tertiaires.</span><span class="sxs-lookup"><span data-stu-id="a1637-233">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a1637-234">Les noms de domaine complets (FQDN) – sip.pstnhub.dod.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1637-234">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="a1637-235">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="a1637-235">52.127.64.33</span></span>
- <span data-ttu-id="a1637-236">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="a1637-236">52.127.68.34</span></span>

<span data-ttu-id="a1637-237">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="a1637-237">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a1637-238">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="a1637-238">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a1637-239">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-239">Office 365 GCC High environment</span></span>

<span data-ttu-id="a1637-240">Le point de connexion pour le routage direct est le nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="a1637-240">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a1637-241">**SIP.pstnhub.gov.Teams.Microsoft.us** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="a1637-241">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a1637-242">Dans la mesure où l’environnement de grande qualité n’existe qu’aux centres de données américains, il n’y a pas de noms de domaine complets secondaires et tertiaires.</span><span class="sxs-lookup"><span data-stu-id="a1637-242">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a1637-243">Les noms de domaine complets (FQDN) – sip.pstnhub.gov.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1637-243">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="a1637-244">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="a1637-244">52.127.88.59</span></span>
- <span data-ttu-id="a1637-245">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="a1637-245">52.127.92.64</span></span>

<span data-ttu-id="a1637-246">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="a1637-246">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a1637-247">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="a1637-247">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="a1637-248">Signalisation SIP : ports</span><span class="sxs-lookup"><span data-stu-id="a1637-248">SIP Signaling: Ports</span></span>

<span data-ttu-id="a1637-249">La configuration requise pour les ports est identique pour tous les environnements Office 365 dans lesquels le routage direct est disponible :</span><span class="sxs-lookup"><span data-stu-id="a1637-249">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="a1637-250">Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-250">Office 365</span></span>
- <span data-ttu-id="a1637-251">GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-251">Office 365 GCC</span></span>
- <span data-ttu-id="a1637-252">Office 365 (GCC High)</span><span class="sxs-lookup"><span data-stu-id="a1637-252">Office 365 GCC High</span></span>
- <span data-ttu-id="a1637-253">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="a1637-253">Office 365 DoD</span></span>

<span data-ttu-id="a1637-254">Vous devez utiliser les ports suivants :</span><span class="sxs-lookup"><span data-stu-id="a1637-254">You must use the following ports:</span></span>

| <span data-ttu-id="a1637-255">Trafic</span><span class="sxs-lookup"><span data-stu-id="a1637-255">Traffic</span></span> | <span data-ttu-id="a1637-256">De</span><span class="sxs-lookup"><span data-stu-id="a1637-256">From</span></span> | <span data-ttu-id="a1637-257">À</span><span class="sxs-lookup"><span data-stu-id="a1637-257">To</span></span> | <span data-ttu-id="a1637-258">Port source</span><span class="sxs-lookup"><span data-stu-id="a1637-258">Source port</span></span> | <span data-ttu-id="a1637-259">Port de destination</span><span class="sxs-lookup"><span data-stu-id="a1637-259">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a1637-260">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a1637-260">SIP/TLS</span></span>| <span data-ttu-id="a1637-261">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="a1637-261">SIP Proxy</span></span> | <span data-ttu-id="a1637-262">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-262">SBC</span></span> | <span data-ttu-id="a1637-263">1024-65535</span><span class="sxs-lookup"><span data-stu-id="a1637-263">1024 - 65535</span></span> | <span data-ttu-id="a1637-264">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-264">Defined on the SBC</span></span> |
| <span data-ttu-id="a1637-265">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a1637-265">SIP/TLS</span></span> | <span data-ttu-id="a1637-266">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-266">SBC</span></span> | <span data-ttu-id="a1637-267">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="a1637-267">SIP Proxy</span></span> | <span data-ttu-id="a1637-268">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-268">Defined on the SBC</span></span> | <span data-ttu-id="a1637-269">5061</span><span class="sxs-lookup"><span data-stu-id="a1637-269">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="a1637-270">Trafic multimédia : plages d’adresses IP et de ports</span><span class="sxs-lookup"><span data-stu-id="a1637-270">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="a1637-271">Le trafic multimédia entre le client SBC et teams est disponible si la connectivité directe est disponible ou par le biais de relais de transport d’équipes si le client ne peut pas accéder à l’SBC en utilisant l’adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="a1637-271">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="a1637-272">Configuration requise pour le trafic multimédia direct (entre le client teams et l’SBC)</span><span class="sxs-lookup"><span data-stu-id="a1637-272">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="a1637-273">Le client doit avoir accès aux ports spécifiés (voir table) sur l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-273">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="a1637-274">Remarque : si le client se trouve dans un réseau interne, le média est transmis à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-274">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="a1637-275">Vous pouvez configurer l’épinglage des cheveux sur votre appareil NAT pour que le trafic ne reste jamais sur l’équipement réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1637-275">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="a1637-276">Trafic</span><span class="sxs-lookup"><span data-stu-id="a1637-276">Traffic</span></span> | <span data-ttu-id="a1637-277">De</span><span class="sxs-lookup"><span data-stu-id="a1637-277">From</span></span> | <span data-ttu-id="a1637-278">À</span><span class="sxs-lookup"><span data-stu-id="a1637-278">To</span></span> | <span data-ttu-id="a1637-279">Port source</span><span class="sxs-lookup"><span data-stu-id="a1637-279">Source port</span></span> | <span data-ttu-id="a1637-280">Port de destination</span><span class="sxs-lookup"><span data-stu-id="a1637-280">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a1637-281">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a1637-281">UDP/SRTP</span></span> | <span data-ttu-id="a1637-282">Client</span><span class="sxs-lookup"><span data-stu-id="a1637-282">Client</span></span> | <span data-ttu-id="a1637-283">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-283">SBC</span></span> | <span data-ttu-id="a1637-284">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="a1637-284">50 000 – 50 019</span></span>  | <span data-ttu-id="a1637-285">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-285">Defined on the SBC</span></span> |
| <span data-ttu-id="a1637-286">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a1637-286">UDP/SRTP</span></span> | <span data-ttu-id="a1637-287">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-287">SBC</span></span> | <span data-ttu-id="a1637-288">Client</span><span class="sxs-lookup"><span data-stu-id="a1637-288">Client</span></span> | <span data-ttu-id="a1637-289">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-289">Defined on the SBC</span></span> | <span data-ttu-id="a1637-290">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="a1637-290">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="a1637-291">Si vous disposez d’un appareil réseau qui traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-291">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="a1637-292">Configuration requise pour l’utilisation des relais de transport</span><span class="sxs-lookup"><span data-stu-id="a1637-292">Requirements for using Transport Relays</span></span>

<span data-ttu-id="a1637-293">Les relais de transport sont dans la même plage que les processeurs de médias (pour les cas de non-contournement) :</span><span class="sxs-lookup"><span data-stu-id="a1637-293">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a1637-294">Environnements Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a1637-294">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="a1637-295">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="a1637-295">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a1637-296">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-296">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a1637-297">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a1637-297">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a1637-298">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-298">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a1637-299">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a1637-299">52.127.88.0/21</span></span>


<span data-ttu-id="a1637-300">Le tableau suivant indique la plage de ports des relais de transport Teams (applicables à tous les environnements) :</span><span class="sxs-lookup"><span data-stu-id="a1637-300">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="a1637-301">Trafic</span><span class="sxs-lookup"><span data-stu-id="a1637-301">Traffic</span></span> | <span data-ttu-id="a1637-302">De</span><span class="sxs-lookup"><span data-stu-id="a1637-302">From</span></span> | <span data-ttu-id="a1637-303">À</span><span class="sxs-lookup"><span data-stu-id="a1637-303">To</span></span> | <span data-ttu-id="a1637-304">Port source</span><span class="sxs-lookup"><span data-stu-id="a1637-304">Source port</span></span> | <span data-ttu-id="a1637-305">Port de destination</span><span class="sxs-lookup"><span data-stu-id="a1637-305">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a1637-306">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a1637-306">UDP/SRTP</span></span> | <span data-ttu-id="a1637-307">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="a1637-307">Transport Relay</span></span> | <span data-ttu-id="a1637-308">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-308">SBC</span></span> | <span data-ttu-id="a1637-309">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="a1637-309">50 000 -59 999</span></span>    | <span data-ttu-id="a1637-310">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-310">Defined on the SBC</span></span> |
| <span data-ttu-id="a1637-311">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a1637-311">UDP/SRTP</span></span> | <span data-ttu-id="a1637-312">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-312">SBC</span></span> | <span data-ttu-id="a1637-313">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="a1637-313">Transport Relay</span></span> | <span data-ttu-id="a1637-314">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-314">Defined on the SBC</span></span> | <span data-ttu-id="a1637-315">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="a1637-315">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="a1637-316">Microsoft recommande au moins deux ports par appel simultané sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-316">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="a1637-317">Microsoft étant doté de deux versions de relais de transport, les informations suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="a1637-317">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="a1637-318">v4, qui peut uniquement utiliser la plage de ports 50 000 à 59 999</span><span class="sxs-lookup"><span data-stu-id="a1637-318">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="a1637-319">V6, qui est compatible avec les ports 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="a1637-319">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="a1637-320">Pour le moment, le contournement de média ne prend en charge que la version v4 de relais de transport.</span><span class="sxs-lookup"><span data-stu-id="a1637-320">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="a1637-321">La prise en charge de la version V6 sera bientôt prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1637-321">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="a1637-322">Vous avez besoin d’ouvrir les ports 3478 et 3479 pour la transition.</span><span class="sxs-lookup"><span data-stu-id="a1637-322">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="a1637-323">Lorsque Microsoft présente la prise en charge des relais de transport V6 avec le contournement de média, vous n’aurez pas besoin de reconfigurer votre équipement réseau ou SBCs.</span><span class="sxs-lookup"><span data-stu-id="a1637-323">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="a1637-324">Configuration requise pour l’utilisation de processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="a1637-324">Requirements for using media processors</span></span>

<span data-ttu-id="a1637-325">Les processeurs multimédias sont toujours dans le chemin multimédia pour les applications vocales et pour les clients Web (par exemple, les clients teams dans Microsoft Edge ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="a1637-325">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="a1637-326">Les exigences sont les mêmes que pour la configuration sans contournement.</span><span class="sxs-lookup"><span data-stu-id="a1637-326">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="a1637-327">La plage d’adresses IP du trafic multimédia est</span><span class="sxs-lookup"><span data-stu-id="a1637-327">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a1637-328">Environnements Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a1637-328">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="a1637-329">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="a1637-329">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a1637-330">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-330">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a1637-331">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a1637-331">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a1637-332">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a1637-332">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a1637-333">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a1637-333">52.127.88.0/21</span></span>

<span data-ttu-id="a1637-334">Le tableau suivant indique la portée de port des processeurs multimédias (applicables à tous les environnements) :</span><span class="sxs-lookup"><span data-stu-id="a1637-334">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="a1637-335">Trafic</span><span class="sxs-lookup"><span data-stu-id="a1637-335">Traffic</span></span> | <span data-ttu-id="a1637-336">De</span><span class="sxs-lookup"><span data-stu-id="a1637-336">From</span></span> | <span data-ttu-id="a1637-337">À</span><span class="sxs-lookup"><span data-stu-id="a1637-337">To</span></span> | <span data-ttu-id="a1637-338">Port source</span><span class="sxs-lookup"><span data-stu-id="a1637-338">Source port</span></span> | <span data-ttu-id="a1637-339">Port de destination</span><span class="sxs-lookup"><span data-stu-id="a1637-339">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a1637-340">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a1637-340">UDP/SRTP</span></span> | <span data-ttu-id="a1637-341">Processeur de média</span><span class="sxs-lookup"><span data-stu-id="a1637-341">Media Processor</span></span> | <span data-ttu-id="a1637-342">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-342">SBC</span></span> | <span data-ttu-id="a1637-343">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a1637-343">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="a1637-344">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-344">Defined on the SBC</span></span> |
| <span data-ttu-id="a1637-345">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a1637-345">UDP/SRTP</span></span> | <span data-ttu-id="a1637-346">SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-346">SBC</span></span> | <span data-ttu-id="a1637-347">Processeur de média</span><span class="sxs-lookup"><span data-stu-id="a1637-347">Media Processor</span></span> | <span data-ttu-id="a1637-348">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="a1637-348">Defined on the SBC</span></span> | <span data-ttu-id="a1637-349">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a1637-349">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="a1637-350">Configurer des Trunks séparés pour le contournement du contenu multimédia et l’exclusion de médias non multimédias</span><span class="sxs-lookup"><span data-stu-id="a1637-350">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="a1637-351">Si vous effectuez une migration vers une dérivation multimédia à partir d’une dérivation non multimédia et que vous voulez confirmer la fonctionnalité avant de migrer toute utilisation en dérivation du support multimédia, vous pouvez créer une stratégie de routage et une stratégie d’acheminement en ligne distinctes pour diriger vers le Trunk de contournement du média et l’affecter à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a1637-351">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="a1637-352">Étapes de configuration de haut niveau :</span><span class="sxs-lookup"><span data-stu-id="a1637-352">High-level configuration steps:</span></span>

- <span data-ttu-id="a1637-353">Identifiez les utilisateurs pour tester le contournement du contenu multimédia.</span><span class="sxs-lookup"><span data-stu-id="a1637-353">Identify users to test media bypass.</span></span>

- <span data-ttu-id="a1637-354">Créez deux Trunks distinctes avec différents noms de domaine complets : l’un est activé pour la dérivation multimédia ; l’autre non.</span><span class="sxs-lookup"><span data-stu-id="a1637-354">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="a1637-355">Les deux Trunks pointent vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="a1637-355">Both trunks point to the same SBC.</span></span> <span data-ttu-id="a1637-356">Les ports pour le signalement SIP TLS doivent être différents.</span><span class="sxs-lookup"><span data-stu-id="a1637-356">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="a1637-357">Les ports pour le média doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="a1637-357">The ports for media must be the same.</span></span>

- <span data-ttu-id="a1637-358">Créez une nouvelle stratégie de routage de la voix en ligne et attribuez la ligne de contournement du support multimédia aux itinéraires correspondants associés à l’utilisation RTC de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="a1637-358">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="a1637-359">Affectez la nouvelle stratégie de routage vocale en ligne aux utilisateurs que vous avez identifiés pour tester le contournement du contenu multimédia.</span><span class="sxs-lookup"><span data-stu-id="a1637-359">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="a1637-360">L’exemple ci-dessous illustre cette logique.</span><span class="sxs-lookup"><span data-stu-id="a1637-360">The example below illustrates this logic.</span></span>

| <span data-ttu-id="a1637-361">Ensemble d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a1637-361">Set of users</span></span> | <span data-ttu-id="a1637-362">Nombre d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a1637-362">Number of users</span></span> | <span data-ttu-id="a1637-363">Nom de domaine complet du Trunk affecté dans OVRP</span><span class="sxs-lookup"><span data-stu-id="a1637-363">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="a1637-364">Contournement de média activé</span><span class="sxs-lookup"><span data-stu-id="a1637-364">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="a1637-365">Utilisateurs dotés d’une ligne de contournement non multimédia</span><span class="sxs-lookup"><span data-stu-id="a1637-365">Users with non-media bypass trunk</span></span> | <span data-ttu-id="a1637-366">980</span><span class="sxs-lookup"><span data-stu-id="a1637-366">980</span></span> | <span data-ttu-id="a1637-367">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="a1637-367">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="a1637-368">true</span><span class="sxs-lookup"><span data-stu-id="a1637-368">true</span></span>
<span data-ttu-id="a1637-369">Utilisateurs avec relais multimédia</span><span class="sxs-lookup"><span data-stu-id="a1637-369">Users with media bypass trunk</span></span> | <span data-ttu-id="a1637-370">CX3-20</span><span class="sxs-lookup"><span data-stu-id="a1637-370">20</span></span> | <span data-ttu-id="a1637-371">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="a1637-371">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="a1637-372">false</span><span class="sxs-lookup"><span data-stu-id="a1637-372">false</span></span> | 

<span data-ttu-id="a1637-373">Les deux Trunks peuvent pointer sur la même SBC avec la même adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="a1637-373">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="a1637-374">Les ports de signalisation TLS de l’SBC doivent être différents, comme indiqué dans le schéma suivant.</span><span class="sxs-lookup"><span data-stu-id="a1637-374">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="a1637-375">Remarque vous devrez vous assurer que votre certificat prend en charge les deux Trunks.</span><span class="sxs-lookup"><span data-stu-id="a1637-375">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="a1637-376">Dans SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="a1637-376">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Affiche les deux liaisons peuvent pointer sur le même SBC avec la même adresse IP publique](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="a1637-378">Pour plus d’informations sur la configuration de deux lignes sur le même SBC, voir la documentation fournie par votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="a1637-378">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="a1637-379">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="a1637-379">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a1637-380">Documentation relative au déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="a1637-380">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a1637-381">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="a1637-381">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a1637-382">Documentation sur le déploiement de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="a1637-382">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="a1637-383">Points de terminaison client pris en charge avec l’exclusion de média</span><span class="sxs-lookup"><span data-stu-id="a1637-383">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="a1637-384">La dérivation de média est prise en charge par tous les clients teams et les appareils de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="a1637-384">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="a1637-385">Pour tous les autres points de terminaison qui ne prennent pas en charge la dérivation multimédia, nous allons aborder l’appel sans contournement, même s’il a démarré en tant qu’appel de contournement.</span><span class="sxs-lookup"><span data-stu-id="a1637-385">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="a1637-386">Ce problème se produit automatiquement et ne nécessite aucune action de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="a1637-386">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="a1637-387">Cela inclut les téléphones 3PIP Skype entreprise et les clients Web teams qui prennent en charge l’appel de routage direct (nouveau Microsoft Edge basé sur chrome, Google Chrome et Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="a1637-387">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="a1637-388">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1637-388">See also</span></span>

[<span data-ttu-id="a1637-389">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="a1637-389">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



