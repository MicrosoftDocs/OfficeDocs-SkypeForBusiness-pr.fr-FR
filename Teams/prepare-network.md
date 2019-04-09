---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
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
ms.openlocfilehash: cf48da12ddd1088c499f9d0703dc229d5b5df605
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31516790"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="93dc5-104">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="93dc5-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="93dc5-105">Teams associe trois types de trafic :</span><span class="sxs-lookup"><span data-stu-id="93dc5-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="93dc5-106">le trafic de données entre l'environnement en ligne Office 365 et le client Teams (signalisation, présence, conversation, chargement et téléchargement de fichiers, synchronisation OneNote) ;</span><span class="sxs-lookup"><span data-stu-id="93dc5-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="93dc5-107">le trafic des communications P2P en temps réel (audio, vidéo, partage de bureau) ;</span><span class="sxs-lookup"><span data-stu-id="93dc5-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="93dc5-108">le trafic des communications de conférence en temps réel (audio, vidéo, partage de bureau).</span><span class="sxs-lookup"><span data-stu-id="93dc5-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="93dc5-p102">Cela affecte le réseau sur deux niveaux : le trafic est acheminé entre les clients Microsoft Teams directement pour les communications P2P et le trafic est acheminé entre l'environnement Office 365 et les clients Microsoft Teams dans le cas des réunions. Pour assurer un flux optimal, le trafic doit pouvoir être acheminé à la fois entre les segments réseau (par ex. : entre des sites sur le réseau WAN) et entre les sites réseau et Office 365. Si les ports appropriés ne sont pas ouverts ou que des ports spécifiques sont activement bloqués, cela risque de dégrader la qualité de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="93dc5-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="93dc5-112">Les réunions sont pris en charge sur iOS et Android appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="93dc5-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="93dc5-113">Pour obtenir une expérience optimale avec support en temps réel dans Microsoft Teams, votre réseau doit satisfaire la configuration réseau requise pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="93dc5-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="93dc5-114">Pour plus d’informations, consultez la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="93dc5-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="93dc5-115">Les deux segments réseau de définition (client vers Microsoft Edge et côté client vers Microsoft Edge) doivent respecter la configuration requise suivante.</span><span class="sxs-lookup"><span data-stu-id="93dc5-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="93dc5-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="93dc5-116">Value</span></span>  |<span data-ttu-id="93dc5-117">Client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="93dc5-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="93dc5-118">Périphérie client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="93dc5-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="93dc5-119">**Latence (unidirectionnelle)**\*</span><span class="sxs-lookup"><span data-stu-id="93dc5-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="93dc5-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="93dc5-120">< 50ms</span></span>          |<span data-ttu-id="93dc5-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="93dc5-121">< 30ms</span></span>         |
|<span data-ttu-id="93dc5-122">**Latence (durée aller-retour ou temps d’aller-retour)**\*</span><span class="sxs-lookup"><span data-stu-id="93dc5-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="93dc5-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="93dc5-123">< 100ms</span></span>   |<span data-ttu-id="93dc5-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="93dc5-124">< 60ms</span></span> |
|<span data-ttu-id="93dc5-125">**Perte de paquets en rafale**</span><span class="sxs-lookup"><span data-stu-id="93dc5-125">**Burst packet loss**</span></span>    |<span data-ttu-id="93dc5-126">< 10 % sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="93dc5-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="93dc5-127">< 1% sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="93dc5-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="93dc5-128">**Perte de paquets**</span><span class="sxs-lookup"><span data-stu-id="93dc5-128">**Packet loss**</span></span>     |<span data-ttu-id="93dc5-129">< 1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="93dc5-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="93dc5-130">< 0,1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="93dc5-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="93dc5-131">**Gigue entre les arrivées de paquets**</span><span class="sxs-lookup"><span data-stu-id="93dc5-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="93dc5-132">< 30 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="93dc5-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="93dc5-133">< 15 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="93dc5-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="93dc5-134">**Réorganisation des paquets**</span><span class="sxs-lookup"><span data-stu-id="93dc5-134">**Packet reorder**</span></span>    |<span data-ttu-id="93dc5-135">< 0,05 % paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="93dc5-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="93dc5-136">< 0,01% paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="93dc5-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="93dc5-137">\*Les cibles de métrique latence supposent que votre entreprise ou les sites et les bords de Microsoft sont sur le même continent.</span><span class="sxs-lookup"><span data-stu-id="93dc5-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="93dc5-138">Connexion au site votre société et le bord du réseau Microsoft inclut premier accès tronçon réseau, qui peut être Wi-Fi ou une autre technologie sans fil.</span><span class="sxs-lookup"><span data-stu-id="93dc5-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="93dc5-139">Les objectifs de performances réseau supposent que la bande passante appropriée et/ou de [planification QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="93dc5-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="93dc5-140">En d’autres termes, les conditions s’appliquent directement à du trafic multimédia en temps réel équipes lorsque la connexion réseau est soumis à une charge maximale.</span><span class="sxs-lookup"><span data-stu-id="93dc5-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="93dc5-141">Pour tester les deux segments réseau, vous pouvez utiliser l' [Outil d’évaluation de réseau](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="93dc5-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="93dc5-142">Cet outil peut être déployé sur le client PC directement et sur un PC connecté à la périphérie du réseau client.</span><span class="sxs-lookup"><span data-stu-id="93dc5-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="93dc5-143">L’outil comprend une documentation limitée, mais une documentation plue autour de l’utilisation de l’outil se trouvent ici : [Évaluation de préparation de réseau](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="93dc5-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="93dc5-144">En exécutant cette évaluation de préparation du réseau, vous pouvez valider la préparation de votre réseau d’exécuter des applications multimédia en temps réel, tels que Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="93dc5-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="93dc5-145">Il s’agit de l’évaluation de préparation même réseau qui est recommandé d’exécuter pour les clients qui souhaitent pour déployer Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="93dc5-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="93dc5-146">Bande passante requise</span><span class="sxs-lookup"><span data-stu-id="93dc5-146">Bandwidth requirements</span></span>
<span data-ttu-id="93dc5-147">Teams Microsoft offre les meilleures audio, vidéo et contenu expérience indépendamment de vos conditions réseau.</span><span class="sxs-lookup"><span data-stu-id="93dc5-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="93dc5-148">Avec les codecs variables, média peut être négocié dans les environnements de bande passante limitée avec un impact minimal.</span><span class="sxs-lookup"><span data-stu-id="93dc5-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="93dc5-149">Mais où la bande passante n’est pas un problème, une expérience peut être optimisée pour la qualité, y compris des résolution vidéo 1080p, jusqu'à 30 i/s pour la vidéo et 15 i/s pour le contenu et les paramètres audio haute fidélité.</span><span class="sxs-lookup"><span data-stu-id="93dc5-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="93dc5-150">Considérations relatives au réseau supplémentaires</span><span class="sxs-lookup"><span data-stu-id="93dc5-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="93dc5-151">Résolution de nom externe</span><span class="sxs-lookup"><span data-stu-id="93dc5-151">External Name Resolution</span></span>

