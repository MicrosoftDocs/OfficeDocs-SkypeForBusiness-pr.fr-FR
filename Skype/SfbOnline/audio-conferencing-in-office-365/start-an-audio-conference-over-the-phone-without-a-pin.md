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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment activer ou désactiver la possibilité pour des appelants anonymes de se joindre aux réunions dans le centre d’administration Skype entreprise ou à l’aide d’un script PowerShell. '
ms.openlocfilehash: 746e21b7b1a8d15c31dfe11e46ac09edfbb29b99
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858704"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="4ba1c-103">Démarrer une audioconférence par téléphone sans code confidentiel dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ba1c-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="4ba1c-104">Pour plus d’informations sur le démarrage d’une audioconférence sans code confidentiel dans Microsoft Teams, voir [Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4ba1c-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="4ba1c-105">Il peut être frustrant pour des utilisateurs qui composent le numéro de téléphone d'une réunion d'être placés en file d'attente de la réunion, car l'organisateur de la réunion Skype Entreprise n'a pas encore lancé l'événement.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because an organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="4ba1c-106">L'organisateur doit appeler la réunion et un code confidentiel lui est demandé par défaut pour que la réunion puisse commencer.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-106">If a meeting organizer calls into their meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="4ba1c-107">Vous pouvez modifier ce paramètre pour que n'importe qui puisse composer le numéro de téléphone de la réunion et la commence sans avoir à composer de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-107">You can set it up so that anyone can dial in to the meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="4ba1c-108">Le Centre d'administration Skype Entreprise permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="4ba1c-p102">Un code confidentiel n'est pas nécessaire pour l'organisateur de la réunion si quelqu'un a commencé la réunion à partir de l'application Skype Entreprise. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion rejoint sa réunion par téléphone. Le code confidentiel des réunions est envoyé aux utilisateurs audio qui possèdent une **licence de réunion audio** ou pour lesquels la fonction d'audioconférence est activée. Reportez-vous aux rubriques[Envoyer un message électronique à un utilisateur avec leurs informations d'audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md) et[Courriers électroniques envoyés automatiquement aux utilisateurs en cas de modification de leurs paramètres d'audioconférence](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="4ba1c-p102">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business client. A PIN is only required when a meeting organizer joins their meeting over a phone. The PIN for meetings is sent to the dial-in user when they are assigned the **Skype for Business PSTN Conferencing** license or are enabled for dial-in conferencing. See,[Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and[Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="4ba1c-113">Autorisation ou refus des appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="4ba1c-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="4ba1c-114">Dans le **centre d'administration Skype Entreprise**, au sein du menu de navigation de gauche, accédez à **Audioconférence** > **Utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="4ba1c-114">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Dial-in users**.</span></span> 
    
2. <span data-ttu-id="4ba1c-115">Dans la liste, sélectionnez l'utilisateur et, dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-115">In the list select the user and on the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="4ba1c-116">Dans la page Propriétés de l'utilisateur, sous **Options de réunion**, activez ou désactivez la case à cocher **Autoriser les appelants non authentifiés à être les premiers participants d'une réunion. Si ce n'est pas le cas, ils se trouveront en file d'attente jusqu'à ce qu'un utilisateur authentifié participe**.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-116">On the user's properties page, under **Meeting options**, check or uncheck **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="4ba1c-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="4ba1c-118">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4ba1c-118">\*\*\*\* Using Windows PowerShell</span></span>
  
- <span data-ttu-id="4ba1c-119">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4ba1c-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="4ba1c-120">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4ba1c-120">What else should you know?</span></span>

- <span data-ttu-id="4ba1c-121">Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la rubrique [Réinitialiser le code confidentiel d'audioconférence pour un utilisateur](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="4ba1c-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="4ba1c-122">Si l'accès anonyme, ou la saisie facultative d'un code confidentiel pour le début d'une réunion, est activé :</span><span class="sxs-lookup"><span data-stu-id="4ba1c-122">If anonymous access or not requiring a PIN to start a meeting is enabled:</span></span>
    
  - <span data-ttu-id="4ba1c-123">Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : un appelant est invité s’il est l’organisateur ; s'il indique Oui, il lui est demandé de saisir son code confidentiel et une fois le code confidentiel saisi, la réunion sera démarrée et l’utilisateur y participera.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-123">A caller will be prompted if he's the organizer, if he says yes, he'll be prompted for his PIN after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="4ba1c-124">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="4ba1c-125">Si l'accès anonyme, ou la saisie facultative d'un code confidentiel pour le début d'une réunion, est désactivée :</span><span class="sxs-lookup"><span data-stu-id="4ba1c-125">If anonymous access or not requiring a PIN to start a meeting is disabled:</span></span>
    
  - <span data-ttu-id="4ba1c-126">Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="4ba1c-127">Étant donné que le paramétrage de l'organisateur est défini sur Désactivé, la réunion commence et les appelants anonymes peuvent participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-127">Because the setting of the organizer is set to off, the meeting will start and the anonymouscallers will join the meeting.</span></span>
    
  - <span data-ttu-id="4ba1c-128">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4ba1c-129">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="4ba1c-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4ba1c-130">Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="4ba1c-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="4ba1c-p104">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ba1c-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4ba1c-134">Pourquoi utiliser Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ba1c-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4ba1c-135">Meilleurs façons d'utiliser Windows PowerShell pour gérer Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba1c-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4ba1c-136">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à la seule utilisation du centre d’administration Office 365, par exemple lorsque vous faites des modifications de paramètres pour beaucoup d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="4ba1c-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4ba1c-137">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ba1c-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="4ba1c-138">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ba1c-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="4ba1c-139">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ba1c-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4ba1c-140">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ba1c-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4ba1c-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="4ba1c-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4ba1c-143">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4ba1c-143">Related topics</span></span>

[<span data-ttu-id="4ba1c-144">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba1c-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
