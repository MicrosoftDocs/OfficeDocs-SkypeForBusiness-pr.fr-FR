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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment activer ou désactiver la possibilité pour des appelants anonymes de se joindre aux réunions dans le centre d’administration Skype entreprise ou à l’aide d’un script PowerShell. '
ms.openlocfilehash: 1cdcbd2f610c3d60ba2fb4e554823d410fd4ae8f
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792639"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="db3cc-103">Démarrer une audioconférence par téléphone sans code confidentiel dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="db3cc-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="db3cc-104">Pour plus d’informations sur le démarrage d’une audioconférence sans code confidentiel dans Microsoft Teams, voir [Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="db3cc-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="db3cc-105">Il peut être frustrant pour des utilisateurs qui composent le numéro de téléphone d’une réunion d’être conservés dans la salle d’attente de la réunion, car l’organisateur de la réunion Skype entreprise n’a pas encore commencé la réunion.</span><span class="sxs-lookup"><span data-stu-id="db3cc-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="db3cc-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span><span class="sxs-lookup"><span data-stu-id="db3cc-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="db3cc-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="db3cc-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="db3cc-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span><span class="sxs-lookup"><span data-stu-id="db3cc-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="db3cc-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="db3cc-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="db3cc-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="db3cc-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="db3cc-113">Autorisation ou refus des appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="db3cc-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="db3cc-114">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation gauche, accédez à**utilisateurs**de l' **audioconférence** > .</span><span class="sxs-lookup"><span data-stu-id="db3cc-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="db3cc-115">Dans la liste, sélectionnez l’utilisateur, puis, dans le volet action, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="db3cc-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="db3cc-116">Sur la page des propriétés de l’utilisateur, sous options de la **réunion**, activez ou désactivez **l’option autoriser les appelants non authentifiés comme premiers participants à une réunion. Si ce n’est pas le cas, il attend dans la salle d’attente jusqu’à ce qu’un utilisateur authentifié y adhère**.</span><span class="sxs-lookup"><span data-stu-id="db3cc-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="db3cc-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="db3cc-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="db3cc-118">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="db3cc-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="db3cc-119">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="db3cc-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="db3cc-120">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="db3cc-120">What else should you know?</span></span>

- <span data-ttu-id="db3cc-121">Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la rubrique réinitialisation [du code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="db3cc-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="db3cc-122">Si l’accès anonyme ou ne nécessite pas un code confidentiel pour démarrer une réunion, est désactivé:</span><span class="sxs-lookup"><span data-stu-id="db3cc-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="db3cc-123">Si la réunion n’a pas commencé (il n’y a pas encore de compte dans la réunion): un appelant sera invité s’il s’agit de l’organisateur; s’il répond oui, il est invité à entrer son code confidentiel et, après avoir entré son code confidentiel, la réunion démarre et l’utilisateur se connecte à la réunion.</span><span class="sxs-lookup"><span data-stu-id="db3cc-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="db3cc-124">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="db3cc-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="db3cc-125">Si vous avez accès anonyme ou si vous n’avez pas besoin d’un code confidentiel pour démarrer une réunion, est activé:</span><span class="sxs-lookup"><span data-stu-id="db3cc-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="db3cc-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span><span class="sxs-lookup"><span data-stu-id="db3cc-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="db3cc-128">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="db3cc-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="db3cc-129">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="db3cc-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="db3cc-130">Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="db3cc-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="db3cc-p104">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="db3cc-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="db3cc-134">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="db3cc-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="db3cc-135">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db3cc-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="db3cc-136">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité qui consiste à utiliser le centre d’administration Microsoft 365, par exemple, lorsque vous modifiez les paramètres de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="db3cc-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="db3cc-137">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="db3cc-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="db3cc-138">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="db3cc-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="db3cc-139">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="db3cc-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="db3cc-140">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="db3cc-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="db3cc-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="db3cc-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="db3cc-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db3cc-143">Related topics</span></span>

[<span data-ttu-id="db3cc-144">Tester ou acheter l’audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="db3cc-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
