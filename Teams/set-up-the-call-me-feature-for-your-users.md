---
title: Configurer la fonctionnalité M’appeler pour vos utilisateurs
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer la fonctionnalité M’appeler dans Teams afin que les utilisateurs ne peuvent pas rejoindre la partie audio par téléphone lorsqu’ils utilisent leur ordinateur pour l’audio.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821094"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="69cd7-103">Configurer la fonctionnalité M’appeler pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="69cd7-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="69cd7-104">Dans Microsoft Teams, la fonctionnalité **M’appeler** permet aux utilisateurs de rejoindre la partie audio d’une réunion par téléphone.</span><span class="sxs-lookup"><span data-stu-id="69cd7-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="69cd7-105">Cela est utile dans les cas où l’utilisation d’un ordinateur pour l’audio n’est peut-être pas possible.</span><span class="sxs-lookup"><span data-stu-id="69cd7-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="69cd7-106">Les utilisateurs peuvent obtenir la partie audio de la réunion via leur téléphone portable ou leur ligne téléphonique ainsi que la partie contenu de la réunion, par exemple lorsqu’un autre participant partage son écran ou lit une vidéo sur leur &mdash; &mdash; ordinateur.</span><span class="sxs-lookup"><span data-stu-id="69cd7-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="69cd7-107">Pendant les périodes de forte affluence de réunions (que nous avons connues en liaison avec l'épidémie COVID-19), il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton <strong>Rejoindre une réunion Teams</strong> plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option <strong>M’appeler au</strong>.</span><span class="sxs-lookup"><span data-stu-id="69cd7-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="69cd7-108">Cela contribuera à garantir la qualité audio pendant les heures au cours desquelles le grand nombre de réunions entraîne une congestion du réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="69cd7-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="69cd7-109">Pendant la durée de l’épidémie COVID-19, il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton **Rejoindre une réunion Teams** plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option **M’appeler au**</strong>.</span><span class="sxs-lookup"><span data-stu-id="69cd7-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="69cd7-110">Cela est principalement dû à l’encombrement des infrastructures téléphonique des pays touchés par le COVID-19.</span><span class="sxs-lookup"><span data-stu-id="69cd7-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="69cd7-111">En évitant les appels RTC, vous bénéficierez probablement d’une meilleure qualité audio.</span><span class="sxs-lookup"><span data-stu-id="69cd7-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="69cd7-112">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="69cd7-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="69cd7-113">Participer à une réunion en utilisant un téléphone pour le son</span><span class="sxs-lookup"><span data-stu-id="69cd7-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="69cd7-114">Cliquez **sur** Rejoindre pour participer à une réunion, puis sur **Audio** sur l’écran Choisir vos  **paramètres audio et** vidéo.</span><span class="sxs-lookup"><span data-stu-id="69cd7-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="69cd7-115">À partir de là, les utilisateurs peuvent avoir l’appel de réunion et les rejoindre, ou se joindre manuellement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="69cd7-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Capture d’écran de l’option Audio du téléphone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="69cd7-117">**Laisser la réunion Teams appeler**</span><span class="sxs-lookup"><span data-stu-id="69cd7-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="69cd7-118">Sur **l’écran Utiliser le téléphone pour l’audio,** l’utilisateur entre son numéro de téléphone, puis clique sur **M’appeler.**</span><span class="sxs-lookup"><span data-stu-id="69cd7-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="69cd7-119">La réunion appelle l’utilisateur et l’intègre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="69cd7-119">The meeting calls the user and joins them to the meeting.</span></span>

![Capture d’écran de l’option M’appeler sur l’écran Utiliser le téléphone pour l’audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="69cd7-121">**Se composer manuellement**</span><span class="sxs-lookup"><span data-stu-id="69cd7-121">**Dial in manually**</span></span>

<span data-ttu-id="69cd7-122">Vous pouvez également rejoindre la réunion par numérotation directe.</span><span class="sxs-lookup"><span data-stu-id="69cd7-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="69cd7-123">Dans **l’écran Utiliser le téléphone pour la partie audio,** cliquez sur Composer manuellement pour obtenir la liste des numéros de téléphone à utiliser pour se rendre à la réunion. </span><span class="sxs-lookup"><span data-stu-id="69cd7-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Capture d’écran de l’option Composer manuellement](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="69cd7-125">Recevez un appel en cas de problème audio pendant une réunion</span><span class="sxs-lookup"><span data-stu-id="69cd7-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="69cd7-126">Si un utilisateur rencontre des problèmes audio lors de l’utilisation de son ordinateur au cours d’une réunion, il peut facilement passer à son téléphone pour l’audio.</span><span class="sxs-lookup"><span data-stu-id="69cd7-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="69cd7-127">Teams détecte un problème audio ou d’appareil et redirige l’utilisateur vers son téléphone en affichant une option **Me** rappeler.</span><span class="sxs-lookup"><span data-stu-id="69cd7-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="69cd7-128">Voici un exemple du message  et de l’option Me rappeler qui s’affiche lorsque Teams ne détecte pas de microphone.</span><span class="sxs-lookup"><span data-stu-id="69cd7-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Capture d’écran de l’option Me rappeler](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="69cd7-130">L’utilisateur clique **sur Me rappeler,** ce qui affiche l’écran Utiliser **le téléphone pour l’audio.**</span><span class="sxs-lookup"><span data-stu-id="69cd7-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="69cd7-131">À partir de là, il peut entrer son numéro de téléphone, lancer l’appel de la réunion Teams et le joindre à la réunion ou se joindre manuellement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="69cd7-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="69cd7-132">Configurer la fonctionnalité M’appeler</span><span class="sxs-lookup"><span data-stu-id="69cd7-132">Set up the Call me feature</span></span>

<span data-ttu-id="69cd7-133">Pour activer la fonctionnalité M’appeler pour les utilisateurs de votre organisation, les configurations suivantes doivent être configurées :</span><span class="sxs-lookup"><span data-stu-id="69cd7-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="69cd7-134">L’audioconférence est activé pour les utilisateurs dans votre organisation qui planifier des réunions (organisateurs de réunions).</span><span class="sxs-lookup"><span data-stu-id="69cd7-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="69cd7-135">Pour en savoir plus, consultez Configurer l’audioconférence pour [Teams](set-up-audio-conferencing-in-teams.md) et gérer les paramètres d’audioconférence pour [un utilisateur dans Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="69cd7-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="69cd7-136">Les utilisateurs peuvent appeler à partir des réunions.</span><span class="sxs-lookup"><span data-stu-id="69cd7-136">Users can dial out from meetings.</span></span> <span data-ttu-id="69cd7-137">Pour en savoir plus, [consultez Gérer les paramètres d’audioconférence d’un utilisateur dans Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="69cd7-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="69cd7-138">Si un utilisateur n’a pas activé les  appels sortants des réunions, l’option M’appeler n’est pas disponible et l’utilisateur ne recevra pas d’appel pour participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="69cd7-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="69cd7-139">À la place, l’utilisateur voit sur l’écran Utiliser le téléphone pour **l’audio** une liste qui lui permet de se composer manuellement de la réunion sur son téléphone.</span><span class="sxs-lookup"><span data-stu-id="69cd7-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
