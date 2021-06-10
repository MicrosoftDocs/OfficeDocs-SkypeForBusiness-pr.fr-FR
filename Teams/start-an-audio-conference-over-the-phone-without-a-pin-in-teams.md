---
title: Démarrer une audioconférence par téléphone sans code confidentiel dans Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Découvrez comment activer ou désactiver l’accès des appelants anonymes à une réunion à partir du Teams d’administration. '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116962"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="8b272-103">Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b272-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="8b272-104">Il peut être frustrant pour des utilisateurs qui se sont appelés à une réunion d’être placés dans la salle d’accueil de la réunion à l’écoute de la musique, car l’organisateur de la réunion Microsoft Teams n’a pas commencé la réunion.</span><span class="sxs-lookup"><span data-stu-id="8b272-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="8b272-105">Si l’organisateur de la réunion appelle la réunion, un code confidentiel est nécessaire par défaut pour commencer une réunion.</span><span class="sxs-lookup"><span data-stu-id="8b272-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="8b272-106">Vous pouvez configurer de sorte que tout le monde puisse composer le numéro de téléphone d’une réunion sans être invité à composer un code confidentiel pour commencer la réunion.</span><span class="sxs-lookup"><span data-stu-id="8b272-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="8b272-107">Vous pouvez utiliser le Centre d’administration pour activer ou désactiver ce paramètre pour un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b272-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="8b272-108">Un code confidentiel n’est pas nécessaire pour l’organisateur de la réunion si quelqu’un a commencé la réunion à partir de l Microsoft Teams appeille de messagerie.</span><span class="sxs-lookup"><span data-stu-id="8b272-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="8b272-109">Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone.</span><span class="sxs-lookup"><span data-stu-id="8b272-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="8b272-110">Le code confidentiel des réunions est envoyé à l’utilisateur audio lorsqu’il est affecté à la licence **Audioconférence** et activé pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="8b272-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="8b272-111">Consultez [envoyer un courrier](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) électronique à un utilisateur avec ses informations d’audioconférence et des messages électroniques envoyés automatiquement aux utilisateurs en cas de modification de [leurs paramètres.](emails-sent-to-users-when-their-settings-change-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8b272-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="8b272-112">Autorisation ou refus des appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="8b272-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="8b272-113">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="8b272-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8b272-114">Dans le groupe de navigation de gauche, cliquez sur **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="8b272-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="8b272-115">Sélectionnez un utilisateur dans la liste, puis cliquez sur **Modifier** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="8b272-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="8b272-116">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="8b272-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="8b272-117">Dans le **volet Audioconférence,** les appelants peuvent être la première personne à avoir accès **à une réunion.**</span><span class="sxs-lookup"><span data-stu-id="8b272-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="8b272-118">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="8b272-118">Click **Apply**.</span></span> 

<span data-ttu-id="8b272-119">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="8b272-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="8b272-120">Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="8b272-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="8b272-121">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8b272-121">What else should you know?</span></span>

- <span data-ttu-id="8b272-122">Si vous voulez réinitialiser le code confidentiel, consultez Réinitialiser le code confidentiel de [l’audioconférence.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8b272-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="8b272-123">Si l’accès est anonyme ou si vous n’avez pas besoin d’un code confidentiel pour commencer une réunion, est désactivé :</span><span class="sxs-lookup"><span data-stu-id="8b272-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="8b272-124">Si la réunion n’a pas commencé (il n’y a pas encore de personne dans la réunion) : un appelant sera invité à en être l’organisateur. S’il répond Oui, il est invité à saisir son code confidentiel. Une fois qu’il entre le code confidentiel, la réunion commence et l’utilisateur rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="8b272-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="8b272-125">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="8b272-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="8b272-126">Si l’accès est anonyme ou si vous n’avez pas besoin d’un code confidentiel pour commencer une réunion, est activé :</span><span class="sxs-lookup"><span data-stu-id="8b272-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="8b272-127">Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="8b272-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="8b272-128">Étant donné que le paramètre de l’organisateur est réglé sur Off, la réunion démarre et les appelants anonymes la rejoignent.</span><span class="sxs-lookup"><span data-stu-id="8b272-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="8b272-129">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="8b272-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8b272-130">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="8b272-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="8b272-131">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="8b272-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8b272-132">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="8b272-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8b272-133">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="8b272-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8b272-134">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b272-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="8b272-135">[Meilleures méthodes pour gérer vos Microsoft 365 vos Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="8b272-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="8b272-136">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="8b272-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8b272-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8b272-137">Related topics</span></span>

[<span data-ttu-id="8b272-138">Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="8b272-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)