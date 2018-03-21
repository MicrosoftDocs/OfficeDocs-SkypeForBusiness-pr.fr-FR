---
title: "Activer ou désactiver l’envoi de messages électroniques lors de la modifient de leurs paramètres"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 2e8f4975e96531c02cbc2c1a05b4b615829f9205
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="66771-103">Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="66771-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="66771-104">Les utilisateurs sont automatiquement avertis par e-mail lorsqu’ils sont activés pour les conférences Audio.</span><span class="sxs-lookup"><span data-stu-id="66771-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="66771-105">Il peut arriver, cependant, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés à Skype pour des utilisateurs professionnels et Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66771-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="66771-106">Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="66771-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="66771-107">Si vous désactivez l’envoi de courriers électroniques, les e-mails de conférence Audio ne seront pas envoyées à vos utilisateurs, y compris les e-mails pour lorsque les utilisateurs sont activés ou désactivés pour la conférence audio, lorsque leur code PIN est réinitialisé, et lors de modifications de numéro de téléphone de l’ID de conférence et la conférence par défaut .</span><span class="sxs-lookup"><span data-stu-id="66771-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="66771-108">Voici un exemple du courriel envoyé aux utilisateurs lorsqu’ils sont activés pour les conférences Audio :</span><span class="sxs-lookup"><span data-stu-id="66771-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Audio conférence par courrier électronique](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="66771-110">Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="66771-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="66771-111">Il existe plusieurs messages électroniques qui sont envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :</span><span class="sxs-lookup"><span data-stu-id="66771-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="66771-112">Lorsqu’une licence **Audioconférence** est attribuée.</span><span class="sxs-lookup"><span data-stu-id="66771-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="66771-113">Lorsque vous effectuez manuellement la conférence code PIN de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66771-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="66771-114">Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66771-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="66771-115">Lorsque la licence **d’Audioconférence** est supprimée à partir de ceux-ci.</span><span class="sxs-lookup"><span data-stu-id="66771-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="66771-116">Lorsque le fournisseur de conférence audio d’un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="66771-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="66771-117">Lorsque le fournisseur de conférence audio d’un utilisateur est modifié à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66771-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="66771-118">Activer ou désactiver l’envoi pour les utilisateurs de courrier</span><span class="sxs-lookup"><span data-stu-id="66771-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="66771-119">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="66771-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="66771-120">Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="66771-120">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="66771-121">Utilisation du Centre d'administration Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="66771-121">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="66771-122">Accédez au **Centre d’administration Office 365** > **Skype pour les entreprises**et de la navigation de gauche, cliquez sur **audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="66771-122">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="66771-123">Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de conférence audio changent**.</span><span class="sxs-lookup"><span data-stu-id="66771-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="66771-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="66771-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="66771-125">Vous pouvez également envoyer des e-mail à un utilisateur avec les paramètres de conférence audio en accédant à **l’audioconférence** > **les utilisateurs**, la sélection de l’utilisateur et en cliquant sur **Envoyer par courrier électronique, les informations de conférence**.</span><span class="sxs-lookup"><span data-stu-id="66771-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="66771-126">Si vous le faites, un e-mail sera envoyé qui inclut uniquement les ID de conférence et numéro de téléphone de conférence, mais pas le code PIN.</span><span class="sxs-lookup"><span data-stu-id="66771-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="66771-127">Pour plus d’informations, reportez-vous à la section [Envoyer un courrier électronique à un utilisateur avec les informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="66771-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
 <span data-ttu-id="66771-128">Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.</span><span class="sxs-lookup"><span data-stu-id="66771-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="66771-129">Exécutez la commande suivante pour désactiver l’envoi de messages électroniques :</span><span class="sxs-lookup"><span data-stu-id="66771-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="66771-130">Pour obtenir de l’aide avec cette applet de commande, consultez [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="66771-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="66771-131">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="66771-131">What else should you know?</span></span>

- <span data-ttu-id="66771-132">Lorsque les courriels automatiques sont désactivées, vous pouvez manuellement déclencher l’envoi d’un e-mail avec le numéro de téléphone et les ID de conférence utilisant le Skype pour le centre d’administration de Business.</span><span class="sxs-lookup"><span data-stu-id="66771-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="66771-133">Toutefois, si vous le faites, le code confidentiel ne sera inclus.</span><span class="sxs-lookup"><span data-stu-id="66771-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="66771-134">Si vous voulez réinitialiser la code PIN de conférence audio et l’envoi d’e-mails est désactivé, vous devrez envoyer à l’utilisateur d’une autre manière.</span><span class="sxs-lookup"><span data-stu-id="66771-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="66771-135">Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse e-mail et afficher le nom à l’aide de Windows PowerShell et également utiliser l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="66771-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="66771-136">Si vous souhaitez modifier les informations d’adresse de messagerie, vous avez besoin pour vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les e-mails provenant de personnalisé spécifié à partir de l’adresse.</span><span class="sxs-lookup"><span data-stu-id="66771-136">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="66771-137">entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;</span><span class="sxs-lookup"><span data-stu-id="66771-137">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="66771-138">entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="66771-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="66771-139">Définissez le paramètre _SendEmailOverride_ sur _True_.</span><span class="sxs-lookup"><span data-stu-id="66771-139">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="66771-140">L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66771-140">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="66771-141">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="66771-141">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="66771-142">Ces applets de commande vous permet de gagner du temps ou d’automatiser cette action.</span><span class="sxs-lookup"><span data-stu-id="66771-142">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="66771-143">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="66771-143">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="66771-144">Supprimer-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="66771-144">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="66771-145">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="66771-145">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="66771-146">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="66771-146">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="66771-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="66771-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="66771-150">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="66771-150">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="66771-151">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="66771-151">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="66771-152">Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="66771-152">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="66771-153">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="66771-153">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="66771-154">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="66771-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="66771-155">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="66771-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="66771-156">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="66771-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="66771-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="66771-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="66771-159">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="66771-159">Related topics</span></span>

[<span data-ttu-id="66771-160">E-mails envoyés aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="66771-160">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="66771-161">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="66771-161">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)

[<span data-ttu-id="66771-162">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="66771-162">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
