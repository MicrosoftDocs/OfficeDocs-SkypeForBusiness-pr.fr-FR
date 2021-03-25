---
title: Activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres d’audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 6b9e67d8c87b023409b7934a944f298487f91289
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114250"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="e2204-103">Activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres d’audioconférence dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e2204-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e2204-104">Si vous voulez activer ou désactiver l’envoi de courriers électroniques dans Microsoft Teams, consultez activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres de l’audioconférence [dans Microsoft Teams.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="e2204-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="e2204-105">Les utilisateurs sont automatiquement avertis par courrier électronique lorsqu’ils sont activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e2204-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e2204-106">Toutefois, il peut être possible que vous vouliez réduire le nombre de messages électroniques envoyés aux utilisateurs de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e2204-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="e2204-107">Dans ce cas, vous pouvez désactiver l’envoi de courriers électroniques.</span><span class="sxs-lookup"><span data-stu-id="e2204-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="e2204-108">Si vous désactivez l’envoi de courriers électroniques, les messages audioconférences ne seront pas envoyés à vos utilisateurs, y compris les courriers électroniques concernant les moments où les utilisateurs sont activés ou désactivés pour l’audioconférence, lorsque leur code confidentiel est réinitialisé, et lorsque l’ID de conférence et le numéro de téléphone de conférence par défaut changent.</span><span class="sxs-lookup"><span data-stu-id="e2204-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="e2204-109">Voici un exemple du courrier électronique envoyé aux utilisateurs lorsqu’ils sont activés pour l’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="e2204-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Messagerie audioconférence](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="e2204-111">Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="e2204-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="e2204-112">Après avoir activé l’audioconférence, plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="e2204-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="e2204-113">**Lorsqu’une licence d’audioconférence** leur est affectée.</span><span class="sxs-lookup"><span data-stu-id="e2204-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="e2204-114">Lorsque vous réinitialisez manuellement le code confidentiel de l’utilisateur pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e2204-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="e2204-115">Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e2204-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="e2204-116">Lorsque la **licence d’audioconférence** leur est retirée.</span><span class="sxs-lookup"><span data-stu-id="e2204-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="e2204-117">Lorsque le fournisseur de services d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou à **Aucun.**</span><span class="sxs-lookup"><span data-stu-id="e2204-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="e2204-118">Lorsque Microsoft est le fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e2204-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="e2204-119">Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e2204-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="e2204-120">Vous pouvez utiliser le Centre d’administration de Skype Entreprise Windows PowerShell pour activer ou désactiver le courrier électronique envoyé aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e2204-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="e2204-121">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="e2204-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="e2204-122">Dans le **Centre d’administration Skype Entreprise,** dans le panneau de navigation de gauche, cliquez sur **Audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="e2204-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="e2204-123">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="e2204-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="e2204-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e2204-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e2204-125">Vous pouvez également envoyer un courrier électronique à un utilisateur avec les paramètres de conférence audio en sélectionnant Utilisateurs de l’audioconférence, en sélectionnant l’utilisateur et en cliquant sur Envoyer les informations sur la conférence  >  par **courrier électronique.**</span><span class="sxs-lookup"><span data-stu-id="e2204-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="e2204-126">Dans ce cas, un message électronique incluant uniquement l’ID de conférence et le numéro de téléphone de la conférence sera envoyé, mais pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="e2204-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="e2204-127">Pour [plus d’informations,](send-an-email-to-a-user-with-their-dial-in-information.md) voir Envoyer un courrier électronique à un utilisateur avec ses informations d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e2204-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="e2204-128">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="e2204-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="e2204-129">Pour désactiver l’envoi de courriers électroniques, exécutez l’une des exécuter comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2204-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="e2204-130">Pour obtenir de l’aide sur cette cmdlet, voir [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)</span><span class="sxs-lookup"><span data-stu-id="e2204-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="e2204-131">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e2204-131">What else should you know?</span></span>

- <span data-ttu-id="e2204-132">Lorsque les messages automatiques sont désactivés, vous pouvez toujours déclencher l’envoi d’un message électronique avec l’ID de conférence et le numéro de téléphone à l’aide du Centre d’administration Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e2204-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="e2204-133">Toutefois, si vous le faites, le code confidentiel n’est pas inclus.</span><span class="sxs-lookup"><span data-stu-id="e2204-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="e2204-134">Si vous voulez réinitialiser le code confidentiel de l’audioconférence et que l’envoi de courriers électroniques est désactivé, vous devrez l’envoyer à l’utilisateur par un autre moyen.</span><span class="sxs-lookup"><span data-stu-id="e2204-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="e2204-135">L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2204-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e2204-136">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="e2204-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e2204-137">Vous pouvez utiliser ces cmdlets pour gagner du temps ou automatiser ce processus.</span><span class="sxs-lookup"><span data-stu-id="e2204-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="e2204-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2204-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="e2204-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2204-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="e2204-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="e2204-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="e2204-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2204-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="e2204-142">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="e2204-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e2204-143">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="e2204-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e2204-144">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="e2204-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e2204-145">Pourquoi utiliser Microsoft 365 ou PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="e2204-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="e2204-146">[Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e2204-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="e2204-147">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="e2204-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e2204-148">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2204-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e2204-149">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e2204-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e2204-150">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e2204-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e2204-151">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e2204-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="e2204-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="e2204-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2204-154">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e2204-154">Related topics</span></span>

[<span data-ttu-id="e2204-155">Messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="e2204-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="e2204-156">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="e2204-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)