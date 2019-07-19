---
title: Activation ou désactivation de l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Skype entreprise Online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 28da70d829972a7b9d3659290652c2482d409364
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792327"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="9a4a3-103">Activation ou désactivation de l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a4a3-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="9a4a3-104">Si vous souhaitez activer ou désactiver l’envoi de courriers électroniques dans Microsoft Teams, voir [activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Microsoft teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="9a4a3-105">Les utilisateurs sont automatiquement avertis par courrier lorsqu’ils sont activés pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="9a4a3-106">Toutefois, il peut arriver que vous souhaitiez réduire le nombre de messages électroniques envoyés aux utilisateurs de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="9a4a3-107">Dans ces cas, vous pouvez désactiver l’envoi de messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="9a4a3-108">Si vous désactivez l’envoi de courriers électroniques, les messages électroniques de l’audioconférence ne seront envoyés à vos utilisateurs, y compris les messages électroniques pour lesquels les utilisateurs sont activés ou désactivés pour les conférences audio, lorsque leur code confidentiel est réinitialisé et lorsque l’ID de conférence et le numéro de téléphone de la Conférence par défaut changent. .</span><span class="sxs-lookup"><span data-stu-id="9a4a3-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="9a4a3-109">Voici un exemple de message électronique envoyé aux utilisateurs lorsqu’ils sont activés pour les conférences audio:</span><span class="sxs-lookup"><span data-stu-id="9a4a3-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Messagerie de l’audioconférence](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="9a4a3-111">Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="9a4a3-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="9a4a3-112">Plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation après leur activation pour l’audioconférence:</span><span class="sxs-lookup"><span data-stu-id="9a4a3-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="9a4a3-113">Lorsqu’une licence de **conférence audio** leur est affectée.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="9a4a3-114">Lorsque vous réinitialisez manuellement le code confidentiel de l’audioconférence de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="9a4a3-115">Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="9a4a3-116">Lorsque la licence de **conférence audio** y est supprimée.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="9a4a3-117">Lorsque le fournisseur de services d’audioconférence d’un utilisateur est passé de Microsoft à un autre fournisseur ou à **aucun**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="9a4a3-118">Lorsque Microsoft est remplacé par le fournisseur de services d’audioconférence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="9a4a3-119">Activation ou désactivation de l’envoi de messages électroniques aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9a4a3-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="9a4a3-120">Vous pouvez utiliser le centre d’administration Skype entreprise ou Windows PowerShell pour activer ou désactiver les messages envoyés aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="9a4a3-121">![Icône illustrant le logo](../images/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="9a4a3-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="9a4a3-122">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, cliquez sur **audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="9a4a3-123">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="9a4a3-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9a4a3-125">Vous pouvez également envoyer un courrier électronique à un utilisateur avec les paramètres de l’audioconférence en accédant aux**utilisateurs**de l' **audioconférence** > , en sélectionnant l’utilisateur, puis en cliquant sur **Envoyer les informations sur la Conférence par courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="9a4a3-126">Dans ce cas, un message électronique est envoyé, qui inclut l’ID de conférence et le numéro de téléphone de la Conférence, mais pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="9a4a3-127">Pour plus d’informations, voir [Envoyer un courrier électronique à un utilisateur avec ses informations de conférence audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="9a4a3-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="9a4a3-128">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="9a4a3-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="9a4a3-129">Pour désactiver l’envoi de courriers électroniques, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="9a4a3-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="9a4a3-130">Pour obtenir de l’aide sur cette cmdlet, voir [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="9a4a3-131">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9a4a3-131">What else should you know?</span></span>

- <span data-ttu-id="9a4a3-132">Lorsque les messages électroniques automatiques sont désactivés, vous pouvez toujours déclencher manuellement l’envoi d’un courrier électronique contenant l’ID de la Conférence et le numéro de téléphone à l’aide du centre d’administration Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="9a4a3-133">Toutefois, le code confidentiel n’est pas inclus.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="9a4a3-134">Si vous souhaitez réinitialiser le code confidentiel de l’audioconférence et que l’envoi des courriers électroniques est désactivé, vous devez l’envoyer à l’utilisateur d’une autre manière.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="9a4a3-135">L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9a4a3-136">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="9a4a3-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9a4a3-137">Vous pouvez utiliser ces applets pour gagner du temps ou automatiser cette opération.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="9a4a3-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="9a4a3-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="9a4a3-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="9a4a3-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="9a4a3-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a4a3-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="9a4a3-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="9a4a3-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="9a4a3-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a4a3-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9a4a3-145">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a4a3-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9a4a3-146">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a4a3-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="9a4a3-147">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="9a4a3-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9a4a3-148">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a4a3-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="9a4a3-149">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a4a3-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9a4a3-150">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a4a3-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9a4a3-151">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9a4a3-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="9a4a3-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="9a4a3-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9a4a3-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a4a3-154">Related topics</span></span>

[<span data-ttu-id="9a4a3-155">Courriers électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres de conférence audio</span><span class="sxs-lookup"><span data-stu-id="9a4a3-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="9a4a3-156">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="9a4a3-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


