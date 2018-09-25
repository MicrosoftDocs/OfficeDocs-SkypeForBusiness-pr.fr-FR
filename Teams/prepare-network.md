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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40250062b5439726fa1a0d7f886ba99e71a2060a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014506"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="bb1e4-104">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb1e4-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="bb1e4-105">Teams associe trois types de trafic :</span><span class="sxs-lookup"><span data-stu-id="bb1e4-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="bb1e4-106">le trafic de données entre l'environnement en ligne Office 365 et le client Teams (signalisation, présence, conversation, chargement et téléchargement de fichiers, synchronisation OneNote) ;</span><span class="sxs-lookup"><span data-stu-id="bb1e4-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="bb1e4-107">le trafic des communications P2P en temps réel (audio, vidéo, partage de bureau) ;</span><span class="sxs-lookup"><span data-stu-id="bb1e4-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="bb1e4-108">le trafic des communications de conférence en temps réel (audio, vidéo, partage de bureau).</span><span class="sxs-lookup"><span data-stu-id="bb1e4-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="bb1e4-p102">Cela affecte le réseau sur deux niveaux : le trafic est acheminé entre les clients Microsoft Teams directement pour les communications P2P et le trafic est acheminé entre l'environnement Office 365 et les clients Microsoft Teams dans le cas des réunions. Pour assurer un flux optimal, le trafic doit pouvoir être acheminé à la fois entre les segments réseau (par ex. : entre des sites sur le réseau WAN) et entre les sites réseau et Office 365. Si les ports appropriés ne sont pas ouverts ou que des ports spécifiques sont activement bloqués, cela risque de dégrader la qualité de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb1e4-112">Les réunions sont actuellement prises en charge sur les appareils iOS et Android, mais pas sur les appareils Windows.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone.</span></span>

