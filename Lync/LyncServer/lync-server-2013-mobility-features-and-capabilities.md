---
title: 'Lync Server 2013 : Fonctionnalités de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="b11a3-102">Fonctionnalités de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b11a3-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b11a3-103">_**Dernière modification de la rubrique:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b11a3-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="b11a3-104">La fonctionnalité de mobilité introduite dans les mises à jour cumulatives de Lync Server 2013: février 2013 prend en charge les fonctionnalités des clients mobiles Lync 2010 et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b11a3-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="b11a3-105">Lorsque vous déployez le service de mobilité Lync Server 2013, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android et Windows Phone ou Nokia Symbian pour effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.</span><span class="sxs-lookup"><span data-stu-id="b11a3-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="b11a3-106">De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler par le biais d’un numéro de téléphone, de la messagerie vocale et d’appels manqués.</span><span class="sxs-lookup"><span data-stu-id="b11a3-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="b11a3-107">Les nouvelles fonctionnalités intégrées aux mises à jour cumulatives de Lync Server 2013: février 2013 incluent la fonctionnalité de voix sur IP (VoIP) et la vidéo (H. 264) pour les participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b11a3-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="b11a3-108">La fonctionnalité de mobilité introduite dans les mises à jour cumulatives de Lync Server 2013: février 2013 prend en charge les fonctionnalités de client mobile de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b11a3-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="b11a3-109">Les mises à jour cumulatives pour Lync Server 2013:2013 février installer l’API Web de communications unifiées ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="b11a3-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="b11a3-110">UCWA est le composant utilisé pour les clients mobiles Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b11a3-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="b11a3-111">Dans Lync Server 2013, MCX est utilisé pour les clients mobiles Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="b11a3-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="b11a3-112">Mises à jour cumulatives pour Lync Server 2013: février 2013 Introduisez UCWA comme nouveau point d’entrée pour les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="b11a3-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="b11a3-113">Lync Server 2013 implémente simultanément le service de mobilité (MCX), introduit dans les mises à jour cumulatives de Lync Server 2010:2011 novembre, et prend en charge Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="b11a3-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="b11a3-114">Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013: février 2013, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android et Windows Phone pris en charge pour effectuer des activités suivantes:</span><span class="sxs-lookup"><span data-stu-id="b11a3-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b11a3-115">Les fonctionnalités prises en charge par le service de mobilité par le biais des mises à jour cumulatives pour Lync Server 2010:2011 novembre sont indiquées (MCX).</span><span class="sxs-lookup"><span data-stu-id="b11a3-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="b11a3-116">Toutes les fonctionnalités répertoriées sont prises en charge par UCWA, introduites dans les mises à jour cumulatives de Lync Server 2013: février 2013.</span><span class="sxs-lookup"><span data-stu-id="b11a3-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="b11a3-117">Envoyer et recevoir des messages instantanés (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="b11a3-118">Afficher la présence (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="b11a3-119">Afficher les contacts (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="b11a3-120">Cliquez pour participer à une conférence (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="b11a3-121">Appel via le bureau (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="b11a3-122">Une seule valeur (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="b11a3-123">Messagerie vocale (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="b11a3-124">Notification d’appel manqué (MCX)</span><span class="sxs-lookup"><span data-stu-id="b11a3-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="b11a3-125">VoIP</span><span class="sxs-lookup"><span data-stu-id="b11a3-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="b11a3-126">Vidéo des participants (H.264)</span><span class="sxs-lookup"><span data-stu-id="b11a3-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b11a3-127">Lync 2010 mobile proposait un client pour les appareils Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="b11a3-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="b11a3-128">Lync 2013 mobile n’aura pas de client pour les appareils Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="b11a3-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="b11a3-129">Les utilisateurs d’Apple iPad pourront accéder aux fonctionnalités améliorées.</span><span class="sxs-lookup"><span data-stu-id="b11a3-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="b11a3-130">Lorsque vous participez à une réunion à l’aide de la fonction d’appel audio, un utilisateur d’iPad peut afficher les présentations Microsoft PowerPoint téléchargées au sein d’une réunion, partager des applications et des bureaux, afficher la liste des participants à la réunion et recevoir des notifications d’autres types de contenu qui sont partagés au sein de la réunion.</span><span class="sxs-lookup"><span data-stu-id="b11a3-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="b11a3-131">Lorsque vous avez atteint le numéro unique, un utilisateur reçoit les appels sur un numéro de téléphone mobile composé du numéro professionnel.</span><span class="sxs-lookup"><span data-stu-id="b11a3-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="b11a3-132">Avec la fonction d’appel via le bureau, l’utilisateur passe un appel sortant du client mobile Lync en utilisant un numéro de téléphone professionnel plutôt que le numéro de téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="b11a3-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="b11a3-133">Pour les appels sortants, le client envoie une demande à MCX ou UCWA (en fonction de la version mobile de Lync) pour l’appeler.</span><span class="sxs-lookup"><span data-stu-id="b11a3-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="b11a3-134">Le serveur Initialise l’appel, puis le rappelle sur le téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="b11a3-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="b11a3-135">Lorsque l’utilisateur répond, le serveur effectue l’appel en composant un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="b11a3-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="b11a3-136">En utilisant les appels via le bureau, les utilisateurs peuvent conserver leur identité professionnelle pendant un appel, ce qui signifie que le destinataire de l’appel n’a pas pu voir le numéro de téléphone mobile de l’appelant et l’appelant évite les frais d’appel sortants.</span><span class="sxs-lookup"><span data-stu-id="b11a3-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b11a3-137">Toutes les fonctionnalités ne fonctionnent pas exactement de la même manière sur tous les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="b11a3-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="b11a3-138">Pour plus d’informations sur les fonctionnalités prises en charge sur les appareils mobiles, voir <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>tableaux de comparaison des clients mobiles à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="b11a3-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="b11a3-139">Pour plus d’informations sur les appareils et systèmes d’exploitation pris en charge, voir les rubriques relatives à la configuration <A href="lync-server-2013-planning-for-mobile-clients.md">des clients mobiles dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b11a3-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b11a3-140">Lorsque vous utilisez la fonctionnalité de découverte automatique de Lync Server 2013, les applications mobiles peuvent automatiquement Rechercher les services Web de Lync Server 2013 sans nécessiter l’entrée manuelle des URL dans les paramètres de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b11a3-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="b11a3-141">La saisie manuelle d’URL dans les paramètres de l’appareil mobile est également prise en charge, principalement à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="b11a3-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b11a3-142">MCX et UCWA sont des services gratuits qui sont déployés pour prendre en charge les clients mobiles Lync 2010 et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b11a3-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="b11a3-143">Lync 2013 mobile ne sera pas en mesure de se connecter aux déploiements de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b11a3-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="b11a3-144">Lync 2010 mobile et Lync 2013 mobile pourront utiliser un déploiement Lync Server 2013 avec les mises à jour cumulatives de Lync Server 2013: le 2013 février est appliqué.</span><span class="sxs-lookup"><span data-stu-id="b11a3-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="b11a3-145">La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="b11a3-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="b11a3-146">Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.</span><span class="sxs-lookup"><span data-stu-id="b11a3-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="b11a3-147">Par exemple, une invitation à un message instantané manqué peut générer une notification de transmission.</span><span class="sxs-lookup"><span data-stu-id="b11a3-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="b11a3-148">MCX, UCWA, Autodiscover Service et la prise en charge des notifications de transmission sont fournies dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b11a3-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="b11a3-149">Les fonctionnalités de client mises à jour, les fonctionnalités et l’utilisation de UCWA comme point d’entrée de mobilité sont introduites dans les mises à jour cumulatives de Lync Server 2013: février 2013.</span><span class="sxs-lookup"><span data-stu-id="b11a3-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

