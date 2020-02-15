---
title: 'Lync Server 2013 : planification du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0d3173b3316d4e4dff704402da94c20aa2c9f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="48b1a-102">Planification du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b1a-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48b1a-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="48b1a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="48b1a-p101">Pour les applications de communications unifiées basées sur IP, comme la téléphonie, la vidéo et le partage d’application, la bande passante disponible des réseaux d’entreprise n’est généralement pas perçue comme un facteur limitatif dans les environnements de réseau local. En revanche, la bande passante réseau peut être limitée sur des liaisons de réseau étendu qui assurent l’interconnexion des sites. Lorsque le trafic réseau afflue et sature une liaison de réseau étendu, les mécanismes courants, comme la mise en attente, la mise en mémoire tampon et l’abandon de paquets, sont utilisés pour résoudre le problème de congestion. Le trafic supplémentaire est généralement retardé jusqu’à ce que le réseau ne soit plus saturé. Si nécessaire, le trafic peut également être interrompu. Avec un trafic de données conventionnel, le client qui reçoit les données peut facilement surmonter ce type de problème. Avec un trafic en temps réel, la saturation du réseau ne peut pas être résolue de cette manière, car les communications unifiées sont sensibles à la latence et à la perte de paquets. Si le réseau étendu est saturé, la qualité de l’expérience (QoE) des utilisateurs peut s’en ressentir. Lorsque le trafic en temps réel est saturé, il vaut mieux refuser des appels plutôt que de fournir des connexions de mauvaise qualité.</span><span class="sxs-lookup"><span data-stu-id="48b1a-p101">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments. However, on WAN links that interconnect sites, network bandwidth can be limited. When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion. The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped. For conventional data traffic in such situations, the receiving client can recover. For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss. Congestion on the WAN can result in a poor Quality of Experience (QoE) for users. For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="48b1a-112">Le contrôle d’admission des appels (CAC) détermine si la bande passante réseau est suffisante pour établir une session en temps réel de qualité acceptable.</span><span class="sxs-lookup"><span data-stu-id="48b1a-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="48b1a-113">Dans Lync Server 2013, le contrôle d’admission des appels contrôle le trafic en temps réel uniquement pour l’audio et la vidéo, mais il n’affecte pas le trafic de données.</span><span class="sxs-lookup"><span data-stu-id="48b1a-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="48b1a-114">Si la bande passante n’est pas suffisante sur le chemin du réseau étendu par défaut, le contrôle d’admission des appels peut essayer d’acheminer l’appel via un chemin Internet ou sur le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="48b1a-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="48b1a-115">Le contrôle d’admission des accès est disponible uniquement dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48b1a-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="48b1a-116">Cette section décrit le contrôle d’admission des appels et explique comment le planifier.</span><span class="sxs-lookup"><span data-stu-id="48b1a-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48b1a-117">Lync Server dispose de trois fonctionnalités voix entreprise avancées : le contrôle d’admission des appels (CAC), les services d’urgence (E9-1-1) et la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="48b1a-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="48b1a-118">Pour une vue d’ensemble des informations de planification communes à ces trois fonctionnalités, reportez-vous à <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network Settings for the Advanced Enterprise Voice Features in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48b1a-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="48b1a-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="48b1a-119">In This Section</span></span>

  - [<span data-ttu-id="48b1a-120">Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b1a-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="48b1a-121">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b1a-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="48b1a-122">Exemple : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b1a-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="48b1a-123">Composants et topologies pour CAC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b1a-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="48b1a-124">Meilleures pratiques pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b1a-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="48b1a-125">Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b1a-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