<span data-ttu-id="93dc5-152">Assurez-vous que tous les ordinateurs clients exécutant les équipes client peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365, et que votre pare-feu empêchent pas l’accès.</span><span class="sxs-lookup"><span data-stu-id="93dc5-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="93dc5-153">Pour plus d’informations sur la configuration des ports de pare-feu, accédez à [Office 365 URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="93dc5-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="93dc5-154">Taille du Pool de NAT</span><span class="sxs-lookup"><span data-stu-id="93dc5-154">NAT Pool Size</span></span>

<span data-ttu-id="93dc5-155">Lorsque plusieurs utilisateurs/périphériques accéder à Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou la traduction d’adresse de Port (PAT), vous devez vous assurer que les périphériques derrière chaque adresse IP routable publiquement ne dépassent pas le nombre pris en charge.</span><span class="sxs-lookup"><span data-stu-id="93dc5-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="93dc5-156">Pour atténuer ce risque, assurez-vous adéquate des adresses IP publiques sont affectés aux pools de NAT pour éviter l’épuisement du port.</span><span class="sxs-lookup"><span data-stu-id="93dc5-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="93dc5-157">Épuisement port entraînera interne aux utilisateurs et des périphériques de face problèmes lors de la connexion aux services Office 365.</span><span class="sxs-lookup"><span data-stu-id="93dc5-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="93dc5-158">Pour plus d’informations, voir [prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="93dc5-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="93dc5-159">**Détection d’intrusion et des conseils de prévention**</span><span class="sxs-lookup"><span data-stu-id="93dc5-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="93dc5-160">Si votre environnement comporte un système de prévention (intrusion) déployés pour un niveau supplémentaire de sécurité pour les connexions sortantes et/ou de détection d’Intrusion, vérifiez que tout le trafic à destination vers Office 365 URL autorisés.</span><span class="sxs-lookup"><span data-stu-id="93dc5-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="93dc5-161">Détermination de l’intégrité de réseau</span><span class="sxs-lookup"><span data-stu-id="93dc5-161">Network health determination</span></span>
-----------------

