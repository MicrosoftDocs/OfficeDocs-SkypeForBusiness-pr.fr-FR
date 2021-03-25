---
title: Démarrer une audioconférence par téléphone sans code confidentiel dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez comment activer ou désactiver la possibilité pour des appelants anonymes de se joindre aux réunions dans le centre d’administration Skype entreprise ou à l’aide d’un script PowerShell. '
ms.openlocfilehash: 6eb62e2a2a295644185b3f0e6fd424749dc5bf56
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111940"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="9a227-103">Démarrer une audioconférence par téléphone sans code confidentiel dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a227-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="9a227-104">Pour plus d’informations sur le démarrage d’une audioconférence sans code confidentiel dans Microsoft Teams, voir [Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="9a227-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="9a227-105">Il peut être frustrant pour des utilisateurs se composant d’un numéro de téléphone d’être placés dans la salle d’accueil de la réunion, car l’organisateur de la réunion Skype Entreprise n’a pas commencé la réunion.</span><span class="sxs-lookup"><span data-stu-id="9a227-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="9a227-106">Si l’organisateur de la réunion appelle la réunion, un code confidentiel est nécessaire par défaut pour commencer une réunion.</span><span class="sxs-lookup"><span data-stu-id="9a227-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="9a227-107">Vous pouvez configurer de sorte que tout le monde puisse composer le numéro d’accès à une réunion sans être invité à composer un code confidentiel pour commencer la réunion.</span><span class="sxs-lookup"><span data-stu-id="9a227-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="9a227-108">Le Centre d'administration Skype Entreprise permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="9a227-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="9a227-109">Un code confidentiel n’est pas nécessaire pour l’organisateur de la réunion si quelqu’un a commencé la réunion à partir de l’application Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="9a227-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="9a227-110">Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone.</span><span class="sxs-lookup"><span data-stu-id="9a227-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="9a227-111">Le code confidentiel des réunions est envoyé à l’utilisateur audio lorsqu’il est affecté à la licence **Audioconférence** et activé pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="9a227-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="9a227-112">Consultez Envoyer [un courrier](send-an-email-to-a-user-with-their-dial-in-information.md) électronique à un utilisateur avec ses informations d’audioconférence et ses courriers électroniques envoyés automatiquement aux utilisateurs en cas de modification de [leurs paramètres.](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="9a227-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="9a227-113">Autorisation ou refus des appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="9a227-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="9a227-114">Dans le **Centre d’administration Skype** Entreprise, dans le panneau de navigation de gauche, allez à **Utilisateurs de l’audioconférence.**  >  </span><span class="sxs-lookup"><span data-stu-id="9a227-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="9a227-115">Dans la liste, sélectionnez l’utilisateur, puis dans le volet Action, cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="9a227-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="9a227-116">Dans la page Propriétés de l’utilisateur, sous **Options** de réunion, sélectionnez ou désélectisz l’option Autoriser les appelants non authentifiés à être les premiers utilisateurs **d’une réunion. Si ce n’est pas le cas, il attend dans la salle d’attente jusqu’à ce qu’un utilisateur authentifié participe.**</span><span class="sxs-lookup"><span data-stu-id="9a227-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="9a227-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9a227-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="9a227-118">**Utilisation de Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="9a227-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="9a227-119">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9a227-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="9a227-120">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9a227-120">What else should you know?</span></span>

- <span data-ttu-id="9a227-121">Si vous voulez réinitialiser le code confidentiel, consultez Réinitialiser le code confidentiel de [l’audioconférence.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="9a227-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="9a227-122">Si l’accès est anonyme ou si vous n’avez pas besoin d’un code confidentiel pour commencer une réunion, est désactivé :</span><span class="sxs-lookup"><span data-stu-id="9a227-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="9a227-123">Si la réunion n’a pas commencé (il n’y a pas encore de personne dans la réunion) : un appelant sera invité à s’en faire l’organisateur. S’il répond Oui, il est invité à saisir son code confidentiel. Une fois qu’il entre le code confidentiel, la réunion commence et l’utilisateur rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="9a227-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="9a227-124">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="9a227-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="9a227-125">Si l’accès est anonyme ou si vous n’avez pas besoin d’un code confidentiel pour commencer une réunion, est activé :</span><span class="sxs-lookup"><span data-stu-id="9a227-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="9a227-126">Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="9a227-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="9a227-127">Étant donné que le paramètre de l’organisateur est réglé sur Off, la réunion démarre et les appelants anonymes la rejoignent.</span><span class="sxs-lookup"><span data-stu-id="9a227-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="9a227-128">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="9a227-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9a227-129">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="9a227-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9a227-130">Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="9a227-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="9a227-131">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="9a227-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9a227-132">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="9a227-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9a227-133">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="9a227-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9a227-134">Pourquoi utiliser Microsoft 365 ou PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="9a227-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="9a227-135">[Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9a227-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="9a227-136">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez les paramètres de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="9a227-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="9a227-137">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a227-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="9a227-138">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a227-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="9a227-139">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a227-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9a227-140">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a227-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="9a227-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="9a227-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9a227-143">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9a227-143">Related topics</span></span>

[<span data-ttu-id="9a227-144">Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="9a227-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)