<span data-ttu-id="bb1e4-113">Pour bénéficier d'une expérience optimale avec le multimédia en temps réel dans Microsoft Teams, la configuration réseau requise pour Office 365 doit être satisfaite.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="bb1e4-114">Pour plus d’informations, consultez la rubique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="bb1e4-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="bb1e4-115">Les deux segments réseau de définition (client vers Microsoft Edge et côté client vers Microsoft Edge) doivent respecter la configuration requise suivante.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="bb1e4-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="bb1e4-116">Value</span></span>  |<span data-ttu-id="bb1e4-117">Client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bb1e4-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="bb1e4-118">Périphérie client vers Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bb1e4-118">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bb1e4-119">**Latence (unidirectionnelle)**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-119">**Latency (one way)**</span></span>     |<span data-ttu-id="bb1e4-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="bb1e4-120">< 50ms</span></span>          |<span data-ttu-id="bb1e4-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="bb1e4-121">< 30ms</span></span>          |
|<span data-ttu-id="bb1e4-122">**Latence (RTT or durée de l'aller-retour)**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-122">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="bb1e4-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="bb1e4-123">< 100ms</span></span>         |<span data-ttu-id="bb1e4-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="bb1e4-124">< 60ms</span></span>         |
|<span data-ttu-id="bb1e4-125">**Perte de paquets en rafale**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-125">**Burst packet loss**</span></span>    |<span data-ttu-id="bb1e4-126">< 10 % sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="bb1e4-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="bb1e4-127">< 1% sur un intervalle de 200 ms</span><span class="sxs-lookup"><span data-stu-id="bb1e4-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="bb1e4-128">**Perte de paquets**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-128">**Packet loss**</span></span>     |<span data-ttu-id="bb1e4-129">< 1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="bb1e4-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="bb1e4-130">< 0,1 % sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="bb1e4-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="bb1e4-131">**Gigue entre les arrivées de paquets**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="bb1e4-132">< 30 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="bb1e4-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="bb1e4-133">< 15 ms sur un intervalle de 15 s</span><span class="sxs-lookup"><span data-stu-id="bb1e4-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="bb1e4-134">**Réorganisation des paquets**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-134">**Packet reorder**</span></span>    |<span data-ttu-id="bb1e4-135">< 0,05 % paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="bb1e4-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="bb1e4-136">< 0,01% paquets désorganisés</span><span class="sxs-lookup"><span data-stu-id="bb1e4-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="bb1e4-137">Pour tester les deux segments réseau, vous pouvez utiliser l’[Outil d'évaluation du réseau](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="bb1e4-137">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="bb1e4-138">Cet outil peut être déployé sur le PC client directement et sur un PC connecté au périphérique réseau client.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-138">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="bb1e4-139">Il inclut une documentation restreinte, mais une documentation plus approfondie concernant l’utilisation de l’outil est disponible ici : [Évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="bb1e4-139">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="bb1e4-140">En exécutant cet outil d’évaluation de la préparation du réseau, vous pouvez valider la préparation de votre réseau à exécuter des applications multimédias en temps réel telles que Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-140">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="bb1e4-141">Il s'agit de la même évaluation de disponibilité réseau recommandée pour les clients qui souhaitent déployer correctement Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-141">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="bb1e4-142">Condition requise pour la bande passante</span><span class="sxs-lookup"><span data-stu-id="bb1e4-142">Bandwidth requirements</span></span>
----------

<span data-ttu-id="bb1e4-143">Les calculs de bande passante pour Microsoft Teams sont complexes et une calculatrice a été créée à cet effet.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-143">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="bb1e4-144">Pour accéder à la calculatrice, cliquez ici : [Planificateur de réseau dans MyAdvisor](https://aka.ms/bwcalc/).</span><span class="sxs-lookup"><span data-stu-id="bb1e4-144">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="bb1e4-145">Remarques supplémentaires relatives au réseau</span><span class="sxs-lookup"><span data-stu-id="bb1e4-145">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="bb1e4-146">**Résolution des noms externes**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-146">**External Name Resolution**</span></span>

<span data-ttu-id="bb1e4-147">Assurez-vous que tous les ordinateurs client exécutant Teams peuvent résoudre les requêtes DNS externes pour détecter les services fournis par Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-147">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="bb1e4-148">**Taille du pool NAT**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-148">**NAT Pool Size**</span></span>

<span data-ttu-id="bb1e4-149">Lorsque plusieurs utilisateurs/appareils accèdent à Office 365 à l'aide de la traduction d'adresses réseau (NAT) ou de la traduction d'adresses de port (PAT), vous devez vous assurer que les appareils placés derrière chaque adresse IP publiquement routable n'excèdent pas le nombre pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-149">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="bb1e4-150">Pour atténuer ce risque, assurez-vous que les adresses IP publiques adéquates sont affectées aux pools NAT pour éviter toute insuffisance de ports.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-150">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="bb1e4-151">Si les ports sont insuffisants, les utilisateurs finaux internes et les périphériques rencontreront des problèmes lorsqu'ils se connecteront aux services Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-151">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="bb1e4-152">Pour plus d’informations, consultez la rubrique [Prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="bb1e4-152">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="bb1e4-153">**Instructions pour la détection et la prévention d'intrusion**</span><span class="sxs-lookup"><span data-stu-id="bb1e4-153">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="bb1e4-154">Si votre environnement disposent d'un système de détection et/ou de prévention d'intrusion (IDS/IPS) déployé pour obtenir une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout trafic vers des URL Office 365 est placé sur liste verte.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-154">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="bb1e4-155">Détermination de l'intégrité réseau</span><span class="sxs-lookup"><span data-stu-id="bb1e4-155">Network health determination</span></span>
-----------------

<span data-ttu-id="bb1e4-156">Lors de la planification de l'implémentation de Microsoft Teams dans votre réseau, vous devez vous assurer de disposer de la bande passante requise, d'avoir accès à toutes les adresses IP requises, que les ports corrects sont ouverts et que les conditions requises en matière de performances pour le multimédia en temps réel sont respectées.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-156">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="bb1e4-157">Si ces critères ne sont pas satisfaits, vos utilisateurs finaux ne bénéficieront pas d'une expérience optimale de Teams en raison de la mauvaise qualité pendant les appels et les réunions.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-157">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="bb1e4-158">Si les critères ne sont pas remplis, il convient d'interrompre le projet pour vous assurer de satisfaire les critères avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-158">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="bb1e4-160">Point de décision</span><span class="sxs-lookup"><span data-stu-id="bb1e4-160">Decision Point</span></span>         |<span data-ttu-id="bb1e4-161">Avez-vous évalué les capacités de votre réseau pour la prise en charge multimédia en temps réel ?</span><span class="sxs-lookup"><span data-stu-id="bb1e4-161">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="bb1e4-162">Si votre réseau n'est pas correctement évalué ou que vous êtes conscient qu'il ne prendra pas en charge le trafic multimédia en temps réel, désactiverez-vous les fonctionnalités vidéo et de partage d'écran pour limiter l'impact sur le réseau et la qualité médiocre de l'expérience avec Teams ?</span><span class="sxs-lookup"><span data-stu-id="bb1e4-162">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Icône Étapes suivantes.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="bb1e4-164">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="bb1e4-164">Next Steps</span></span>         |<span data-ttu-id="bb1e4-165">Qualité réseau inconnue : suivez les instructions sur [l’évaluation de la préparation du réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) pour déterminer si votre réseau est préparé pour le trafic multimédia en temps réel.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-165">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="bb1e4-166">Qualité réseau médiocre : Réalisez les étapes de correction du réseau pour mettre à disposition un environnement adéquat pour le trafic multimédia en temps réel de haute qualité.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-166">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="bb1e4-167">Réseau satisfaisant : Vérifiez que l'ensemble des adresses IP et des ports sont accessibles.</span><span class="sxs-lookup"><span data-stu-id="bb1e4-167">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

