---
title: 'Lync Server 2013 : Planification du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af07a3f0b067f4dae3835c682cb51e6fefdcf21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="8f0b2-102">Planification du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0b2-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f0b2-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8f0b2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8f0b2-104">Pour les applications de communications unifiées (UC) qui sont basées sur le protocole IP, comme la téléphonie, la vidéo et le partage d’application, la bande passante disponible des réseaux d’entreprise n’est généralement pas considérée comme un facteur limitatif dans les environnements LAN.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="8f0b2-105">En revanche, la bande passante réseau peut être limitée sur des liaisons de réseau étendu qui assurent l’interconnexion des sites.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="8f0b2-106">Quand un flux réseau surabonne une liaison WAN, des mécanismes actuels comme la mise en file d’attente, la mise en mémoire tampon et la suppression de paquets sont utilisés pour résoudre le congestion.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="8f0b2-107">Le trafic supplémentaire est généralement retardé jusqu’à ce que la congestion du réseau soit régressif ou, si nécessaire, le trafic est rejeté.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="8f0b2-108">Pour le trafic de données conventionnel dans ces situations, le client de réception peut récupérer.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="8f0b2-109">Pour le trafic en temps réel, comme les communications unifiées, la congestion du réseau ne peut pas être résolue de cette manière, car le trafic de communications unifiées est sensible à la latence et à la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="8f0b2-110">La congestion sur le WAN peut entraîner une médiocre qualité de l’apprentissage (QoE) pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="8f0b2-111">Pour le trafic en temps réel dans des conditions congestionnées, il est préférable de rejeter les appels plutôt que d’offrir des connexions de mauvaise qualité.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="8f0b2-112">Le contrôle d’admission des appels (CAC) détermine si la bande passante réseau est suffisante pour établir une session en temps réel de qualité acceptable.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="8f0b2-113">Dans Lync Server 2013, CAC contrôle le trafic en temps réel uniquement pour les appels audio et vidéo, mais n’affecte pas le trafic de données.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="8f0b2-114">Si la bande passante n’est pas suffisante sur le chemin du réseau étendu par défaut, le contrôle d’admission des appels peut essayer d’acheminer l’appel via un chemin Internet ou sur le réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="8f0b2-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="8f0b2-115">Le CAC est disponible uniquement sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="8f0b2-116">Cette section décrit le contrôle d’admission des appels et explique comment le planifier.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f0b2-117">Lync Server comporte trois fonctionnalités avancées de voix entreprise: contrôle d’admission des appels (CAC), services d’urgence (E9-1-1) et contournement de média.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="8f0b2-118">Pour obtenir une vue d’ensemble des informations de planification communes à ces trois fonctionnalités, consultez <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">la rubrique paramètres réseau pour les fonctionnalités avancées de voix entreprise de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8f0b2-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f0b2-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8f0b2-119">In This Section</span></span>

  - [<span data-ttu-id="8f0b2-120">Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0b2-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="8f0b2-121">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0b2-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="8f0b2-122">Exemple: rassemblement de vos exigences de contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0b2-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="8f0b2-123">Composants et topologies pour CAC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0b2-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="8f0b2-124">Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0b2-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="8f0b2-125">Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0b2-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

