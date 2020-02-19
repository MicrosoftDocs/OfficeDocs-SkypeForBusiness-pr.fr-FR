---
title: Vue d’ensemble des conférences A/V de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d77d39cfa1483db9251d038f876f8e91428ae23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="c6800-102">Vue d’ensemble de la conférence A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6800-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6800-103">_**Dernière modification de la rubrique :** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="c6800-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="c6800-p101">La conférence A/V permet d’établir des communications audio et vidéo en temps réel entre vos utilisateurs. Lorsque vous déployez la conférence, vous pouvez choisir d’activer et d’utiliser la conférence web et la conférence A/V, ou uniquement la conférence web.</span><span class="sxs-lookup"><span data-stu-id="c6800-p101">A/V conferencing enables real-time audio and video communications between your users. When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="c6800-p102">Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de média de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique.</span><span class="sxs-lookup"><span data-stu-id="c6800-p102">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires. This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="c6800-108">Avant d’activer les utilisateurs pour la conférence A/V, assurez-vous que votre réseau est en mesure de gérer la charge qui en résulte.</span><span class="sxs-lookup"><span data-stu-id="c6800-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="c6800-109">Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6800-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="c6800-110">Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="c6800-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="c6800-111">Ceci est important pour les réseaux restreints, tels que les liaisons à bande passante limitée entre les sites centraux et les sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="c6800-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="c6800-112">Pour plus d’informations, reportez-vous à [vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="c6800-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="c6800-113">Pour plus d’informations sur les besoins en bande passante des médias, voir [Network Bandwidth Requirements for Media Traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="c6800-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="c6800-114">Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio tels que des casques pour y prendre part.</span><span class="sxs-lookup"><span data-stu-id="c6800-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="c6800-115">Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo tels que des webcams pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c6800-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="c6800-116">Nous vous recommandons d’utiliser des appareils de communications unifiées certifiés par Microsoft pour tous les types d’appareils, afin de garantir une expérience utilisateur optimale.</span><span class="sxs-lookup"><span data-stu-id="c6800-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="c6800-117">Pour plus d’informations sur les périphériques certifiés UC, voir « téléphones et appareils pour [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861)Lync » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c6800-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="c6800-118">Pour les périphériques audio ou vidéo, le déploiement des périphériques et la formation des utilisateurs sont des étapes importantes qu’il convient de planifier soigneusement.</span><span class="sxs-lookup"><span data-stu-id="c6800-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="c6800-119">Les sections suivantes décrivent les fonctionnalités de conférence audio et vidéo et fournissent des informations sur la gestion de la bande passante et la sélection de clients appropriés.</span><span class="sxs-lookup"><span data-stu-id="c6800-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="c6800-120">Fonctionnalités d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="c6800-120">Audio Conferencing Features</span></span>

<span data-ttu-id="c6800-121">Lync Server 2013 offre plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’expérience de conférence audio pour l’utilisateur, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6800-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="c6800-122">**Public muet**   le présentateur peut utiliser ce paramètre pour désactiver tous les participants audio de la Conférence et placer la Conférence dans un État où les non-présentateurs ne peuvent pas le désactiver.</span><span class="sxs-lookup"><span data-stu-id="c6800-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="c6800-123">**Annonces d’entrée/sortie de conférence**   si vous avez activé la Conférence rendez-vous, les présentateurs peuvent utiliser ce paramètre pour activer ou désactiver les annonces d’entrée et de sortie afin de minimiser les distractions lorsqu’une conférence est en cours.</span><span class="sxs-lookup"><span data-stu-id="c6800-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="c6800-124">**L’ajout d’un utilisateur en appelant**   des présentateurs et des participants disposant d’une autorisation, peut ajouter des numéros RTC aux conférences et faire en sorte que la Conférence rende les numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="c6800-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="c6800-125">Fonctionnalités de visioconférence</span><span class="sxs-lookup"><span data-stu-id="c6800-125">Video Conferencing Features</span></span>

<span data-ttu-id="c6800-126">Lync Server 2013 offre plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’expérience de conférence vidéo pour l’utilisateur, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6800-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="c6800-127">**Vue**   de la galerie dans les conférences vidéo qui contiennent plus de deux personnes, les utilisateurs voient automatiquement tous les utilisateurs de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="c6800-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="c6800-128">Si celle-ci comporte plus de cinq participants, la vidéo des participants les plus actifs apparaît sur la ligne supérieure et seule la photo apparaît pour les autres participants.</span><span class="sxs-lookup"><span data-stu-id="c6800-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="c6800-129">La vidéo à plusieurs est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6800-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="c6800-130">Pour plus d’informations sur la configuration ou la désactivation de la vidéo à plusieurs, voir [configuration de la bande passante vidéo dans Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="c6800-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="c6800-131">**Vidéo panoramique si**   un périphérique de conférence vidéo Roundtable est installé dans la salle de conférence, cette fonctionnalité fournit une vue complète de 360 degrés de la salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="c6800-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="c6800-132">Le clip vidéo panoramique est disponible uniquement avec les périphériques RoundTable.</span><span class="sxs-lookup"><span data-stu-id="c6800-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="c6800-133">**Présentateur uniquement**   les présentateurs de mode vidéo peuvent configurer la réunion de sorte que seule la vidéo du présentateur soit affichée.</span><span class="sxs-lookup"><span data-stu-id="c6800-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="c6800-134">Ceci empêche toute distraction lors des réunions à grande échelle, lorsque plusieurs flux vidéo sont disponibles et verrouillés à différentes sources.</span><span class="sxs-lookup"><span data-stu-id="c6800-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="c6800-135">Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable.</span><span class="sxs-lookup"><span data-stu-id="c6800-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="c6800-136">\*\*\*\*   Les utilisateurs de la vidéo HD peuvent bénéficier de résolutions jusqu’à la haute définition (HD) dans les appels à deux et les conférences à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="c6800-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="c6800-137">\*\*\*\*   Les présentateurs vidéo Spotlight peuvent configurer la réunion de sorte que seule la vidéo d’un participant sélectionné qui est une source vidéo soit visible par les autres participants à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="c6800-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="c6800-138">Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable pour la vidéo panoramique.</span><span class="sxs-lookup"><span data-stu-id="c6800-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

