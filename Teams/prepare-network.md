---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
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
ms.openlocfilehash: c45845a99b9e1684339699a67fbfa46118cb50dd
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461451"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="2e512-104">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e512-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="2e512-105">Regarder la session suivante pour en savoir comment les équipes s’appuie sur votre réseau et comment mieux planifier la connectivité réseau optimale : [Planification des équipes réseau](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="2e512-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="2e512-106">Teams associe trois types de trafic :</span><span class="sxs-lookup"><span data-stu-id="2e512-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="2e512-107">le trafic de données entre l'environnement en ligne Office 365 et le client Teams (signalisation, présence, conversation, chargement et téléchargement de fichiers, synchronisation OneNote) ;</span><span class="sxs-lookup"><span data-stu-id="2e512-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="2e512-108">le trafic des communications P2P en temps réel (audio, vidéo, partage de bureau) ;</span><span class="sxs-lookup"><span data-stu-id="2e512-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="2e512-109">le trafic des communications de conférence en temps réel (audio, vidéo, partage de bureau).</span><span class="sxs-lookup"><span data-stu-id="2e512-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="2e512-p102">Cela affecte le réseau sur deux niveaux : le trafic est acheminé entre les clients Microsoft Teams directement pour les communications P2P et le trafic est acheminé entre l'environnement Office 365 et les clients Microsoft Teams dans le cas des réunions. Pour assurer un flux optimal, le trafic doit pouvoir être acheminé à la fois entre les segments réseau (par ex. : entre des sites sur le réseau WAN) et entre les sites réseau et Office 365. Si les ports appropriés ne sont pas ouverts ou que des ports spécifiques sont activement bloqués, cela risque de dégrader la qualité de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="2e512-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="2e512-113">Les réunions sont pris en charge sur iOS et Android appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="2e512-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="2e512-114">Pour bénéficier d'une expérience optimale avec le multimédia en temps réel dans Microsoft Teams, la configuration réseau requise pour Office 365 doit être satisfaite.</span><span class="sxs-lookup"><span data-stu-id="2e512-114">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="2e512-115">Pour plus d’informations, consultez la rubique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="2e512-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="2e512-116">Pour les deux définition segments réseau (Client pour Microsoft Edge) et côté client pour Microsoft Edge, tenez compte des recommandations suivantes.</span><span class="sxs-lookup"><span data-stu-id="2e512-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="2e512-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="2e512-117">Value</span></span>  |<span data-ttu-id="2e512-118">Client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2e512-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="2e512-119">Périphérie client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2e512-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="2e512-120">**Latence (unidirectionnelle)** \*</span><span class="sxs-lookup"><span data-stu-id="2e512-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="2e512-121">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="2e512-121">< 50ms</span></span>          |<span data-ttu-id="2e512-122">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="2e512-122">< 30ms</span></span>         |
|<span data-ttu-id="2e512-123">**Latence (RTT or durée de l'aller-retour)** \*</span><span class="sxs-lookup"><span data-stu-id="2e512-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="2e512-124">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="2e512-124">< 100ms</span></span>   |<span data-ttu-id="2e512-125">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="2e512-125">< 60ms</span></span> |
|<span data-ttu-id="2e512-126">**Perte de paquets en rafale**</span><span class="sxs-lookup"><span data-stu-id="2e512-126">**Burst packet loss**</span></span>    |<span data-ttu-id="2e512-127">< 10 % sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="2e512-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="2e512-128">< 1% sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="2e512-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="2e512-129">**Perte de paquets**</span><span class="sxs-lookup"><span data-stu-id="2e512-129">**Packet loss**</span></span>     |<span data-ttu-id="2e512-130">< 1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="2e512-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="2e512-131">< 0,1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="2e512-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="2e512-132">**Gigue entre les arrivées de paquets**</span><span class="sxs-lookup"><span data-stu-id="2e512-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="2e512-133">< 30 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="2e512-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="2e512-134">< 15 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="2e512-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="2e512-135">**Réorganisation des paquets**</span><span class="sxs-lookup"><span data-stu-id="2e512-135">**Packet reorder**</span></span>    |<span data-ttu-id="2e512-136">< 0,05 % paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="2e512-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="2e512-137">< 0,01% paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="2e512-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="2e512-138">\*Les cibles de métrique latence supposent que votre entreprise ou les sites et les bords de Microsoft sont sur le même continent.</span><span class="sxs-lookup"><span data-stu-id="2e512-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="2e512-139">Connexion au site votre société et le bord du réseau Microsoft inclut premier accès tronçon réseau, qui peut être Wi-Fi ou une autre technologie sans fil.</span><span class="sxs-lookup"><span data-stu-id="2e512-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="2e512-140">Les objectifs de performances réseau supposent que la bande passante appropriée et/ou de [planification QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="2e512-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="2e512-141">En d’autres termes, les conditions s’appliquent directement à du trafic multimédia en temps réel équipes lorsque la connexion réseau est soumis à une charge maximale.</span><span class="sxs-lookup"><span data-stu-id="2e512-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="2e512-142">Pour tester les deux segments réseau, vous pouvez utiliser l’[Outil d'évaluation du réseau](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="2e512-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="2e512-143">Cet outil peut être déployé sur le PC client directement et sur un PC connecté au périphérique réseau client.</span><span class="sxs-lookup"><span data-stu-id="2e512-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="2e512-144">Il inclut une documentation restreinte, mais une documentation plus approfondie concernant l’utilisation de l’outil est disponible ici : [Évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="2e512-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="2e512-145">En exécutant cet outil d’évaluation de la préparation du réseau, vous pouvez valider la préparation de votre réseau à exécuter des applications multimédias en temps réel telles que Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2e512-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="2e512-146">Il s'agit de la même évaluation de disponibilité réseau recommandée pour les clients qui souhaitent déployer correctement Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="2e512-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="2e512-147">Condition requise pour la bande passante</span><span class="sxs-lookup"><span data-stu-id="2e512-147">Bandwidth requirements</span></span>

<span data-ttu-id="2e512-148">Les calculs de bande passante pour Microsoft Teams sont complexes et une calculatrice a été créée à cet effet.</span><span class="sxs-lookup"><span data-stu-id="2e512-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="2e512-149">Pour accéder à la Calculatrice, accédez au [Planificateur réseau](https://aka.ms/bwcalc/) dans MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="2e512-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="2e512-150">Améliore la gestion de bande passante équipes sur Skype pour Business Online : pour une haute qualité appelant ou l’expérience (audio, vidéo et partage) de la réunion, les équipes nécessite uniquement 1,2 Mbits/s.</span><span class="sxs-lookup"><span data-stu-id="2e512-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="2e512-151">Il peut également évoluer davantage de très haute qualité s’il existe suffisamment de bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="2e512-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="2e512-152">Lorsqu’une demande d’équipes rencontre une condition de faible bande passante, les équipes peuvent rapidement Ajustez à nouveau l’utilisation de la bande passante pour s’adapter à la bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="2e512-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="2e512-153">Remarques supplémentaires relatives au réseau</span><span class="sxs-lookup"><span data-stu-id="2e512-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="2e512-154">Résolution des noms externes</span><span class="sxs-lookup"><span data-stu-id="2e512-154">External Name Resolution</span></span>

<span data-ttu-id="2e512-155">Assurez-vous que tous les ordinateurs clients exécutant les équipes client peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365, et que votre pare-feu empêchent pas l’accès.</span><span class="sxs-lookup"><span data-stu-id="2e512-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="2e512-156">Pour plus d’informations sur la configuration des ports de pare-feu, accédez à [Office 365 URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="2e512-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="2e512-157">Taille du pool NAT</span><span class="sxs-lookup"><span data-stu-id="2e512-157">NAT Pool Size</span></span>

<span data-ttu-id="2e512-158">Lorsque plusieurs utilisateurs/appareils accèdent à Office 365 à l'aide de la traduction d'adresses réseau (NAT) ou de la traduction d'adresses de port (PAT), vous devez vous assurer que les appareils placés derrière chaque adresse IP publiquement routable n'excèdent pas le nombre pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2e512-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="2e512-159">Pour atténuer ce risque, assurez-vous que les adresses IP publiques adéquates sont affectées aux pools NAT pour éviter toute insuffisance de ports.</span><span class="sxs-lookup"><span data-stu-id="2e512-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="2e512-160">Si les ports sont insuffisants, les utilisateurs finaux internes et les périphériques rencontreront des problèmes lorsqu'ils se connecteront aux services Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e512-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="2e512-161">Pour plus d’informations, consultez la rubrique [Prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="2e512-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="2e512-162">**Instructions pour la détection et la prévention d'intrusion**</span><span class="sxs-lookup"><span data-stu-id="2e512-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="2e512-163">Si votre environnement disposent d'un système de détection et/ou de prévention d'intrusion (IDS/IPS) déployé pour obtenir une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout trafic vers des URL Office 365 est placé sur liste verte.</span><span class="sxs-lookup"><span data-stu-id="2e512-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="2e512-164">Détermination de l'intégrité réseau</span><span class="sxs-lookup"><span data-stu-id="2e512-164">Network health determination</span></span>
-----------------

<span data-ttu-id="2e512-165">Lors de la planification de l'implémentation de Microsoft Teams dans votre réseau, vous devez vous assurer de disposer de la bande passante requise, d'avoir accès à toutes les adresses IP requises, que les ports corrects sont ouverts et que les conditions requises en matière de performances pour le multimédia en temps réel sont respectées.</span><span class="sxs-lookup"><span data-stu-id="2e512-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="2e512-166">Si ces critères ne sont pas satisfaits, vos utilisateurs finaux ne bénéficieront pas d'une expérience optimale de Teams en raison de la mauvaise qualité pendant les appels et les réunions.</span><span class="sxs-lookup"><span data-stu-id="2e512-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="2e512-167">Si les critères ne sont pas remplis, il convient d'interrompre le projet pour vous assurer de satisfaire les critères avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="2e512-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="2e512-169">Point de décision</span><span class="sxs-lookup"><span data-stu-id="2e512-169">Decision Point</span></span>         |<span data-ttu-id="2e512-170">Avez-vous évalué les capacités de votre réseau pour la prise en charge multimédia en temps réel ?</span><span class="sxs-lookup"><span data-stu-id="2e512-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="2e512-171">Si votre réseau n'est pas correctement évalué ou que vous êtes conscient qu'il ne prendra pas en charge le trafic multimédia en temps réel, désactiverez-vous les fonctionnalités vidéo et de partage d'écran pour limiter l'impact sur le réseau et la qualité médiocre de l'expérience avec Teams ?</span><span class="sxs-lookup"><span data-stu-id="2e512-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Icône Étapes suivantes.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="2e512-173">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="2e512-173">Next Steps</span></span>         |<span data-ttu-id="2e512-174">Qualité réseau inconnue : suivez les instructions sur [l’évaluation de la préparation du réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) pour déterminer si votre réseau est préparé pour le trafic multimédia en temps réel.</span><span class="sxs-lookup"><span data-stu-id="2e512-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="2e512-175">Qualité réseau médiocre : Réalisez les étapes de correction du réseau pour mettre à disposition un environnement adéquat pour le trafic multimédia en temps réel de haute qualité.</span><span class="sxs-lookup"><span data-stu-id="2e512-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="2e512-176">Réseau satisfaisant : Vérifiez que l'ensemble des adresses IP et des ports sont accessibles.</span><span class="sxs-lookup"><span data-stu-id="2e512-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="2e512-177">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2e512-177">Related Topics</span></span>

[<span data-ttu-id="2e512-178">Vidéo : Planification du réseau</span><span class="sxs-lookup"><span data-stu-id="2e512-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)