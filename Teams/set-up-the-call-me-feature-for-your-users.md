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
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623130"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="48c5b-103">Configurer la fonctionnalité M’appeler pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="48c5b-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="48c5b-104">Dans Microsoft Teams, la fonctionnalité **M’appeler** permet aux utilisateurs de rejoindre la partie audio d’une réunion par téléphone.</span><span class="sxs-lookup"><span data-stu-id="48c5b-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="48c5b-105">Cela est utile dans les cas où l’utilisation d’un ordinateur pour l’audio n’est peut-être pas possible.</span><span class="sxs-lookup"><span data-stu-id="48c5b-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="48c5b-106">Les utilisateurs peuvent obtenir la partie audio de la réunion via leur téléphone portable ou leur ligne téléphonique ainsi que la partie contenu de la réunion, par exemple lorsqu’un autre participant partage son écran ou lit une vidéo sur leur &mdash; &mdash; ordinateur.</span><span class="sxs-lookup"><span data-stu-id="48c5b-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="48c5b-107">Pendant les périodes de forte affluence de réunions (que nous avons connues en liaison avec l'épidémie COVID-19), il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton <strong>Rejoindre une réunion Teams</strong> plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option <strong>M’appeler au</strong>.</span><span class="sxs-lookup"><span data-stu-id="48c5b-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="48c5b-108">Cela contribuera à garantir la qualité audio pendant les heures au cours desquelles le grand nombre de réunions entraîne une congestion du réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="48c5b-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="48c5b-109">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="48c5b-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="48c5b-110">Participer à une réunion en utilisant un téléphone pour le son</span><span class="sxs-lookup"><span data-stu-id="48c5b-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="48c5b-111">Cliquez **sur Rejoindre** pour participer à une réunion, puis sur Téléphone **dans** l’écran Choisir vos options audio et **vidéo,** puis cliquez **sur Rejoindre maintenant.**</span><span class="sxs-lookup"><span data-stu-id="48c5b-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="48c5b-112">À partir de là, les utilisateurs peuvent avoir l’appel de réunion et les rejoindre, ou se joindre manuellement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="48c5b-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Capture d’écran de l’option Audio du téléphone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="48c5b-114">**Laisser la réunion Teams appeler**</span><span class="sxs-lookup"><span data-stu-id="48c5b-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="48c5b-115">Sur **l’écran Utiliser le téléphone pour l’audio,** l’utilisateur entre son numéro de téléphone, puis clique sur **M’appeler.**</span><span class="sxs-lookup"><span data-stu-id="48c5b-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="48c5b-116">La réunion appelle l’utilisateur et l’intègre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="48c5b-116">The meeting calls the user and joins them to the meeting.</span></span>

![Capture d’écran de l’option M’appeler sur l’écran Utiliser le téléphone pour l’audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="48c5b-118">**Se composer manuellement**</span><span class="sxs-lookup"><span data-stu-id="48c5b-118">**Dial in manually**</span></span>

<span data-ttu-id="48c5b-119">Vous pouvez également rejoindre la réunion par numérotation directe.</span><span class="sxs-lookup"><span data-stu-id="48c5b-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="48c5b-120">Dans **l’écran Utiliser le téléphone pour la partie audio,** cliquez sur Composer manuellement pour obtenir la liste des numéros de téléphone à utiliser pour se rendre à la réunion. </span><span class="sxs-lookup"><span data-stu-id="48c5b-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Capture d’écran de l’option Composer manuellement](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="48c5b-122">Recevez un appel en cas de problème audio pendant une réunion</span><span class="sxs-lookup"><span data-stu-id="48c5b-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="48c5b-123">Si un utilisateur rencontre des problèmes audio lors de l’utilisation de son ordinateur au cours d’une réunion, il peut facilement passer à son téléphone pour l’audio.</span><span class="sxs-lookup"><span data-stu-id="48c5b-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="48c5b-124">Teams détecte un problème audio ou d’appareil et redirige l’utilisateur vers son téléphone en affichant une option **Me** rappeler.</span><span class="sxs-lookup"><span data-stu-id="48c5b-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="48c5b-125">Voici un exemple du message  et de l’option Me rappeler qui s’affiche lorsque Teams ne détecte pas de microphone.</span><span class="sxs-lookup"><span data-stu-id="48c5b-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Capture d’écran de l’option Me rappeler](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="48c5b-127">L’utilisateur clique **sur Me rappeler,** ce qui affiche l’écran **Utiliser le téléphone pour l’audio.**</span><span class="sxs-lookup"><span data-stu-id="48c5b-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="48c5b-128">À partir de là, il peut entrer son numéro de téléphone, lancer l’appel de la réunion Teams et le joindre à la réunion ou se joindre manuellement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="48c5b-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="48c5b-129">Configurer la fonctionnalité M’appeler</span><span class="sxs-lookup"><span data-stu-id="48c5b-129">Set up the Call me feature</span></span>

<span data-ttu-id="48c5b-130">Pour activer la fonctionnalité M’appeler pour les utilisateurs de votre organisation, les configurations suivantes doivent être configurées :</span><span class="sxs-lookup"><span data-stu-id="48c5b-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="48c5b-131">L’audioconférence est activé pour les utilisateurs dans votre organisation qui planifier des réunions (organisateurs de réunions).</span><span class="sxs-lookup"><span data-stu-id="48c5b-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="48c5b-132">Pour en savoir plus, consultez Configurer l’audioconférence pour [Teams](set-up-audio-conferencing-in-teams.md) et gérer les paramètres d’audioconférence pour [un utilisateur dans Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="48c5b-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="48c5b-133">L’organisateur de la réunion peut appeler à partir de réunions.</span><span class="sxs-lookup"><span data-stu-id="48c5b-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="48c5b-134">Pour en savoir plus, [consultez Gérer les paramètres d’audioconférence d’un utilisateur dans Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="48c5b-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="48c5b-135">Si les appels sortants des réunions ne sont pas activés pour l’organisateur de la réunion, l’option audio du téléphone dans l’écran Choisir vos **options** **audio** et vidéo n’est disponible pour personne et les autres utilisateurs ne peuvent pas recevoir d’appel pour participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="48c5b-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="48c5b-136">Pour les utilisateurs dont l’appel sortant est activé, une fois qu’ils ont rejoint la réunion, ils peuvent rejoindre d’autres personnes composant leur numéro à partir de l’icône Afficher **les participants.**</span><span class="sxs-lookup"><span data-stu-id="48c5b-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
