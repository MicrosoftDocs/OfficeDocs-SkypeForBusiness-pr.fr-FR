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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164263"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="4f027-103">Activation ou désactivation de l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4f027-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="4f027-104">Si vous souhaitez activer ou désactiver l’envoi de courriers électroniques dans Microsoft Teams, voir [activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Microsoft teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4f027-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="4f027-105">Les utilisateurs sont automatiquement avertis par courrier lorsqu’ils sont activés pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="4f027-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="4f027-106">Toutefois, il peut arriver que vous souhaitiez réduire le nombre de messages électroniques envoyés aux utilisateurs de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4f027-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="4f027-107">Dans ces cas, vous pouvez désactiver l’envoi de messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="4f027-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="4f027-108">Si vous désactivez l’envoi de courriers électroniques, les messages électroniques de l’audioconférence ne seront envoyés à vos utilisateurs, y compris les messages électroniques pour lesquels les utilisateurs sont activés ou désactivés pour les conférences audio, la réinitialisation de leur code confidentiel et le changement de l’ID de conférence et du numéro de téléphone de la Conférence par défaut.</span><span class="sxs-lookup"><span data-stu-id="4f027-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="4f027-109">Voici un exemple de message électronique envoyé aux utilisateurs lorsqu’ils sont activés pour les conférences audio :</span><span class="sxs-lookup"><span data-stu-id="4f027-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Messagerie de l’audioconférence](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="4f027-111">Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="4f027-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="4f027-112">Plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation après leur activation pour l’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="4f027-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="4f027-113">Lorsqu’une licence de **conférence audio** leur est affectée.</span><span class="sxs-lookup"><span data-stu-id="4f027-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="4f027-114">Lorsque vous réinitialisez manuellement le code confidentiel de l’audioconférence de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f027-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="4f027-115">Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f027-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="4f027-116">Lorsque la licence de **conférence audio** y est supprimée.</span><span class="sxs-lookup"><span data-stu-id="4f027-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="4f027-117">Lorsque le fournisseur de services d’audioconférence d’un utilisateur est passé de Microsoft à un autre fournisseur ou à **aucun**.</span><span class="sxs-lookup"><span data-stu-id="4f027-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="4f027-118">Lorsque Microsoft est remplacé par le fournisseur de services d’audioconférence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f027-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="4f027-119">Activation ou désactivation de l’envoi de messages électroniques aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4f027-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="4f027-120">Vous pouvez utiliser le centre d’administration Skype entreprise ou Windows PowerShell pour activer ou désactiver les messages envoyés aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4f027-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="4f027-121">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="4f027-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="4f027-122">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, cliquez sur **audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="4f027-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="4f027-123">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="4f027-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="4f027-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4f027-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="4f027-125">Vous pouvez également envoyer un courrier électronique à un utilisateur avec les paramètres de l’audioconférence en accédant aux**utilisateurs**de l' **audioconférence** > , en sélectionnant l’utilisateur, puis en cliquant sur **Envoyer les informations sur la Conférence par courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="4f027-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="4f027-126">Dans ce cas, un message électronique est envoyé, qui inclut l’ID de conférence et le numéro de téléphone de la Conférence, mais pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="4f027-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="4f027-127">Pour plus d’informations, voir [Envoyer un courrier électronique à un utilisateur avec ses informations de conférence audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="4f027-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="4f027-128">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="4f027-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="4f027-129">Pour désactiver l’envoi de courriers électroniques, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4f027-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="4f027-130">Pour obtenir de l’aide sur cette cmdlet, voir [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="4f027-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="4f027-131">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4f027-131">What else should you know?</span></span>

- <span data-ttu-id="4f027-132">Lorsque les messages électroniques automatiques sont désactivés, vous pouvez toujours déclencher manuellement l’envoi d’un courrier électronique contenant l’ID de la Conférence et le numéro de téléphone à l’aide du centre d’administration Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4f027-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="4f027-133">Toutefois, le code confidentiel n’est pas inclus.</span><span class="sxs-lookup"><span data-stu-id="4f027-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="4f027-134">Si vous souhaitez réinitialiser le code confidentiel de l’audioconférence et que l’envoi des courriers électroniques est désactivé, vous devez l’envoyer à l’utilisateur d’une autre manière.</span><span class="sxs-lookup"><span data-stu-id="4f027-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="4f027-135">L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f027-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4f027-136">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="4f027-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4f027-137">Vous pouvez utiliser ces applets pour gagner du temps ou automatiser cette opération.</span><span class="sxs-lookup"><span data-stu-id="4f027-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="4f027-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="4f027-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="4f027-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="4f027-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="4f027-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f027-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="4f027-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="4f027-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="4f027-142">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="4f027-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4f027-143">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="4f027-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4f027-144">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="4f027-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4f027-145">Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f027-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4f027-146">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f027-146">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4f027-147">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="4f027-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4f027-148">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f027-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="4f027-149">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4f027-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4f027-150">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4f027-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4f027-151">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4f027-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4f027-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="4f027-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4f027-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f027-154">Related topics</span></span>

[<span data-ttu-id="4f027-155">Courriers électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres de conférence audio</span><span class="sxs-lookup"><span data-stu-id="4f027-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="4f027-156">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="4f027-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


