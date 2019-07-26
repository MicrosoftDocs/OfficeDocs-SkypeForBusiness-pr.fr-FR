---
title: Configurer la fonctionnalité m’appeler pour vos utilisateurs
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer la fonctionnalité m’appeler dans teams pour permettre aux utilisateurs d’accéder à la partie audio par téléphone dans les cas où l’utilisation de leur ordinateur pour l’audio peut ne pas être possible.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae36ddf9c7fd16ad21217d0c68d48d28a0b7463c
ms.sourcegitcommit: 40328f5e80ee992cd0e63655ede9698a35069f15
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2019
ms.locfileid: "35908237"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="b0247-103">Configurer la fonctionnalité m’appeler pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b0247-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="b0247-104">Dans Microsoft Teams, la fonctionnalité **m’appeler** permet aux utilisateurs d’accéder à la partie audio d’une réunion par téléphone.</span><span class="sxs-lookup"><span data-stu-id="b0247-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="b0247-105">C’est pratique dans les situations où l’utilisation d’un ordinateur pour l’audio peut ne pas être possible.</span><span class="sxs-lookup"><span data-stu-id="b0247-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="b0247-106">Les utilisateurs reçoivent la partie audio de la réunion par le biais de leur téléphone mobile ou de leur ligne fixe et&mdash;de la partie du contenu de la réunion, par exemple lorsqu'&mdash;un autre participant à la réunion partage son écran ou lit une vidéo par le biais de leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b0247-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="b0247-107">L’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="b0247-107">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="b0247-108">Participer à une réunion à l’aide du téléphone pour le son</span><span class="sxs-lookup"><span data-stu-id="b0247-108">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="b0247-109">Cliquez sur **rejoindre** pour participer à une réunion, puis cliquez sur **audio du téléphone** dans l’écran **choisir vos paramètres audio et vidéo** .</span><span class="sxs-lookup"><span data-stu-id="b0247-109">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="b0247-110">À partir de là, les utilisateurs peuvent participer à la réunion et les rejoindre manuellement.</span><span class="sxs-lookup"><span data-stu-id="b0247-110">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Capture d’écran de l’option audio du téléphone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="b0247-112">**Permettre à la réunion teams d’appeler**</span><span class="sxs-lookup"><span data-stu-id="b0247-112">**Let the Teams meeting call**</span></span>

<span data-ttu-id="b0247-113">Sur l’écran **utiliser le téléphone pour l’audio** , l’utilisateur entre son numéro de téléphone, puis clique sur **m’appeler**.</span><span class="sxs-lookup"><span data-stu-id="b0247-113">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="b0247-114">La réunion appelle l’utilisateur et l’associe à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b0247-114">The meeting calls the user and joins them to the meeting.</span></span>

![Capture d’écran de l’option m’appeler sur l’écran utiliser le téléphone pour l’audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="b0247-116">**Composer manuellement**</span><span class="sxs-lookup"><span data-stu-id="b0247-116">**Dial in manually**</span></span>

<span data-ttu-id="b0247-117">Une autre méthode consiste à se connecter directement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b0247-117">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="b0247-118">Sur l’écran **utiliser le téléphone pour l’audio** , cliquez sur **composer manuellement** pour obtenir la liste des numéros de téléphone à utiliser pour vous connecter à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b0247-118">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Capture d’écran de l’option composer en manuel](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="b0247-120">Recevez un appel en cas de problème de l’audio pendant une réunion</span><span class="sxs-lookup"><span data-stu-id="b0247-120">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="b0247-121">Si un utilisateur rencontre des problèmes audio lors de l’utilisation de son ordinateur au cours d’une réunion, l’utilisateur peut facilement basculer vers son téléphone pour l’audio.</span><span class="sxs-lookup"><span data-stu-id="b0247-121">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="b0247-122">Teams détecte l’affichage d’un problème audio ou de périphérique, et redirige l’utilisateur pour qu’il utilise son téléphone en affichant une option **me rappeler** .</span><span class="sxs-lookup"><span data-stu-id="b0247-122">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="b0247-123">Voici un exemple de message et l’option **retour m’appeler** qui s’affiche lorsque Microsoft Teams ne détecte pas de micro.</span><span class="sxs-lookup"><span data-stu-id="b0247-123">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Capture d’écran de l’option me rappeler](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="b0247-125">L’utilisateur clique sur **me**rappeler, ce qui fait apparaître l’écran **utiliser le téléphone pour l’audio** .</span><span class="sxs-lookup"><span data-stu-id="b0247-125">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="b0247-126">À partir de cet emplacement, ils peuvent entrer leur numéro de téléphone et participer à la réunion teams et les rejoindre manuellement.</span><span class="sxs-lookup"><span data-stu-id="b0247-126">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="b0247-127">Configurer la fonctionnalité m’appeler</span><span class="sxs-lookup"><span data-stu-id="b0247-127">Set up the Call me feature</span></span>

<span data-ttu-id="b0247-128">Pour activer la fonctionnalité appeler pour les utilisateurs de votre organisation, les informations suivantes doivent être configurées:</span><span class="sxs-lookup"><span data-stu-id="b0247-128">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="b0247-129">L’option audioconférence est activée pour les utilisateurs de votre organisation qui planifient des réunions (organisateurs de la réunion).</span><span class="sxs-lookup"><span data-stu-id="b0247-129">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="b0247-130">Pour en savoir plus, consultez la rubrique [configurer l’audioconférence pour les équipes](set-up-audio-conferencing-in-teams.md) et [gérer les paramètres de l’audioconférence pour un utilisateur dans teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b0247-130">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="b0247-131">Les utilisateurs peuvent se connecter aux réunions.</span><span class="sxs-lookup"><span data-stu-id="b0247-131">Users can dial out from meetings.</span></span> <span data-ttu-id="b0247-132">Pour en savoir plus, voir [gérer les paramètres d’audioconférence pour un utilisateur dans teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b0247-132">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="b0247-133">Si un utilisateur n’a pas accès à la Conférence rendez-vous pour les réunions activées, l’option **m’appeler** n’est pas disponible et l’utilisateur ne reçoit pas d’appel pour le joindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b0247-133">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="b0247-134">Au lieu de cela, l’utilisateur voit la liste des numéros de téléphone de l’écran **utiliser le téléphone pour l’audio** qu’il peut utiliser pour se connecter manuellement à la réunion sur son téléphone.</span><span class="sxs-lookup"><span data-stu-id="b0247-134">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
