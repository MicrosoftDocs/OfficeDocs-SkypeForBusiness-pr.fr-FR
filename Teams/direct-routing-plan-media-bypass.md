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
ms.openlocfilehash: cabbfd62ecc1a86d6e893d8d26ecdbe6cbbe7dbb
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469580"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="5f656-103">Planifier le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="5f656-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="5f656-104">À propos du contournement de média avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="5f656-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="5f656-105">La dérivation de médias vous permet d’abréger le chemin du trafic multimédia et de réduire le nombre de tronçons en transit pour de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="5f656-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="5f656-106">Par le biais du contournement du contenu multimédia, le contenu multimédia est maintenu entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via le système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="5f656-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="5f656-107">Pour configurer la dérivation multimédia, l’SBC et le client doivent se trouver dans le même emplacement ou réseau.</span><span class="sxs-lookup"><span data-stu-id="5f656-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="5f656-108">Vous pouvez contrôler la dérivation multimédia pour chaque SBC en utilisant la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** défini sur true ou false.</span><span class="sxs-lookup"><span data-stu-id="5f656-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="5f656-109">Cela ne signifie pas que le trafic multimédia restera dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5f656-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="5f656-110">Cet article décrit le flux d’appels dans différents scénarios.</span><span class="sxs-lookup"><span data-stu-id="5f656-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="5f656-111">Les diagrammes ci-dessous montrent la différence de flux d’appels avec et sans dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="5f656-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="5f656-112">Sans dérivation multimédia, quand un client effectue ou reçoit un appel, la signalisation et le flux multimédia entre le SBC, le système Microsoft Phone et le client Teams, comme indiqué dans le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="5f656-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f656-113">![Affiche la signalisation et le flux multimédia sans contournement du support multimédia](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="5f656-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="5f656-114">Par exemple, supposons qu’un utilisateur se trouve dans le même bâtiment ou réseau que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="5f656-115">Par exemple, supposons qu’un utilisateur participant à un bâtiment à Francfort effectue un appel vers un utilisateur RTC :</span><span class="sxs-lookup"><span data-stu-id="5f656-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="5f656-116">**Sans dérivation multimédia**, le contenu multimédia sera transmis par l’intermédiaire d’Amsterdam ou de Dublin (sur lequel sont déployés les centres de connaissances Microsoft) et de retour vers l’SBC à Francfort.</span><span class="sxs-lookup"><span data-stu-id="5f656-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="5f656-117">Le centre de donnees en Europe est sélectionné, car le SBC est en Europe et Microsoft utilise le centre de donne le plus proche de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="5f656-118">Même si cette approche n’a aucun impact sur la qualité des appels en raison de l’optimisation du flux de trafic au sein de réseaux Microsoft dans la plupart des zones géographiques, le trafic comporte une boucle inutile.</span><span class="sxs-lookup"><span data-stu-id="5f656-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="5f656-119">Par le biais du **contournement du contenu multimédia**, le média est maintenu directement entre l’utilisateur teams et l’élément SBC, comme illustré dans le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="5f656-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5f656-120">![Affiche le signalement et le flux multimédia avec une dérivation multimédia](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="5f656-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="5f656-121">La fonction de contournement de média utilise des protocoles appelés interactifs (ICE) sur le client teams et ICE Lite sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="5f656-122">Ces protocoles permettent le routage direct pour utiliser le chemin multimédia le plus direct pour une qualité optimale.</span><span class="sxs-lookup"><span data-stu-id="5f656-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="5f656-123">ICE et ICE Lite sont des normes WebRTC.</span><span class="sxs-lookup"><span data-stu-id="5f656-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="5f656-124">Pour plus d’informations sur ces protocoles, voir RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="5f656-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="5f656-125">Planification de flux d’appels et de pare-feu</span><span class="sxs-lookup"><span data-stu-id="5f656-125">Call flow and firewall planning</span></span>

