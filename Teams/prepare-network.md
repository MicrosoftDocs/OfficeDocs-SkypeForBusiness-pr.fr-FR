---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Découvrez comment préparer et gérer votre réseau pour Microsoft Teams. Les informations comprennent la configuration réseau requise, la condition requise en matière de bande passante ainsi que des remarques supplémentaires.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d203aefa4ba6991fbe6cf6a2ac463f4649f2aaa9
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198420"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="ce284-104">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce284-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="ce284-105">Teams associe trois types de trafic :</span><span class="sxs-lookup"><span data-stu-id="ce284-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="ce284-106">le trafic de données entre l'environnement en ligne Office 365 et le client Teams (signalisation, présence, conversation, chargement et téléchargement de fichiers, synchronisation OneNote) ;</span><span class="sxs-lookup"><span data-stu-id="ce284-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="ce284-107">le trafic des communications P2P en temps réel (audio, vidéo, partage de bureau) ;</span><span class="sxs-lookup"><span data-stu-id="ce284-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="ce284-108">le trafic des communications de conférence en temps réel (audio, vidéo, partage de bureau).</span><span class="sxs-lookup"><span data-stu-id="ce284-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="ce284-p102">Cela affecte le réseau sur deux niveaux : le trafic est acheminé entre les clients Microsoft Teams directement pour les communications P2P et le trafic est acheminé entre l'environnement Office 365 et les clients Microsoft Teams dans le cas des réunions. Pour assurer un flux optimal, le trafic doit pouvoir être acheminé à la fois entre les segments réseau (par ex. : entre des sites sur le réseau WAN) et entre les sites réseau et Office 365. Si les ports appropriés ne sont pas ouverts ou que des ports spécifiques sont activement bloqués, cela risque de dégrader la qualité de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="ce284-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="ce284-112">Les réunions sont prises en charge sur les appareils mobiles iOS et Android.</span><span class="sxs-lookup"><span data-stu-id="ce284-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="ce284-113">Pour bénéficier d’une meilleure utilisation du contenu multimédia en temps réel au sein de Microsoft Teams, votre réseau doit respecter la configuration requise en matière de réseau pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce284-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="ce284-114">Pour plus d’informations, consultez la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="ce284-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="ce284-115">Les deux segments réseau de définition (client vers Microsoft Edge et côté client vers Microsoft Edge) doivent respecter la configuration requise suivante.</span><span class="sxs-lookup"><span data-stu-id="ce284-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="ce284-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="ce284-116">Value</span></span>  |<span data-ttu-id="ce284-117">Client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ce284-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="ce284-118">Périphérie client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ce284-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="ce284-119">**Latence (unidirectionnelle)**\*</span><span class="sxs-lookup"><span data-stu-id="ce284-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="ce284-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="ce284-120">< 50ms</span></span>          |<span data-ttu-id="ce284-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="ce284-121">< 30ms</span></span>         |
|<span data-ttu-id="ce284-122">**Latence (RTT ou durée de l’aller-retour)**\*</span><span class="sxs-lookup"><span data-stu-id="ce284-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="ce284-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="ce284-123">< 100ms</span></span>   |<span data-ttu-id="ce284-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="ce284-124">< 60ms</span></span> |
|<span data-ttu-id="ce284-125">**Perte de paquets en rafale**</span><span class="sxs-lookup"><span data-stu-id="ce284-125">**Burst packet loss**</span></span>    |<span data-ttu-id="ce284-126">< 10 % sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="ce284-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="ce284-127">< 1% sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="ce284-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="ce284-128">**Perte de paquets**</span><span class="sxs-lookup"><span data-stu-id="ce284-128">**Packet loss**</span></span>     |<span data-ttu-id="ce284-129">< 1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="ce284-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="ce284-130">< 0,1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="ce284-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="ce284-131">**Gigue entre les arrivées de paquets**</span><span class="sxs-lookup"><span data-stu-id="ce284-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="ce284-132">< 30 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="ce284-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="ce284-133">< 15 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="ce284-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="ce284-134">**Réorganisation des paquets**</span><span class="sxs-lookup"><span data-stu-id="ce284-134">**Packet reorder**</span></span>    |<span data-ttu-id="ce284-135">< 0,05 % paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="ce284-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="ce284-136">< 0,01% paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="ce284-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="ce284-137">\*Les cibles métriques de latence présupposent que le site ou les sites de votre entreprise et les bords Microsoft se trouvent sur le même continent.</span><span class="sxs-lookup"><span data-stu-id="ce284-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="ce284-138">La connexion au site de votre entreprise avec le réseau de périmètre Microsoft inclut un accès réseau de premier saut, qui peut être WiFi ou une autre technologie sans fil.</span><span class="sxs-lookup"><span data-stu-id="ce284-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="ce284-139">Les cibles de performance réseau adoptent une planification de bande passante et/ou de [QoS](QoS-in-Teams.md)correcte.</span><span class="sxs-lookup"><span data-stu-id="ce284-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="ce284-140">En d’autres termes, les exigences s’appliquent directement au trafic multimédia en temps réel lors de la connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="ce284-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="ce284-141">Pour tester les deux segments réseau, vous pouvez utiliser l' [outil d’évaluation du réseau](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="ce284-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="ce284-142">Cet outil peut être déployé sur le PC client directement et sur un PC connecté au bord du réseau du client.</span><span class="sxs-lookup"><span data-stu-id="ce284-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="ce284-143">L’outil inclut une documentation limitée, mais une documentation plus approfondie sur l’utilisation de l’outil est disponible ici: [évaluation](https://go.microsoft.com/fwlink/?linkid=855800)de la disponibilité du réseau.</span><span class="sxs-lookup"><span data-stu-id="ce284-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="ce284-144">L’exécution de cette analyse de préparation du réseau vous permet de valider la préparation de votre réseau pour exécuter des applications multimédias en temps réel, telles que Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ce284-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="ce284-145">Il s’agit de la même évaluation de compatibilité réseau que celle qui est recommandée pour les clients souhaitant déployer Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="ce284-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="ce284-146">Bande passante requise</span><span class="sxs-lookup"><span data-stu-id="ce284-146">Bandwidth requirements</span></span>
<span data-ttu-id="ce284-147">Microsoft teams vous offre la meilleure expérience audio, vidéo et de partage de contenu quelle que soit l’état de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="ce284-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="ce284-148">Grâce aux codecs variables, le média peut être négocié dans les environnements à bande passante limitée avec un impact minimal.</span><span class="sxs-lookup"><span data-stu-id="ce284-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="ce284-149">Même si la bande passante n’est pas un problème, les expériences peuvent être optimisées en matière de qualité, y compris jusqu’à 1080p résolutions vidéo, jusqu’à 30 IPS pour la vidéo et 15fps pour le contenu et le son haute fidélité.</span><span class="sxs-lookup"><span data-stu-id="ce284-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="ce284-150">Considérations relatives au réseau supplémentaire</span><span class="sxs-lookup"><span data-stu-id="ce284-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="ce284-151">Résolution de noms externes</span><span class="sxs-lookup"><span data-stu-id="ce284-151">External Name Resolution</span></span>

