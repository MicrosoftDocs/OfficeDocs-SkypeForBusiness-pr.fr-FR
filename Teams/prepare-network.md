---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
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
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640729"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="eb6a4-104">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb6a4-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="eb6a4-105">Regarder la session suivante pour en savoir comment les équipes s’appuie sur votre réseau et comment mieux planifier la connectivité réseau optimale : [Planification des équipes réseau](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="eb6a4-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="eb6a4-106">Les équipes combine les trois formes du trafic :</span><span class="sxs-lookup"><span data-stu-id="eb6a4-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="eb6a4-107">Trafic de données entre l’environnement en ligne d’Office 365 et le client équipes (signalisation, présence, conversation, téléchargement de fichier et téléchargement, la synchronisation de OneNote).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="eb6a4-108">Trafic de communications en temps réel d’égal à égal (partage de bureau, vidéo et audio).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="eb6a4-109">Trafic de communication en temps réel de conférence (audio, vidéo, bureau partage).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="eb6a4-110">Cela a un impact sur le réseau à deux niveaux : flux de trafic entre les clients Microsoft Teams directement pour les scénarios d’égal à égal et passera le trafic entre l’environnement Office 365 et les clients Microsoft Teams pour les scénarios de réunion.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="eb6a4-111">Pour vérifier le flux de trafic optimales, le trafic doit être autorisé à circuler entre les segments réseau interne (par exemple, entre les sites sur le WAN) ainsi qu’entre les sites réseau et Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="eb6a4-112">Une expérience de dégradé n’entraîne pas ouvrir les ports corrects ou activement le blocage des ports spécifiques.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="eb6a4-113">Les réunions sont pris en charge sur iOS et Android appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="eb6a4-114">Pour obtenir une expérience optimale avec support en temps réel dans Microsoft Teams, votre réseau doit satisfaire la configuration réseau requise pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-114">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="eb6a4-115">Pour plus d’informations, voir [la qualité des médias et des performances pour la connectivité réseau pour Skype pour Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="eb6a4-116">Pour les deux définition segments réseau (Client pour Microsoft Edge) et côté client pour Microsoft Edge, tenez compte des recommandations suivantes.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="eb6a4-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="eb6a4-117">Value</span></span>  |<span data-ttu-id="eb6a4-118">Client Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eb6a4-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="eb6a4-119">Côté client pour Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eb6a4-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="eb6a4-120">**Latence (unidirectionnelle)**\*</span><span class="sxs-lookup"><span data-stu-id="eb6a4-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="eb6a4-121">< aller-retour de 50 millisecondes</span><span class="sxs-lookup"><span data-stu-id="eb6a4-121">< 50ms</span></span>          |<span data-ttu-id="eb6a4-122">< 30ms</span><span class="sxs-lookup"><span data-stu-id="eb6a4-122">< 30ms</span></span>         |
|<span data-ttu-id="eb6a4-123">**Latence (durée aller-retour ou temps d’aller-retour)**\*</span><span class="sxs-lookup"><span data-stu-id="eb6a4-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="eb6a4-124">< 100 millisecondes</span><span class="sxs-lookup"><span data-stu-id="eb6a4-124">< 100ms</span></span>   |<span data-ttu-id="eb6a4-125">< 60 MS</span><span class="sxs-lookup"><span data-stu-id="eb6a4-125">< 60ms</span></span> |
|<span data-ttu-id="eb6a4-126">**Perte de paquets en rafale**</span><span class="sxs-lookup"><span data-stu-id="eb6a4-126">**Burst packet loss**</span></span>    |<span data-ttu-id="eb6a4-127"><10 % au cours de l’intervalle de 200 MS</span><span class="sxs-lookup"><span data-stu-id="eb6a4-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="eb6a4-128"><1 % au cours de l’intervalle de 200 MS</span><span class="sxs-lookup"><span data-stu-id="eb6a4-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="eb6a4-129">**Perte de paquets**</span><span class="sxs-lookup"><span data-stu-id="eb6a4-129">**Packet loss**</span></span>     |<span data-ttu-id="eb6a4-130"><1 % au cours des 15 s intervalle</span><span class="sxs-lookup"><span data-stu-id="eb6a4-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="eb6a4-131"><0.1% pendant les 15 s intervalle</span><span class="sxs-lookup"><span data-stu-id="eb6a4-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="eb6a4-132">**Gigue arrivée entre des batteries de paquets**</span><span class="sxs-lookup"><span data-stu-id="eb6a4-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="eb6a4-133"><30ms pendant les 15 s intervalle</span><span class="sxs-lookup"><span data-stu-id="eb6a4-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="eb6a4-134"><15ms pendant les 15 s intervalle</span><span class="sxs-lookup"><span data-stu-id="eb6a4-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="eb6a4-135">**Réorganisation des paquets**</span><span class="sxs-lookup"><span data-stu-id="eb6a4-135">**Packet reorder**</span></span>    |<span data-ttu-id="eb6a4-136">paquets d’ordre <0.05%</span><span class="sxs-lookup"><span data-stu-id="eb6a4-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="eb6a4-137">paquets d’ordre <0.01%</span><span class="sxs-lookup"><span data-stu-id="eb6a4-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="eb6a4-138">\*Les cibles de métrique latence supposent que votre entreprise ou les sites et les bords de Microsoft sont sur le même continent.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="eb6a4-139">Connexion au site votre société et le bord du réseau Microsoft inclut premier accès tronçon réseau, qui peut être Wi-Fi ou une autre technologie sans fil.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="eb6a4-140">Les objectifs de performances réseau supposent que la bande passante appropriée et/ou de [planification QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="eb6a4-141">En d’autres termes, les conditions s’appliquent directement à du trafic multimédia en temps réel équipes lorsque la connexion réseau est soumis à une charge maximale.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="eb6a4-142">Pour tester les deux segments réseau, vous pouvez utiliser l' [Outil d’évaluation de réseau](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="eb6a4-143">Cet outil peut être déployé sur le client PC directement et sur un PC connecté à la périphérie du réseau client.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="eb6a4-144">L’outil comprend une documentation limitée, mais une documentation plue autour de l’utilisation de l’outil se trouvent ici : [Évaluation de préparation de réseau](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="eb6a4-145">En exécutant cette évaluation de préparation du réseau, vous pouvez valider la préparation de votre réseau d’exécuter des applications multimédia en temps réel, tels que Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="eb6a4-146">Il s’agit de l’évaluation de préparation même réseau qui est recommandé d’exécuter pour les clients qui souhaitent pour déployer Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="eb6a4-147">Bande passante requise</span><span class="sxs-lookup"><span data-stu-id="eb6a4-147">Bandwidth requirements</span></span>

<span data-ttu-id="eb6a4-148">Calculs de bande passante pour Microsoft Teams sont complexes et pour aider, une calculatrice a été créée.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="eb6a4-149">Pour accéder à la Calculatrice, accédez au [Planificateur réseau](https://aka.ms/bwcalc/) dans MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="eb6a4-150">Améliore la gestion de bande passante équipes sur Skype pour Business Online : pour une haute qualité appelant ou l’expérience (audio, vidéo et partage) de la réunion, les équipes nécessite uniquement 1,2 Mbits/s.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="eb6a4-151">Il peut également évoluer davantage de très haute qualité s’il existe suffisamment de bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="eb6a4-152">Lorsqu’une demande d’équipes rencontre une condition de faible bande passante, les équipes peuvent rapidement Ajustez à nouveau l’utilisation de la bande passante pour s’adapter à la bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="eb6a4-153">Considérations relatives au réseau supplémentaires</span><span class="sxs-lookup"><span data-stu-id="eb6a4-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="eb6a4-154">Résolution de nom externe</span><span class="sxs-lookup"><span data-stu-id="eb6a4-154">External Name Resolution</span></span>

<span data-ttu-id="eb6a4-155">Assurez-vous que tous les ordinateurs clients exécutant les équipes client peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365, et que votre pare-feu empêchent pas l’accès.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="eb6a4-156">Pour plus d’informations sur la configuration des ports de pare-feu, accédez à [Office 365 URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="eb6a4-157">Taille du Pool de NAT</span><span class="sxs-lookup"><span data-stu-id="eb6a4-157">NAT Pool Size</span></span>

<span data-ttu-id="eb6a4-158">Lorsque plusieurs utilisateurs/périphériques accéder à Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou la traduction d’adresse de Port (PAT), vous devez vous assurer que les périphériques derrière chaque adresse IP routable publiquement ne dépassent pas le nombre pris en charge.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="eb6a4-159">Pour atténuer ce risque, assurez-vous adéquate des adresses IP publiques sont affectés aux pools de NAT pour éviter l’épuisement du port.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="eb6a4-160">Épuisement port entraînera interne aux utilisateurs et des périphériques de face problèmes lors de la connexion aux services Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="eb6a4-161">Pour plus d’informations, voir [prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="eb6a4-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="eb6a4-162">**Détection d’intrusion et des conseils de prévention**</span><span class="sxs-lookup"><span data-stu-id="eb6a4-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="eb6a4-163">Si votre environnement comporte un système de prévention (intrusion) déployés pour un niveau supplémentaire de sécurité pour les connexions sortantes et/ou de détection d’Intrusion, vérifiez que tout le trafic à destination vers Office 365 URL autorisés.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="eb6a4-164">Détermination de l’intégrité de réseau</span><span class="sxs-lookup"><span data-stu-id="eb6a4-164">Network health determination</span></span>
-----------------

<span data-ttu-id="eb6a4-165">Lors de la planification de l’implémentation de Teams Microsoft au sein de votre réseau, vous devez vous assurer que la bande passante requise, vous avez accès à toutes les adresses IP requises, les ports corrects sont ouverts, et vous respectent les exigences de performances pour les médias en temps réel .</span><span class="sxs-lookup"><span data-stu-id="eb6a4-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="eb6a4-166">Si vous savez que vous ne respecte pas ces critères, vos utilisateurs finaux pas obtiendrez une expérience optimale des équipes en raison de la mauvaise qualité durant des réunions et appels.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="eb6a4-167">Doivent pas répondre aux critères, c’est à la fois à prendre en compte l’interruption du projet afin de que vous répondent aux critères avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="eb6a4-169">Point de décision</span><span class="sxs-lookup"><span data-stu-id="eb6a4-169">Decision Point</span></span>         |<span data-ttu-id="eb6a4-170">Avez-vous évalué vos fonctionnalités de réseau pour la prise en charge multimédia en temps réel ?</span><span class="sxs-lookup"><span data-stu-id="eb6a4-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="eb6a4-171">Si votre réseau n’a pas été correctement évalué ou si vous savez qu’il ne prendra pas en charge multimédia en temps réel, vous désactivera vidéo et les capacités pour réduire l’impact sur le réseau et une mauvaise expérience équipes de partage d’écran ?</span><span class="sxs-lookup"><span data-stu-id="eb6a4-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Icône Étapes suivantes.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="eb6a4-173">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="eb6a4-173">Next Steps</span></span>         |<span data-ttu-id="eb6a4-174">Qualité du réseau inconnue : suivez les instructions de [l’Évaluation de préparation de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) pour déterminer si votre réseau est prêt pour le média en temps réel.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="eb6a4-175">Réseau qualité médiocre : Effectuez les étapes de correction de réseau pour fournir un environnement approprié pour une qualité multimédia en temps réel.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="eb6a4-176">Réseau satisfaisant : Assurez-vous que tous les ports et adresses IP sont correctement accessibles.</span><span class="sxs-lookup"><span data-stu-id="eb6a4-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="eb6a4-177">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="eb6a4-177">Related Topics</span></span>

[<span data-ttu-id="eb6a4-178">Vidéo : Planification du réseau</span><span class="sxs-lookup"><span data-stu-id="eb6a4-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)