<span data-ttu-id="5f656-126">Le flux d’appels et la planification de pare-feu varient selon que l’utilisateur a un accès direct à l’adresse IP publique de l’SBC et que l’utilisateur se trouve à l’intérieur ou à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="5f656-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5f656-127">Flux d’appels si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="5f656-128">Si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC, le flux des appels est le suivant :</span><span class="sxs-lookup"><span data-stu-id="5f656-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="5f656-129">Pour le contournement du média multimédia, le client teams doit avoir accès à l’adresse IP publique de la SBC même à partir d’un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="5f656-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="5f656-130">Si les médias directs ne sont pas souhaités, le média peut circuler via des relais de transport.</span><span class="sxs-lookup"><span data-stu-id="5f656-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="5f656-131">Il s’agit de la solution recommandée quand un utilisateur se trouve dans la même construction et/ou le même réseau que l’SBC : supprimer les composants Cloud Microsoft du chemin multimédia.</span><span class="sxs-lookup"><span data-stu-id="5f656-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="5f656-132">Le signalement est toujours transmis via le Cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f656-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="5f656-133">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est interne et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media) :</span><span class="sxs-lookup"><span data-stu-id="5f656-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="5f656-134">Les flèches et les valeurs numériques des chemins sont conformes aux [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span><span class="sxs-lookup"><span data-stu-id="5f656-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="5f656-135">Le signalement SIP accepte toujours les chemins 4 et 4 (selon la direction du trafic).</span><span class="sxs-lookup"><span data-stu-id="5f656-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5f656-136">Le contenu multimédia reste local et prend le chemin 5b.</span><span class="sxs-lookup"><span data-stu-id="5f656-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f656-137">![Flux d’appels avec contournement de média activé, le client est interne](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="5f656-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5f656-138">Flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="5f656-139">La description suivante décrit le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5f656-140">Par exemple, supposons que l’utilisateur est externe et que l’administrateur client a décidé de ne pas ouvrir l’adresse IP publique de l’SBC auprès de tout le monde sur Internet, mais uniquement dans Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="5f656-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="5f656-141">Les composants internes du trafic peuvent être acheminés par le biais des relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="5f656-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="5f656-142">Vous devez tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="5f656-142">Consider the following:</span></span>

- <span data-ttu-id="5f656-143">Des relais de transport d’équipes sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="5f656-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="5f656-144">Dans le cas d’une dérivation de média, Microsoft utilise une version de relais de transport qui nécessite l’ouverture des ports 50 000 à 59 999 entre les relais de transport d’équipe et l’SBC (à l’avenir, nous envisageons de migrer vers la version qui ne nécessite que les ports 3478 et 3479).</span><span class="sxs-lookup"><span data-stu-id="5f656-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="5f656-145">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client ne peut pas accéder à l’adresse IP publique du contrôleur de bordure de session (le contenu multimédia est relayée par teams Relay Relay).</span><span class="sxs-lookup"><span data-stu-id="5f656-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="5f656-146">Les flèches et les valeurs numériques des chemins sont conformes aux [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span><span class="sxs-lookup"><span data-stu-id="5f656-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="5f656-147">Les médias sont relayés par le biais de chemins d’accès 3, 3, 4 et 4 '</span><span class="sxs-lookup"><span data-stu-id="5f656-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f656-148">![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="5f656-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="5f656-149">Flux d’appels s’il se trouve hors du réseau et a accès à l’adresse IP publique de l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="5f656-150">Il ne s’agit pas d’une configuration recommandée, car elle ne tire aucunement parti des relais de transport Teams.</span><span class="sxs-lookup"><span data-stu-id="5f656-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="5f656-151">Au lieu de cela, vous devez prendre en considération le scénario précédent dans lequel l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5f656-152">Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media).</span><span class="sxs-lookup"><span data-stu-id="5f656-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="5f656-153">Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="5f656-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="5f656-154">Le signalement SIP accepte toujours les chemins 3 et 3 (selon la direction du trafic).</span><span class="sxs-lookup"><span data-stu-id="5f656-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5f656-155">Flux multimédias utilisant Path 2.</span><span class="sxs-lookup"><span data-stu-id="5f656-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f656-156">![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="5f656-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="5f656-157">Utilisation de processeurs multimédias et de relais de transport</span><span class="sxs-lookup"><span data-stu-id="5f656-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="5f656-158">Il existe deux composants dans le Cloud Microsoft qui peuvent se trouver dans le chemin d’accès au média : processeurs multimédias et relais de transport.</span><span class="sxs-lookup"><span data-stu-id="5f656-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="5f656-159">Le processeur de média est un composant public qui gère le contenu multimédia en cas de non-contournement et gère le contenu multimédia pour les applications vocales.</span><span class="sxs-lookup"><span data-stu-id="5f656-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="5f656-160">Les processeurs multimédias sont toujours dans le chemin d’accès pour les utilisateurs finaux sans ignorer les appels, mais jamais dans le chemin d’accès pour les appels ignorés.</span><span class="sxs-lookup"><span data-stu-id="5f656-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="5f656-161">Les processeurs multimédias sont toujours dans le chemin d’accès de toutes les applications vocales, telles que le parc d’appels, le standard automatique d’entreprise et les files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="5f656-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="5f656-162">Le relais de transport est utilisé pour se connecter au service de transport le plus proche pour envoyer du trafic en temps réel.</span><span class="sxs-lookup"><span data-stu-id="5f656-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="5f656-163">Les relais de transport peuvent être ou ne pas se trouver dans le chemin d’accès pour les appels passés (provenant de ou destinés aux utilisateurs finaux), en fonction de l’endroit où se trouve l’utilisateur et du mode de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="5f656-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="5f656-164">Le schéma suivant montre deux flux d’appels : l’un avec la dérivation multimédia est activée et le second avec contournement de média désactivé.</span><span class="sxs-lookup"><span data-stu-id="5f656-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="5f656-165">Remarque le diagramme ne montre que le trafic provenant de--ou destinés aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="5f656-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="5f656-166">La manette de média est un microservice dans Azure qui affecte des processeurs de média et crée des offres SDP.</span><span class="sxs-lookup"><span data-stu-id="5f656-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="5f656-167">Le proxy SIP est un composant qui convertit la signalisation HTTP REST utilisée dans teams pour SIP.</span><span class="sxs-lookup"><span data-stu-id="5f656-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f656-168">![Flux d’appels avec contournement de média activé et désactivé](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="5f656-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="5f656-169">Le tableau ci-dessous résume la différence entre les processeurs multimédias et les relais de transport.</span><span class="sxs-lookup"><span data-stu-id="5f656-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="5f656-170">Processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="5f656-170">Media Processors</span></span> | <span data-ttu-id="5f656-171">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="5f656-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="5f656-172">Chemin multimédia pour les appels sans contournement pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="5f656-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="5f656-173">Toujours</span><span class="sxs-lookup"><span data-stu-id="5f656-173">Always</span></span> | <span data-ttu-id="5f656-174">Interdire</span><span class="sxs-lookup"><span data-stu-id="5f656-174">Never</span></span> | 
<span data-ttu-id="5f656-175">Dans le chemin multimédia pour les appels ignorés pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="5f656-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="5f656-176">Interdire</span><span class="sxs-lookup"><span data-stu-id="5f656-176">Never</span></span> | <span data-ttu-id="5f656-177">Si le client ne peut pas accéder à l’SBC sur l’adresse IP publique</span><span class="sxs-lookup"><span data-stu-id="5f656-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="5f656-178">Dans le chemin multimédia pour les applications vocales</span><span class="sxs-lookup"><span data-stu-id="5f656-178">In media path for voice applications</span></span> | <span data-ttu-id="5f656-179">Toujours</span><span class="sxs-lookup"><span data-stu-id="5f656-179">Always</span></span> | <span data-ttu-id="5f656-180">Interdire</span><span class="sxs-lookup"><span data-stu-id="5f656-180">Never</span></span> | 
<span data-ttu-id="5f656-181">Peut faire un transcodage (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="5f656-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="5f656-182">Oui</span><span class="sxs-lookup"><span data-stu-id="5f656-182">Yes</span></span> | <span data-ttu-id="5f656-183">Non, ne relaye le son qu’entre les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="5f656-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="5f656-184">Nombre d’instances dans le monde et emplacement</span><span class="sxs-lookup"><span data-stu-id="5f656-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="5f656-185">10 au total : 2 aux États-Unis et en ouest ; 2 dans Amsterdam et Dublin ; 2 à Hong Kong et Singapour ; 2 au Japon ; 2 de l’Australie est et du sud-est</span><span class="sxs-lookup"><span data-stu-id="5f656-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="5f656-186">Multiples</span><span class="sxs-lookup"><span data-stu-id="5f656-186">Multiple</span></span>

<span data-ttu-id="5f656-187">Les plages d’adresses IP sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f656-187">The IP ranges are:</span></span>
- <span data-ttu-id="5f656-188">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5f656-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="5f656-189">52.120.0.0/14 (adresses IP de 52.120.0.1 à 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="5f656-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="5f656-190">\* Explication du transcodage :</span><span class="sxs-lookup"><span data-stu-id="5f656-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="5f656-191">Le processeur de média est B2BUA, ce qui signifie qu’il peut changer un codec (par exemple, soie du client teams vers MP et G. 711 entre MP et SBC).</span><span class="sxs-lookup"><span data-stu-id="5f656-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="5f656-192">Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n’est jamais changé entre le client et l’SBC, même si le trafic est transmis via des relais.</span><span class="sxs-lookup"><span data-stu-id="5f656-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="5f656-193">Utilisation de médias multimédias teams si Trunk est configuré pour la dérivation multimédia</span><span class="sxs-lookup"><span data-stu-id="5f656-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="5f656-194">Les processeurs multimédias teams sont toujours insérés dans le chemin multimédia dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="5f656-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="5f656-195">Appel transféré de 1:1 vers un appel de groupe</span><span class="sxs-lookup"><span data-stu-id="5f656-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="5f656-196">Appel vers un utilisateur d’équipes fédérées</span><span class="sxs-lookup"><span data-stu-id="5f656-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="5f656-197">Appel transféré ou transféré vers un utilisateur Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="5f656-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="5f656-198">Assurez-vous que votre SBC a accès aux processeurs multimédias et aux plages de relais de transport comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5f656-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="5f656-199">Signalisation SIP : noms de domaine complets</span><span class="sxs-lookup"><span data-stu-id="5f656-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="5f656-200">Pour la signalisation SIP, les exigences en matière de nom de domaine complet et de pare-feu sont les mêmes que pour les cas sans contournement.</span><span class="sxs-lookup"><span data-stu-id="5f656-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="5f656-201">Le routage direct est fourni dans les environnements Microsoft 365 ou Office 365 suivants :</span><span class="sxs-lookup"><span data-stu-id="5f656-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="5f656-202">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5f656-203">GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-203">Office 365 GCC</span></span>
- <span data-ttu-id="5f656-204">Office 365 (GCC High)</span><span class="sxs-lookup"><span data-stu-id="5f656-204">Office 365 GCC High</span></span>
- <span data-ttu-id="5f656-205">Office 365 DoD en savoir plus sur les [environnements d’administration des États-Unis et d’office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.</span><span class="sxs-lookup"><span data-stu-id="5f656-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5f656-206">Environnements Microsoft 365, Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5f656-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="5f656-207">Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :</span><span class="sxs-lookup"><span data-stu-id="5f656-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="5f656-208">**SIP.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) global, doit d’abord être essayé.</span><span class="sxs-lookup"><span data-stu-id="5f656-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="5f656-209">Lorsque le SBC envoie une demande pour résoudre ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de noms principal Azure attribué à l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="5f656-210">Cette affectation est basée sur les métriques de performance des centres de donnes et de proximité géographique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="5f656-211">L’adresse IP renvoyée correspond au FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="5f656-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="5f656-212">**sip2.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) : il correspond à la deuxième région de priorité.</span><span class="sxs-lookup"><span data-stu-id="5f656-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="5f656-213">nom de domaine complet (FQDN) **sip3.pstnhub.Microsoft.com** : il correspond géographiquement à la troisième région de priorité.</span><span class="sxs-lookup"><span data-stu-id="5f656-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="5f656-214">Pour pouvoir effectuer les opérations suivantes, vous devez placer ces trois noms de domaine complets :</span><span class="sxs-lookup"><span data-stu-id="5f656-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="5f656-215">Offrir une plus meilleure version (moins chargée et la plus proche du centre de divertissement SBC attribué en interrogeant le premier nom de domaine complet).</span><span class="sxs-lookup"><span data-stu-id="5f656-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="5f656-216">Fournir un basculement lorsqu’une connexion à partir d’un SBC est établie à un centre de donne qui rencontre un problème temporaire.</span><span class="sxs-lookup"><span data-stu-id="5f656-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="5f656-217">Pour plus d’informations, consultez la section mécanisme de basculement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5f656-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="5f656-218">Les noms de domaine complets **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**et **sip3.pstnhub.Microsoft.com** seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f656-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="5f656-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="5f656-219">52.114.148.0</span></span>
- <span data-ttu-id="5f656-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="5f656-220">52.114.132.46</span></span>
- <span data-ttu-id="5f656-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="5f656-221">52.114.16.74</span></span>
- <span data-ttu-id="5f656-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="5f656-222">52.114.20.29</span></span>
- <span data-ttu-id="5f656-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="5f656-223">52.114.75.24</span></span>
- <span data-ttu-id="5f656-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="5f656-224">52.114.76.76</span></span>
- <span data-ttu-id="5f656-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="5f656-225">52.114.7.24</span></span>
- <span data-ttu-id="5f656-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="5f656-226">52.114.14.70</span></span>

<span data-ttu-id="5f656-227">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="5f656-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="5f656-228">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet **SIP-All.pstnhub.Microsoft.com** est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="5f656-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5f656-229">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="5f656-230">Le point de connexion pour le routage direct est le nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="5f656-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5f656-231">**SIP.pstnhub.DoD.Teams.Microsoft.us** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="5f656-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5f656-232">Comme l’environnement Office 365 DoD existe uniquement dans les centres de données américains, il n’existe pas de noms de domaine complets secondaires et tertiaires.</span><span class="sxs-lookup"><span data-stu-id="5f656-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5f656-233">Les noms de domaine complets (FQDN) – sip.pstnhub.dod.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f656-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="5f656-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="5f656-234">52.127.64.33</span></span>
- <span data-ttu-id="5f656-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="5f656-235">52.127.68.34</span></span>

<span data-ttu-id="5f656-236">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="5f656-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5f656-237">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="5f656-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5f656-238">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="5f656-239">Le point de connexion pour le routage direct est le nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="5f656-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5f656-240">**SIP.pstnhub.gov.Teams.Microsoft.us** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="5f656-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5f656-241">Dans la mesure où l’environnement de grande qualité n’existe qu’aux centres de données américains, il n’y a pas de noms de domaine complets secondaires et tertiaires.</span><span class="sxs-lookup"><span data-stu-id="5f656-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5f656-242">Les noms de domaine complets (FQDN) – sip.pstnhub.gov.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f656-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="5f656-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="5f656-243">52.127.88.59</span></span>
- <span data-ttu-id="5f656-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="5f656-244">52.127.92.64</span></span>

<span data-ttu-id="5f656-245">Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="5f656-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5f656-246">Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us est résolu sur toutes les adresses IP suivantes.</span><span class="sxs-lookup"><span data-stu-id="5f656-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="5f656-247">Signalisation SIP : ports</span><span class="sxs-lookup"><span data-stu-id="5f656-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="5f656-248">La configuration requise pour les ports est identique pour tous les environnements Office 365 dans lesquels le routage direct est disponible :</span><span class="sxs-lookup"><span data-stu-id="5f656-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="5f656-249">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5f656-250">GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-250">Office 365 GCC</span></span>
- <span data-ttu-id="5f656-251">Office 365 (GCC High)</span><span class="sxs-lookup"><span data-stu-id="5f656-251">Office 365 GCC High</span></span>
- <span data-ttu-id="5f656-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="5f656-252">Office 365 DoD</span></span>

<span data-ttu-id="5f656-253">Vous devez utiliser les ports suivants :</span><span class="sxs-lookup"><span data-stu-id="5f656-253">You must use the following ports:</span></span>

| <span data-ttu-id="5f656-254">Trafic</span><span class="sxs-lookup"><span data-stu-id="5f656-254">Traffic</span></span> | <span data-ttu-id="5f656-255">De</span><span class="sxs-lookup"><span data-stu-id="5f656-255">From</span></span> | <span data-ttu-id="5f656-256">À</span><span class="sxs-lookup"><span data-stu-id="5f656-256">To</span></span> | <span data-ttu-id="5f656-257">Port source</span><span class="sxs-lookup"><span data-stu-id="5f656-257">Source port</span></span> | <span data-ttu-id="5f656-258">Port de destination</span><span class="sxs-lookup"><span data-stu-id="5f656-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5f656-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5f656-259">SIP/TLS</span></span>| <span data-ttu-id="5f656-260">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="5f656-260">SIP Proxy</span></span> | <span data-ttu-id="5f656-261">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-261">SBC</span></span> | <span data-ttu-id="5f656-262">1024-65535</span><span class="sxs-lookup"><span data-stu-id="5f656-262">1024 - 65535</span></span> | <span data-ttu-id="5f656-263">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-263">Defined on the SBC</span></span> |
| <span data-ttu-id="5f656-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5f656-264">SIP/TLS</span></span> | <span data-ttu-id="5f656-265">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-265">SBC</span></span> | <span data-ttu-id="5f656-266">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="5f656-266">SIP Proxy</span></span> | <span data-ttu-id="5f656-267">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-267">Defined on the SBC</span></span> | <span data-ttu-id="5f656-268">5061</span><span class="sxs-lookup"><span data-stu-id="5f656-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="5f656-269">Trafic multimédia : plages d’adresses IP et de ports</span><span class="sxs-lookup"><span data-stu-id="5f656-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="5f656-270">Le trafic multimédia entre le client SBC et teams est disponible si la connectivité directe est disponible ou par le biais de relais de transport d’équipes si le client ne peut pas accéder à l’SBC en utilisant l’adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="5f656-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="5f656-271">Configuration requise pour le trafic multimédia direct (entre le client teams et l’SBC)</span><span class="sxs-lookup"><span data-stu-id="5f656-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="5f656-272">Le client doit avoir accès aux ports spécifiés (voir table) sur l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="5f656-273">Remarque : si le client se trouve dans un réseau interne, le média est transmis à l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="5f656-274">Vous pouvez configurer l’épinglage des cheveux sur votre appareil NAT pour que le trafic ne reste jamais sur l’équipement réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5f656-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="5f656-275">Trafic</span><span class="sxs-lookup"><span data-stu-id="5f656-275">Traffic</span></span> | <span data-ttu-id="5f656-276">De</span><span class="sxs-lookup"><span data-stu-id="5f656-276">From</span></span> | <span data-ttu-id="5f656-277">À</span><span class="sxs-lookup"><span data-stu-id="5f656-277">To</span></span> | <span data-ttu-id="5f656-278">Port source</span><span class="sxs-lookup"><span data-stu-id="5f656-278">Source port</span></span> | <span data-ttu-id="5f656-279">Port de destination</span><span class="sxs-lookup"><span data-stu-id="5f656-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5f656-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5f656-280">UDP/SRTP</span></span> | <span data-ttu-id="5f656-281">Client</span><span class="sxs-lookup"><span data-stu-id="5f656-281">Client</span></span> | <span data-ttu-id="5f656-282">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-282">SBC</span></span> | <span data-ttu-id="5f656-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="5f656-283">50 000 – 50 019</span></span>  | <span data-ttu-id="5f656-284">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-284">Defined on the SBC</span></span> |
| <span data-ttu-id="5f656-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5f656-285">UDP/SRTP</span></span> | <span data-ttu-id="5f656-286">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-286">SBC</span></span> | <span data-ttu-id="5f656-287">Client</span><span class="sxs-lookup"><span data-stu-id="5f656-287">Client</span></span> | <span data-ttu-id="5f656-288">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-288">Defined on the SBC</span></span> | <span data-ttu-id="5f656-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="5f656-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="5f656-290">Si vous disposez d’un appareil réseau qui traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="5f656-291">Configuration requise pour l’utilisation des relais de transport</span><span class="sxs-lookup"><span data-stu-id="5f656-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="5f656-292">Les relais de transport sont dans la même plage que les processeurs de médias (pour les cas de non-contournement) :</span><span class="sxs-lookup"><span data-stu-id="5f656-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5f656-293">Environnements Microsoft 365, Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5f656-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="5f656-294">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5f656-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5f656-295">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5f656-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5f656-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5f656-297">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5f656-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5f656-298">52.127.88.0/21</span></span>


<span data-ttu-id="5f656-299">Le tableau suivant indique la plage de ports des relais de transport Teams (applicables à tous les environnements) :</span><span class="sxs-lookup"><span data-stu-id="5f656-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="5f656-300">Trafic</span><span class="sxs-lookup"><span data-stu-id="5f656-300">Traffic</span></span> | <span data-ttu-id="5f656-301">De</span><span class="sxs-lookup"><span data-stu-id="5f656-301">From</span></span> | <span data-ttu-id="5f656-302">À</span><span class="sxs-lookup"><span data-stu-id="5f656-302">To</span></span> | <span data-ttu-id="5f656-303">Port source</span><span class="sxs-lookup"><span data-stu-id="5f656-303">Source port</span></span> | <span data-ttu-id="5f656-304">Port de destination</span><span class="sxs-lookup"><span data-stu-id="5f656-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5f656-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5f656-305">UDP/SRTP</span></span> | <span data-ttu-id="5f656-306">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="5f656-306">Transport Relay</span></span> | <span data-ttu-id="5f656-307">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-307">SBC</span></span> | <span data-ttu-id="5f656-308">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="5f656-308">50 000 -59 999</span></span>    | <span data-ttu-id="5f656-309">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-309">Defined on the SBC</span></span> |
| <span data-ttu-id="5f656-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5f656-310">UDP/SRTP</span></span> | <span data-ttu-id="5f656-311">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-311">SBC</span></span> | <span data-ttu-id="5f656-312">Relais de transport</span><span class="sxs-lookup"><span data-stu-id="5f656-312">Transport Relay</span></span> | <span data-ttu-id="5f656-313">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-313">Defined on the SBC</span></span> | <span data-ttu-id="5f656-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="5f656-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="5f656-315">Microsoft recommande au moins deux ports par appel simultané sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="5f656-316">Microsoft étant doté de deux versions de relais de transport, les informations suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="5f656-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="5f656-317">v4, qui peut uniquement utiliser la plage de ports 50 000 à 59 999</span><span class="sxs-lookup"><span data-stu-id="5f656-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="5f656-318">V6, qui est compatible avec les ports 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="5f656-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="5f656-319">Pour le moment, le contournement de média ne prend en charge que la version v4 de relais de transport.</span><span class="sxs-lookup"><span data-stu-id="5f656-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="5f656-320">La prise en charge de la version V6 sera bientôt prise en charge.</span><span class="sxs-lookup"><span data-stu-id="5f656-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="5f656-321">Vous avez besoin d’ouvrir les ports 3478 et 3479 pour la transition.</span><span class="sxs-lookup"><span data-stu-id="5f656-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="5f656-322">Lorsque Microsoft présente la prise en charge des relais de transport V6 avec le contournement de média, vous n’aurez pas besoin de reconfigurer votre équipement réseau ou SBCs.</span><span class="sxs-lookup"><span data-stu-id="5f656-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="5f656-323">Configuration requise pour l’utilisation de processeurs multimédias</span><span class="sxs-lookup"><span data-stu-id="5f656-323">Requirements for using media processors</span></span>

<span data-ttu-id="5f656-324">Les processeurs multimédias sont toujours dans le chemin multimédia pour les applications vocales et pour les clients Web (par exemple, les clients teams dans Microsoft Edge ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="5f656-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="5f656-325">Les exigences sont les mêmes que pour la configuration sans contournement.</span><span class="sxs-lookup"><span data-stu-id="5f656-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="5f656-326">La plage d’adresses IP du trafic multimédia est</span><span class="sxs-lookup"><span data-stu-id="5f656-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5f656-327">Environnements Office 365 et Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5f656-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="5f656-328">52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5f656-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5f656-329">Environnement DoD DoD dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5f656-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5f656-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5f656-331">Environnement de grande qualité dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5f656-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5f656-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5f656-332">52.127.88.0/21</span></span>

<span data-ttu-id="5f656-333">Le tableau suivant indique la portée de port des processeurs multimédias (applicables à tous les environnements) :</span><span class="sxs-lookup"><span data-stu-id="5f656-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="5f656-334">Trafic</span><span class="sxs-lookup"><span data-stu-id="5f656-334">Traffic</span></span> | <span data-ttu-id="5f656-335">De</span><span class="sxs-lookup"><span data-stu-id="5f656-335">From</span></span> | <span data-ttu-id="5f656-336">À</span><span class="sxs-lookup"><span data-stu-id="5f656-336">To</span></span> | <span data-ttu-id="5f656-337">Port source</span><span class="sxs-lookup"><span data-stu-id="5f656-337">Source port</span></span> | <span data-ttu-id="5f656-338">Port de destination</span><span class="sxs-lookup"><span data-stu-id="5f656-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5f656-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5f656-339">UDP/SRTP</span></span> | <span data-ttu-id="5f656-340">Processeur de média</span><span class="sxs-lookup"><span data-stu-id="5f656-340">Media Processor</span></span> | <span data-ttu-id="5f656-341">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-341">SBC</span></span> | <span data-ttu-id="5f656-342">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="5f656-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="5f656-343">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-343">Defined on the SBC</span></span> |
| <span data-ttu-id="5f656-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5f656-344">UDP/SRTP</span></span> | <span data-ttu-id="5f656-345">SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-345">SBC</span></span> | <span data-ttu-id="5f656-346">Processeur de média</span><span class="sxs-lookup"><span data-stu-id="5f656-346">Media Processor</span></span> | <span data-ttu-id="5f656-347">Définie sur l’SBC</span><span class="sxs-lookup"><span data-stu-id="5f656-347">Defined on the SBC</span></span> | <span data-ttu-id="5f656-348">3478, 3479 et 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="5f656-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="5f656-349">Configurer des Trunks séparés pour le contournement du contenu multimédia et l’exclusion de médias non multimédias</span><span class="sxs-lookup"><span data-stu-id="5f656-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="5f656-350">Si vous effectuez une migration vers une dérivation multimédia à partir d’une dérivation non multimédia et que vous voulez confirmer la fonctionnalité avant de migrer toute utilisation en dérivation du support multimédia, vous pouvez créer une stratégie de routage et une stratégie d’acheminement en ligne distinctes pour diriger vers le Trunk de contournement du média et l’affecter à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5f656-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="5f656-351">Étapes de configuration de haut niveau :</span><span class="sxs-lookup"><span data-stu-id="5f656-351">High-level configuration steps:</span></span>

- <span data-ttu-id="5f656-352">Identifiez les utilisateurs pour tester le contournement du contenu multimédia.</span><span class="sxs-lookup"><span data-stu-id="5f656-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="5f656-353">Créez deux Trunks distinctes avec différents noms de domaine complets : l’un est activé pour la dérivation multimédia ; l’autre non.</span><span class="sxs-lookup"><span data-stu-id="5f656-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="5f656-354">Les deux Trunks pointent vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="5f656-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="5f656-355">Les ports pour le signalement SIP TLS doivent être différents.</span><span class="sxs-lookup"><span data-stu-id="5f656-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="5f656-356">Les ports pour le média doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="5f656-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="5f656-357">Créez une nouvelle stratégie de routage de la voix en ligne et attribuez la ligne de contournement du support multimédia aux itinéraires correspondants associés à l’utilisation RTC de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="5f656-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="5f656-358">Affectez la nouvelle stratégie de routage vocale en ligne aux utilisateurs que vous avez identifiés pour tester le contournement du contenu multimédia.</span><span class="sxs-lookup"><span data-stu-id="5f656-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="5f656-359">L’exemple ci-dessous illustre cette logique.</span><span class="sxs-lookup"><span data-stu-id="5f656-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="5f656-360">Ensemble d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="5f656-360">Set of users</span></span> | <span data-ttu-id="5f656-361">Nombre d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="5f656-361">Number of users</span></span> | <span data-ttu-id="5f656-362">Nom de domaine complet du Trunk affecté dans OVRP</span><span class="sxs-lookup"><span data-stu-id="5f656-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="5f656-363">Contournement de média activé</span><span class="sxs-lookup"><span data-stu-id="5f656-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="5f656-364">Utilisateurs dotés d’une ligne de contournement non multimédia</span><span class="sxs-lookup"><span data-stu-id="5f656-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="5f656-365">980</span><span class="sxs-lookup"><span data-stu-id="5f656-365">980</span></span> | <span data-ttu-id="5f656-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="5f656-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="5f656-367">true</span><span class="sxs-lookup"><span data-stu-id="5f656-367">true</span></span>
<span data-ttu-id="5f656-368">Utilisateurs avec relais multimédia</span><span class="sxs-lookup"><span data-stu-id="5f656-368">Users with media bypass trunk</span></span> | <span data-ttu-id="5f656-369">CX3-20</span><span class="sxs-lookup"><span data-stu-id="5f656-369">20</span></span> | <span data-ttu-id="5f656-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="5f656-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="5f656-371">false</span><span class="sxs-lookup"><span data-stu-id="5f656-371">false</span></span> | 

<span data-ttu-id="5f656-372">Les deux Trunks peuvent pointer sur la même SBC avec la même adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="5f656-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="5f656-373">Les ports de signalisation TLS de l’SBC doivent être différents, comme indiqué dans le schéma suivant.</span><span class="sxs-lookup"><span data-stu-id="5f656-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="5f656-374">Remarque vous devrez vous assurer que votre certificat prend en charge les deux Trunks.</span><span class="sxs-lookup"><span data-stu-id="5f656-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="5f656-375">Dans SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="5f656-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f656-376">![Affiche les deux liaisons peuvent pointer sur le même SBC avec la même adresse IP publique](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="5f656-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="5f656-377">Pour plus d’informations sur la configuration de deux lignes sur le même SBC, voir la documentation fournie par votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="5f656-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="5f656-378">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="5f656-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="5f656-379">Documentation relative au déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="5f656-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="5f656-380">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="5f656-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="5f656-381">Documentation sur le déploiement de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="5f656-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="5f656-382">Points de terminaison client pris en charge avec l’exclusion de média</span><span class="sxs-lookup"><span data-stu-id="5f656-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="5f656-383">La dérivation de média est prise en charge par tous les clients teams et les appareils de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="5f656-383">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="5f656-384">Pour tous les autres points de terminaison qui ne prennent pas en charge la dérivation multimédia, nous allons aborder l’appel sans contournement, même s’il a démarré en tant qu’appel de contournement.</span><span class="sxs-lookup"><span data-stu-id="5f656-384">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="5f656-385">Ce problème se produit automatiquement et ne nécessite aucune action de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="5f656-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="5f656-386">Cela inclut les téléphones 3PIP Skype entreprise et les clients Web teams qui prennent en charge l’appel de routage direct (nouveau Microsoft Edge basé sur chrome, Google Chrome et Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="5f656-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="5f656-387">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f656-387">See also</span></span>

[<span data-ttu-id="5f656-388">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="5f656-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)