<span data-ttu-id="93dc5-162">Lors de la planification de l’implémentation de Teams Microsoft au sein de votre réseau, vous devez vous assurer que la bande passante requise, vous avez accès à toutes les adresses IP requises, les ports corrects sont ouverts, et vous respectent les exigences de performances pour les médias en temps réel .</span><span class="sxs-lookup"><span data-stu-id="93dc5-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="93dc5-163">Si vous savez que vous ne respecte pas ces critères, vos utilisateurs finaux pas obtiendrez une expérience optimale des équipes en raison de la mauvaise qualité durant des réunions et appels.</span><span class="sxs-lookup"><span data-stu-id="93dc5-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="93dc5-164">Doivent pas répondre aux critères, c’est à la fois à prendre en compte l’interruption du projet afin de que vous répondent aux critères avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="93dc5-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="93dc5-166">Point de décision</span><span class="sxs-lookup"><span data-stu-id="93dc5-166">Decision Point</span></span>         |<span data-ttu-id="93dc5-167">Avez-vous évalué vos fonctionnalités de réseau pour la prise en charge multimédia en temps réel ?</span><span class="sxs-lookup"><span data-stu-id="93dc5-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="93dc5-168">Si votre réseau n’a pas été correctement évalué ou si vous savez qu’il ne prendra pas en charge multimédia en temps réel, vous désactivera vidéo et les capacités pour réduire l’impact sur le réseau et une mauvaise expérience équipes de partage d’écran ?</span><span class="sxs-lookup"><span data-stu-id="93dc5-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Icône Étapes suivantes.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="93dc5-170">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="93dc5-170">Next Steps</span></span>         |<span data-ttu-id="93dc5-171">Qualité du réseau inconnue : suivez les instructions de [l’Évaluation de préparation de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) pour déterminer si votre réseau est prêt pour le média en temps réel.</span><span class="sxs-lookup"><span data-stu-id="93dc5-171">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="93dc5-172">Réseau qualité médiocre : Effectuez les étapes de correction de réseau pour fournir un environnement approprié pour une qualité multimédia en temps réel.</span><span class="sxs-lookup"><span data-stu-id="93dc5-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="93dc5-173">Réseau satisfaisant : Assurez-vous que tous les ports et adresses IP sont correctement accessibles.</span><span class="sxs-lookup"><span data-stu-id="93dc5-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="93dc5-174">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="93dc5-174">Related Topics</span></span>

[<span data-ttu-id="93dc5-175">Vidéo : Planification du réseau</span><span class="sxs-lookup"><span data-stu-id="93dc5-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
