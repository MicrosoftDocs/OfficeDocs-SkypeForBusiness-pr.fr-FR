---
title: 'Lync Server 2013 : fonctionnalités et fonctionnalités de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac62cb2fe222a2a36c0fc0aeb79a4aaa37e9964
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="a37ef-102">Fonctionnalités et fonctionnalités de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a37ef-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37ef-103">_**Dernière modification de la rubrique :** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="a37ef-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="a37ef-104">La fonctionnalité de mobilité introduite dans les mises à jour cumulatives pour Lync Server 2013 : février 2013 prend en charge les fonctionnalités des clients mobiles Lync 2010 mobile et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ef-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="a37ef-105">Lorsque vous déployez le service de mobilité Lync Server 2013, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android et Windows Phone, ou Nokia Symbian, pour effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.</span><span class="sxs-lookup"><span data-stu-id="a37ef-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="a37ef-106">En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués.</span><span class="sxs-lookup"><span data-stu-id="a37ef-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="a37ef-107">Les nouvelles fonctionnalités introduites dans les mises à jour cumulatives pour Lync Server 2013 : février 2013 incluent la fonctionnalité voix sur IP (VoIP) et la vidéo (H. 264) pour le participant à la réunion.</span><span class="sxs-lookup"><span data-stu-id="a37ef-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="a37ef-108">La fonctionnalité de mobilité introduite dans les mises à jour cumulatives pour Lync Server 2013 : février 2013 prend en charge la fonctionnalité de client mobile Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ef-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="a37ef-109">Les mises à jour cumulatives pour Lync Server 2013 : février 2013 installer l’API Web de communications unifiées ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="a37ef-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="a37ef-110">UCWA est le composant utilisé pour les clients mobiles Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ef-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="a37ef-111">Dans Lync Server 2013, MCX est utilisé pour les clients mobiles Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="a37ef-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="a37ef-112">Mises à jour cumulatives pour Lync Server 2013 : février 2013 introduire UCWA comme nouveau point d’entrée pour les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="a37ef-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="a37ef-113">Lync Server 2013 implémente simultanément le service de mobilité (MCX), introduit dans les mises à jour cumulatives pour Lync Server 2010 : novembre 2011, et prend en charge Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="a37ef-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="a37ef-114">Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013 : février 2013, les utilisateurs peuvent utiliser des périphériques mobiles Apple iOS, Android et Windows Phone pris en charge pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a37ef-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a37ef-115">Les fonctionnalités prises en charge par le service de mobilité à partir des mises à jour cumulatives pour Lync Server 2010 : novembre 2011 sont indiquées par (MCX).</span><span class="sxs-lookup"><span data-stu-id="a37ef-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="a37ef-116">Toutes les fonctionnalités répertoriées sont prises en charge par le UCWA, introduites dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ef-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="a37ef-117">Envoyer et recevoir des messages instantanés (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="a37ef-118">Afficher la présence (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="a37ef-119">Afficher les contacts (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="a37ef-120">Cliquez pour participer à une conférence (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="a37ef-121">Appel via le bureau (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="a37ef-122">Un seul numéro atteint (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="a37ef-123">Messagerie vocale (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="a37ef-124">Notification d’appel manqué (MCX)</span><span class="sxs-lookup"><span data-stu-id="a37ef-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="a37ef-125">Voix sur IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="a37ef-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="a37ef-126">Vidéo des participants (H. 264)</span><span class="sxs-lookup"><span data-stu-id="a37ef-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a37ef-127">Lync 2010 mobile a fourni un client pour les appareils Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="a37ef-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="a37ef-128">Lync 2013 mobile ne disposera pas d’un client pour les appareils basés sur Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="a37ef-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="a37ef-129">Les utilisateurs d’appareils Apple iPad auront accès aux fonctionnalités améliorées.</span><span class="sxs-lookup"><span data-stu-id="a37ef-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="a37ef-130">Après avoir rejoint une réunion à l’aide de l’audio de rappel, un utilisateur de iPad pourra visualiser les présentations Microsoft PowerPoint téléchargées au sein d’une réunion, partager des applications et des bureaux, afficher la liste des participants à la réunion et recevoir des notifications d’autres types de contenu. qui sont partagés au sein de la réunion.</span><span class="sxs-lookup"><span data-stu-id="a37ef-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="a37ef-131">Grâce au numéro unique, un utilisateur reçoit les appels qui ont été passés en composant son numéro professionnel sur son téléphone portable.</span><span class="sxs-lookup"><span data-stu-id="a37ef-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="a37ef-132">Avec l’appel via le bureau, l’utilisateur passe un appel sortant depuis le client Lync mobile en utilisant un numéro de téléphone professionnel au lieu du numéro de téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="a37ef-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="a37ef-133">Avec les appels sortants, le client envoie une demande à MCX ou UCWA (en fonction de la version de Lync mobile) pour effectuer les appels.</span><span class="sxs-lookup"><span data-stu-id="a37ef-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="a37ef-134">Le serveur lance l’appel, puis rappelle l’utilisateur sur son téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="a37ef-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="a37ef-135">Lorsque ce dernier répond, le serveur termine l’appel en composant le numéro de l’interlocuteur.</span><span class="sxs-lookup"><span data-stu-id="a37ef-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="a37ef-136">L’utilisation de l’appel via le bureau permet aux utilisateurs de conserver leur identité professionnelle pendant un appel, ce qui signifie que le destinataire de l’appel ne voit pas le numéro de portable de l’appelant, et ce dernier évite ainsi les frais d’appel sortant encourus.</span><span class="sxs-lookup"><span data-stu-id="a37ef-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a37ef-137">Les fonctionnalités ne fonctionnent pas toutes de la même manière sur tous les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="a37ef-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="a37ef-138">Pour plus d’informations sur les fonctionnalités prises en charge sur les appareils mobiles, consultez <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>les tableaux de comparaison des clients mobiles à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="a37ef-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="a37ef-139">Pour plus d’informations sur les appareils pris en charge et les systèmes d’exploitation, voir les rubriques relatives aux conditions requises sous <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a37ef-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a37ef-140">Lorsque vous utilisez la fonctionnalité de découverte automatique Lync Server 2013, les applications mobiles peuvent localiser automatiquement les services Web Lync Server 2013 sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres de leurs appareils.</span><span class="sxs-lookup"><span data-stu-id="a37ef-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="a37ef-141">La saisie manuelle des URL dans les paramètres d’un appareil mobile est également prise en charge, principalement à des fins de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="a37ef-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a37ef-142">MCX et UCWA sont des services gratuits et sont déployés pour prendre en charge les clients mobiles Lync 2010 mobile et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ef-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="a37ef-143">Lync 2013 mobile ne pourra pas se connecter aux déploiements Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a37ef-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="a37ef-144">Lync 2010 mobile et Lync 2013 mobile seront en mesure d’utiliser un déploiement Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 : février 2013 appliquée.</span><span class="sxs-lookup"><span data-stu-id="a37ef-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="a37ef-145">La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="a37ef-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="a37ef-146">Une notification push est une notification qui est envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.</span><span class="sxs-lookup"><span data-stu-id="a37ef-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="a37ef-147">Par exemple, une invitation de messagerie instantanée manquée peut entraîner une notification de transmission.</span><span class="sxs-lookup"><span data-stu-id="a37ef-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="a37ef-148">MCX, UCWA, le service de découverte automatique et la prise en charge des notifications de type transmission sont fournis dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ef-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="a37ef-149">Les fonctionnalités client mises à jour, les fonctionnalités et l’utilisation de UCWA comme point d’entrée de mobilité sont présentées dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ef-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

