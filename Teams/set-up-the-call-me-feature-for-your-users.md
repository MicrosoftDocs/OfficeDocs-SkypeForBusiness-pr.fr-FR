---
title: Configurer la fonctionnalité M’appeler pour vos utilisateurs
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer la fonctionnalité m’appeler dans teams pour permettre aux utilisateurs d’accéder à la partie audio par téléphone lors de l’utilisation de leur ordinateur pour le son.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138014"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="07888-103">Configurer la fonctionnalité M’appeler pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="07888-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="07888-104">Dans Microsoft Teams, la fonctionnalité **m’appeler** permet aux utilisateurs d’accéder à la partie audio d’une réunion par téléphone.</span><span class="sxs-lookup"><span data-stu-id="07888-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="07888-105">C’est pratique dans les situations où l’utilisation d’un ordinateur pour l’audio peut ne pas être possible.</span><span class="sxs-lookup"><span data-stu-id="07888-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="07888-106">Les utilisateurs peuvent accéder à la partie audio de la réunion par le biais du téléphone portable ou de la ligne fixe et de la partie du contenu de la réunion &mdash; , par exemple lorsqu’un autre participant à une réunion partage son écran ou lit une vidéo &mdash; par le biais de leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="07888-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="07888-107">Pendant les périodes de forte réunion (que nous avons rencontrées en conjonction avec l’COVID-19), nous recommandons aux utilisateurs de participer à des réunions en cliquant sur le bouton participer à la <strong>réunion</strong> et en utilisant <strong>appeler à</strong>.</span><span class="sxs-lookup"><span data-stu-id="07888-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="07888-108">Cela permet de garantir une qualité audio optimale lorsque le volume de la réunion est à l’origine du congestion du réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="07888-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="07888-109">Pendant la durée de l’épidémie COVID-19, il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton **Rejoindre une réunion Teams** plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option **M’appeler au**</strong>.</span><span class="sxs-lookup"><span data-stu-id="07888-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="07888-110">Cela est principalement dû à l’encombrement des infrastructures téléphonique des pays touchés par le COVID-19.</span><span class="sxs-lookup"><span data-stu-id="07888-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="07888-111">En évitant les appels RTC, vous bénéficierez probablement d’une meilleure qualité audio.</span><span class="sxs-lookup"><span data-stu-id="07888-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="07888-112">L’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="07888-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="07888-113">Participer à une réunion à l’aide du téléphone pour le son</span><span class="sxs-lookup"><span data-stu-id="07888-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="07888-114">Cliquez sur **rejoindre** pour participer à une réunion, puis cliquez sur **audio du téléphone** dans l’écran **choisir vos paramètres audio et vidéo** .</span><span class="sxs-lookup"><span data-stu-id="07888-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="07888-115">À partir de là, les utilisateurs peuvent participer à la réunion et les rejoindre manuellement.</span><span class="sxs-lookup"><span data-stu-id="07888-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Capture d’écran de l’option audio du téléphone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="07888-117">**Permettre à la réunion teams d’appeler**</span><span class="sxs-lookup"><span data-stu-id="07888-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="07888-118">Sur l’écran **utiliser le téléphone pour l’audio** , l’utilisateur entre son numéro de téléphone, puis clique sur **m’appeler**.</span><span class="sxs-lookup"><span data-stu-id="07888-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="07888-119">La réunion appelle l’utilisateur et l’associe à la réunion.</span><span class="sxs-lookup"><span data-stu-id="07888-119">The meeting calls the user and joins them to the meeting.</span></span>

![Capture d’écran de l’option m’appeler sur l’écran utiliser le téléphone pour l’audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="07888-121">**Composer manuellement**</span><span class="sxs-lookup"><span data-stu-id="07888-121">**Dial in manually**</span></span>

<span data-ttu-id="07888-122">Une autre méthode consiste à se connecter directement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="07888-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="07888-123">Sur l’écran **utiliser le téléphone pour l’audio** , cliquez sur **composer manuellement** pour obtenir la liste des numéros de téléphone à utiliser pour vous connecter à la réunion.</span><span class="sxs-lookup"><span data-stu-id="07888-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Capture d’écran de l’option composer en manuel](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="07888-125">Recevez un appel en cas de problème de l’audio pendant une réunion</span><span class="sxs-lookup"><span data-stu-id="07888-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="07888-126">Si un utilisateur rencontre des problèmes audio lors de l’utilisation de son ordinateur au cours d’une réunion, l’utilisateur peut facilement basculer vers son téléphone pour l’audio.</span><span class="sxs-lookup"><span data-stu-id="07888-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="07888-127">Teams détecte l’affichage d’un problème audio ou de périphérique, et redirige l’utilisateur pour qu’il utilise son téléphone en affichant une option **me rappeler** .</span><span class="sxs-lookup"><span data-stu-id="07888-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="07888-128">Voici un exemple de message et l’option **retour m’appeler** qui s’affiche lorsque Microsoft Teams ne détecte pas de micro.</span><span class="sxs-lookup"><span data-stu-id="07888-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Capture d’écran de l’option me rappeler](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="07888-130">L’utilisateur clique sur **me**rappeler, ce qui fait apparaître l’écran **utiliser le téléphone pour l’audio** .</span><span class="sxs-lookup"><span data-stu-id="07888-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="07888-131">À partir de cet emplacement, ils peuvent entrer leur numéro de téléphone et participer à la réunion teams et les rejoindre manuellement.</span><span class="sxs-lookup"><span data-stu-id="07888-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="07888-132">Configurer la fonctionnalité m’appeler</span><span class="sxs-lookup"><span data-stu-id="07888-132">Set up the Call me feature</span></span>

<span data-ttu-id="07888-133">Pour activer la fonctionnalité appeler pour les utilisateurs de votre organisation, les informations suivantes doivent être configurées :</span><span class="sxs-lookup"><span data-stu-id="07888-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="07888-134">L’option audioconférence est activée pour les utilisateurs de votre organisation qui planifient des réunions (organisateurs de la réunion).</span><span class="sxs-lookup"><span data-stu-id="07888-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="07888-135">Pour en savoir plus, consultez la rubrique [configurer l’audioconférence pour les équipes](set-up-audio-conferencing-in-teams.md) et [gérer les paramètres de l’audioconférence pour un utilisateur dans teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="07888-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="07888-136">Les utilisateurs peuvent se connecter aux réunions.</span><span class="sxs-lookup"><span data-stu-id="07888-136">Users can dial out from meetings.</span></span> <span data-ttu-id="07888-137">Pour en savoir plus, voir [gérer les paramètres d’audioconférence pour un utilisateur dans teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="07888-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="07888-138">Si un utilisateur n’a pas accès à la Conférence rendez-vous pour les réunions activées, l’option **m’appeler** n’est pas disponible et l’utilisateur ne reçoit pas d’appel pour le joindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="07888-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="07888-139">Au lieu de cela, l’utilisateur voit la liste des numéros de téléphone de l’écran **utiliser le téléphone pour l’audio** qu’il peut utiliser pour se connecter manuellement à la réunion sur son téléphone.</span><span class="sxs-lookup"><span data-stu-id="07888-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