<span data-ttu-id="ce284-152">Assurez-vous que tous les ordinateurs clients exécutant teams peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365 et que vos pare-feu n’empêchent pas l’accès.</span><span class="sxs-lookup"><span data-stu-id="ce284-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="ce284-153">Pour plus d’informations sur la configuration des ports de pare-feu, voir [URL et plages d’adresses IP Office 365](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="ce284-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="ce284-154">Taille du pool NAT</span><span class="sxs-lookup"><span data-stu-id="ce284-154">NAT Pool Size</span></span>

<span data-ttu-id="ce284-155">Lorsque plusieurs utilisateurs/appareils accèdent à Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou de la traduction d’adresses de port (PAT), vous devez vous assurer que les périphériques cachés derrière chaque adresse IP routable publique ne dépassent pas le numéro pris en charge.</span><span class="sxs-lookup"><span data-stu-id="ce284-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="ce284-156">Pour atténuer ce risque, assurez-vous que les adresses IP publiques appropriées sont affectées aux pools NAT pour empêcher l’épuisement du port.</span><span class="sxs-lookup"><span data-stu-id="ce284-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="ce284-157">L’épuisement du port permettra aux utilisateurs finaux et aux appareils internes d’affronter de rencontrer des problèmes lors de la connexion aux services Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce284-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="ce284-158">Pour plus d’informations, voir [prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="ce284-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="ce284-159">**Recommandations en matière de détection d’intrusion et de prévention**</span><span class="sxs-lookup"><span data-stu-id="ce284-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="ce284-160">Si votre environnement dispose d’une détection d’intrusions et/ou d’un système de prévention (IDS/IPS) déployé pour une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout le trafic lié aux URL d’Office 365 est affiché dans la zone d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="ce284-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="ce284-161">Détermination de l’état du réseau</span><span class="sxs-lookup"><span data-stu-id="ce284-161">Network health determination</span></span>
-----------------

<span data-ttu-id="ce284-162">Lors de la planification de l’implémentation de Microsoft teams au sein de votre réseau, vous devez vous assurer que vous disposez bien de la bande passante requise, que vous avez accès à toutes les adresses IP requises, que les ports appropriés sont ouverts et que vous respectez les performances requises pour le média en temps réel. .</span><span class="sxs-lookup"><span data-stu-id="ce284-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="ce284-163">Si vous êtes certain de ne pas répondre à ces critères, vos utilisateurs finaux ne bénéficieront pas d’une meilleure connaissance des équipes en raison d’une mauvaise qualité lors des appels et des réunions.</span><span class="sxs-lookup"><span data-stu-id="ce284-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="ce284-164">Dans le cas contraire, il s’agit du délai nécessaire pour envisagez de suspendre le projet pour vous assurer que vous répondez aux critères avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="ce284-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Icône représentant un point de décision](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="ce284-166">Point de décision</span><span class="sxs-lookup"><span data-stu-id="ce284-166">Decision Point</span></span>         |<span data-ttu-id="ce284-167">Avez-vous évalué vos capacités réseau pour la prise en charge de médias en temps réel?</span><span class="sxs-lookup"><span data-stu-id="ce284-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="ce284-168">Si votre réseau n’a pas été correctement évalué ou s’il ne prend pas en charge les contenus multimédias en temps réel, vous pouvez désactiver les fonctionnalités de partage vidéo et d’écran afin de réduire l’impact sur le réseau et de mauvaises expériences d’équipe.</span><span class="sxs-lookup"><span data-stu-id="ce284-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Icône représentant les étapes suivantes](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="ce284-170">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ce284-170">Next Steps</span></span>         |<span data-ttu-id="ce284-171">Qualité du réseau inconnue: effectuez une analyse de compatibilité réseau pour déterminer si votre réseau est prêt pour le média en temps réel.</span><span class="sxs-lookup"><span data-stu-id="ce284-171">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="ce284-172">Qualité du réseau médiocre: suivez les étapes de la reconversion réseau pour proposer un environnement approprié pour le média en temps réel de haute qualité.</span><span class="sxs-lookup"><span data-stu-id="ce284-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="ce284-173">Réseau satisfaisant: Assurez-vous que toutes les adresses IP et tous les ports sont accessibles correctement.</span><span class="sxs-lookup"><span data-stu-id="ce284-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="ce284-174">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ce284-174">Related Topics</span></span>

[<span data-ttu-id="ce284-175">Vidéo: planification du réseau</span><span class="sxs-lookup"><span data-stu-id="ce284-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
