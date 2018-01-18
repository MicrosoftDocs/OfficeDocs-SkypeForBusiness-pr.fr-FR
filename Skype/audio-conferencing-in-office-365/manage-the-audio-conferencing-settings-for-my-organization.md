---
title: "Gestion des paramètres de conférence rendez-vous de mon organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="50212-103">Gestion des paramètres de conférence rendez-vous de mon organisation</span><span class="sxs-lookup"><span data-stu-id="50212-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="50212-104">[] Il peut être préférable d'afficher tous les paramètres de conférence rendez-vous à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="50212-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="50212-105">Affecter une licence de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="50212-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="50212-106">Vous ne pouvez attribuer des licences à l’aide de la **Skype pour le centre d’administration Business**.</span><span class="sxs-lookup"><span data-stu-id="50212-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="50212-107">Vous devez utiliser le centre d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="50212-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="50212-108">Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="50212-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="50212-109">Pour affecter une licence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="50212-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="50212-110">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-111">Dans la navigation gauche du **Centre d’administration Office 365**, consultez la rubrique **utilisateurs** > **utilisateurs actifs**, puis sélectionnez les utilisateurs à partir de la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="50212-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50212-p102">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**. Vous pouvez également affecter des licences à plusieurs utilisateurs à l'aide de Windows Powershell. Pour obtenir des informations et des exemples de scripts Powershell, reportez-vous à la rubrique [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="50212-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="50212-116">Dans le volet Action sous **Licence affectée**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="50212-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="50212-p103">Sur la page **Affecter une licence**, cochez **Conférence RTC Skype Entreprise**, puis cliquez sur **Enregistrer**. Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="50212-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="50212-p104">Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="50212-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="50212-121">Affecter un ID de conférence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="50212-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="50212-p105">Affectation d'un ID de conférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="50212-p105">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider. The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="50212-124">ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou choisir celui qui est facile à mémoriser.</span><span class="sxs-lookup"><span data-stu-id="50212-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="50212-125">Lorsque l’ID de conférence dynamiques sont utilisés, chaque réunion une planification de l’utilisateur sera obtenir une conférence unique ID attribué</span><span class="sxs-lookup"><span data-stu-id="50212-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="50212-126">Si vous souhaitez affecter les dynamique au lieu de l’ID de conférence statique, reportez-vous [à l’aide de l’audioconférence dynamique d’ID dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="50212-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="50212-127">Le Skype pour Business admin center ne peut pas servir à affecter un ID de conférence à un utilisateur, mais vous pouvez utiliser l’applet de commande Windows PowerShell pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="50212-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="50212-128">Contrairement à l'applet de commande Windows PowerShell, le Centre d'administration Skype Entreprise ne permet pas d'affecter un ID de conférence à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50212-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="50212-129">Pour définir l'ID de conférence d'un utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="50212-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="50212-130">Un ID de conférence doit comporter sept chiffres, et vous ne pouvez pas le modifier dans le Centre d'administration Skype Entreprise ou à l'aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50212-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="50212-131">Après avoir créé un nouvel ID de conférence, l’ancien ID de conférence ne peut pas être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="50212-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="50212-132">Vous devez avertir les utilisateurs de replanifier les invitations pour vous assurer que la nouvelle conférence QU'ID est ajouté pour les invitations aux réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="50212-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="50212-133">Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business mise à jour de leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="50212-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="50212-134">Pour savoir comment télécharger, installer et exécuter le Skype pour l’outil de mise à jour de réunion Professionnel, consultez : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, l’outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online, réunion L’outil de migration (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="50212-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="50212-135">Reportez-vous à la section [Afficher, modifier et réinitialiser un ID de conférence attribué à un utilisateur](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="50212-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="50212-136">Modifier le fournisseur de conférence audio de Microsoft, à un fournisseur tiers</span><span class="sxs-lookup"><span data-stu-id="50212-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="50212-137">Remplacement du fournisseur de conférence rendez-vous Microsoft par un fournisseur tiers</span><span class="sxs-lookup"><span data-stu-id="50212-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-138">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-139">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**, puis sur et sélectionnez l’utilisateur que vous souhaitez modifier le fournisseur de conférence audio de.</span><span class="sxs-lookup"><span data-stu-id="50212-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="50212-140">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="50212-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="50212-141">Sur la page de **Propriétés** , sous **le nom du fournisseur**, sélectionnez le fournisseur de conférence audio pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50212-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50212-142">Vous ne pouvez sélectionner Microsoft comme le fournisseur de conférence audio, ou **None** si vous avez sélectionné plusieurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50212-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="50212-143">Si vous avez sélectionné plusieurs utilisateurs, vous ne pouvez sélectionner que Microsoft comme fournisseur de conférence rendez-vous, ou l'option **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="50212-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="50212-144">Activer ou désactiver les courriers électroniques envoyés à des utilisateurs de conférence audio</span><span class="sxs-lookup"><span data-stu-id="50212-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="50212-145">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="50212-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="50212-146">Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50212-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="50212-147">Utilisation du Centre d'administration Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="50212-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-148">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="50212-149">Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de conférence audio changent**.</span><span class="sxs-lookup"><span data-stu-id="50212-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="50212-150">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="50212-150">Click **Save**.</span></span>
    
    <span data-ttu-id="50212-p108">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="50212-p108">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="50212-153">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="50212-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="50212-154">Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.</span><span class="sxs-lookup"><span data-stu-id="50212-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="50212-155">Utilisation de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50212-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="50212-156">Vous pouvez également utiliser Windows PowerShell et exécuter :</span><span class="sxs-lookup"><span data-stu-id="50212-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="50212-157">Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="50212-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="50212-p109">Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="50212-p109">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="50212-161">Entrez l’adresse e-mail dans le paramètre _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="50212-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="50212-162">entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="50212-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="50212-163">Définissez le paramètre _SendEmailOverride_ sur _True_.</span><span class="sxs-lookup"><span data-stu-id="50212-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="50212-164">Vous pouvez apporter des modifications à l’e-mail envoyé aux utilisateurs, telles que l’adresse e-mail que le courrier électronique est envoyé à partir d’ou le nom d’affichage de l’e-mail en exécutant :</span><span class="sxs-lookup"><span data-stu-id="50212-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="50212-165">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="50212-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="50212-166">Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.</span><span class="sxs-lookup"><span data-stu-id="50212-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="50212-167">Voir les [messages qui sont automatiquement envoyés aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="50212-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="50212-168">Réinitialiser la réunion ID de conférence</span><span class="sxs-lookup"><span data-stu-id="50212-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="50212-169">Réinitialisation de l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="50212-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-170">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-171">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, allez dans le volet Actions, sous **ID de conférence**et **les conférences Audio**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="50212-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="50212-172">Dans le **Réinitialiser l’ID de conférence ?** la fenêtre, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="50212-172">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="50212-173">Un ID de conférence sera créé automatiquement et un message électronique envoyé à l’utilisateur avec le nouvel ID de conférence si l’envoi de courrier électronique à vos utilisateurs est activé.</span><span class="sxs-lookup"><span data-stu-id="50212-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="50212-174">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="50212-174">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="50212-175">Après avoir créé un nouvel ID de conférence, l’ancien ID de conférence ne peut pas être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="50212-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="50212-176">Vous devez avertir les utilisateurs de replanifier les invitations pour vous assurer que la nouvelle conférence QU'ID est ajouté pour les invitations aux réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="50212-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="50212-177">Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business mise à jour de leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="50212-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="50212-178">Pour savoir comment télécharger, installer et exécuter le Skype pour l’outil de mise à jour de réunion Professionnel, consultez : [outil de mise à jour de réunion pour Skype pour les entreprises et Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, L’outil de Migration (64 bits) de réunion](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour l’activité en ligne, l’outil de Migration de réunion (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="50212-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="50212-179">Consultez [Réinitialiser un ID de conférence pour un utilisateur](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="50212-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="50212-180">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="50212-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="50212-181">ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utiliser un qui soit facile à mémoriser.</span><span class="sxs-lookup"><span data-stu-id="50212-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="50212-182">Lorsque l’ID de conférence dynamiques sont utilisés, chaque réunion une planification de l’utilisateur sera obtenir une conférence unique ID attribué</span><span class="sxs-lookup"><span data-stu-id="50212-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="50212-183">Si vous souhaitez affecter les dynamique au lieu de la conférence static ID, [ID de dynamique à l’aide de l’audioconférence de votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="50212-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="50212-184">Bien qu’un ID de conférence statique sera automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous souhaitez la définir pour un certain nombre, ou vos utilisateurs ne vous souvenez plus ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="50212-184">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="50212-185">Vous pouvez utiliser le Skype pour Business admin center et de Windows PowerShell pour afficher, de modifier et de réinitialiser leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="50212-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="50212-186">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="50212-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-187">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="50212-188">Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code PIN pour.</span><span class="sxs-lookup"><span data-stu-id="50212-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="50212-189">Dans le volet Actions, sous le **code confidentiel**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="50212-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="50212-190">Les utilisateurs recevront un message électronique avec leur code PIN lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="50212-190">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="50212-191">Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un e-mail de réinitialisation du code PIN ne seront pas envoyé et vous devrez envoyer manuellement le code PIN de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50212-191">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="50212-192">Le code confidentiel n’apparaît qu’une seule fois après que qu’il a été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="50212-192">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="50212-193">Une fois qu’il est affiché juste après la réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur ; au lieu de cela, \*\*\* s’affichera.</span><span class="sxs-lookup"><span data-stu-id="50212-193">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="50212-194">Les utilisateurs recevront un courrier électronique avec leur code confidentiel lorsqu'ils seront activés pour la conférence rendez-vous ou lorsque le code confidentiel sera réinitialisé. Si vous avez désactivé l'envoi automatique de courriers électroniques, aucun message de réinitialisation du code confidentiel ne sera envoyé à l'utilisateur, ce qui vous obligera à réinitialiser manuellement le code confidentiel. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Lorsqu'il s'affiche après la réinitialisation, le code confidentiel n'apparaît dans les propriétés de l'utilisateur que sous la forme \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="50212-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="50212-195">Envoyer un courriel avec les informations d’audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="50212-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="50212-196">Envoi d'un courrier électronique à un utilisateur avec ses informations de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="50212-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-197">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="50212-198">Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code PIN pour.</span><span class="sxs-lookup"><span data-stu-id="50212-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="50212-199">Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="50212-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50212-200">Lorsque vous effectuez cette opération, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50212-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="50212-201">Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50212-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="50212-202">Définir le numéro de téléphone de conférence audio par défaut pour les organisateurs de la réunion</span><span class="sxs-lookup"><span data-stu-id="50212-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="50212-203">Définition du numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion</span><span class="sxs-lookup"><span data-stu-id="50212-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="50212-204">Pour définir le numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion lorsque vous activez un utilisateur pour la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="50212-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-205">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-p115">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="50212-p115">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="50212-208">Dans le volet Actions, dans les propriétés de l’utilisateur, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="50212-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="50212-209">Sur la page de **Propriétés** , sous **le nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="50212-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="50212-210">Si vous sélectionnez Microsoft comme le fournisseur de conférence audio, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="50212-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="50212-p116">Si vous sélectionnez Microsoft en tant que fournisseur de conférence rendez-vous, vous pouvez choisir le numéro de téléphone par défaut de la conférence rendez-vous dans la liste.</span><span class="sxs-lookup"><span data-stu-id="50212-p116">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number. These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="50212-213">Si vous sélectionnez un fournisseur de services d'audioconférence tiers, vous devrez entrer manuellement le numéro de téléphone payant et, si nécessaire, le numéro de téléphone gratuit. Ces numéros de téléphone constitueront le numéro de téléphone par défaut.</span><span class="sxs-lookup"><span data-stu-id="50212-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="50212-214">Le numéro de téléphone de conférence rendez-vous par défaut d'un utilisateur correspond au numéro indiqué sur l'invitation à la réunion lors de la planification d'une réunion.</span><span class="sxs-lookup"><span data-stu-id="50212-214">Click **Save**.</span></span> 
    
<span data-ttu-id="50212-215">Voir [invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="50212-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="50212-216">Reportez-vous à la rubrique **Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion**.</span><span class="sxs-lookup"><span data-stu-id="50212-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="50212-217">Pour définir le numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion après avoir activé un utilisateur pour la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="50212-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-218">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-219">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**, sélectionnez l’utilisateur que vous souhaitez et dans la page Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="50212-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="50212-220">Sur la page de **Propriétés** , sous **le nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="50212-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="50212-221">Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="50212-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="50212-222">Si l'utilisateur utilise Microsoft en tant que fournisseur de conférence rendez-vous, vous pouvez choisir le numéro de téléphone par défaut de la conférence rendez-vous dans la liste.</span><span class="sxs-lookup"><span data-stu-id="50212-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="50212-223">Si l'utilisateur utilise un fournisseur de services d'audioconférence tiers, vous devrez entrer manuellement le numéro de téléphone payant et, si nécessaire, le numéro de téléphone gratuit.</span><span class="sxs-lookup"><span data-stu-id="50212-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="50212-224">Le numéro de téléphone de conférence rendez-vous par défaut d'un utilisateur correspond au numéro indiqué sur l'invitation à la réunion lors de la planification d'une réunion.</span><span class="sxs-lookup"><span data-stu-id="50212-224">Click **Save**.</span></span> 
    
<span data-ttu-id="50212-225">Voir [invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="50212-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="50212-226">Définition des paramètres de pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="50212-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="50212-227">Configuration des paramètres du pont de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="50212-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="50212-228">Définir les modalités d'accès aux réunions</span><span class="sxs-lookup"><span data-stu-id="50212-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-229">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-230">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="50212-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="50212-231">**Expérience de jointure de la réunion**, cliquez sur les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="50212-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="50212-p117">Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="50212-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="50212-234">Cela peut être définie sur une base de réunion par réunion lorsqu’un utilisateur joint à une réunion en utilisant un Skype pour application métier ou Teams de Microsoft et de les modifient le paramètre **annonce lorsque des personnes intègrent ou quittent** dans le menu réunion de Skype ou Teams de Microsoft, **Options** de la de la réunion.</span><span class="sxs-lookup"><span data-stu-id="50212-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="50212-p118">Ce paramètre peut être défini réunion par réunion lorsqu'un utilisateur participe à une réunion par le biais d'un client Skype Entreprise et qu'il modifie le paramètre **Annoncer l'arrivée ou le départ des personnes** dans le menu Options de la réunion Skype.</span><span class="sxs-lookup"><span data-stu-id="50212-p118">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="50212-237">**Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="50212-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="50212-238">Une fois que vous avez effectué vos modifications, cliquez sur [Enregistrer](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="50212-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="50212-239">Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="50212-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="50212-240">Définition de la longueur du code confidentiel pour les réunions</span><span class="sxs-lookup"><span data-stu-id="50212-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-241">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-242">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="50212-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="50212-243">Sous **sécurité**, entrez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="50212-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="50212-244">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="50212-244">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="50212-245">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="50212-245">The default is 5.</span></span>
    
<span data-ttu-id="50212-246">Le code confidentiel doit comporter de 4 à 12 chiffres. La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="50212-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="50212-247">Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="50212-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="50212-248">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="50212-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-249">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="50212-250">Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de conférence audio changent**.</span><span class="sxs-lookup"><span data-stu-id="50212-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="50212-251">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="50212-251">Click **Save**.</span></span>
    
    <span data-ttu-id="50212-252">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="50212-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="50212-253">Si vous le faites, un e-mail sera envoyé qui inclut uniquement les ID de conférence et le numéro de téléphone de conférence, mais le code confidentiel ne sera pas inclus.</span><span class="sxs-lookup"><span data-stu-id="50212-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="50212-254">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="50212-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="50212-255">Afficher et définir les langues principales et secondaires sur un pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="50212-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="50212-256">Affichage et sélection de la langue principale et des langues secondaires associées à un point de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="50212-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-257">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-258">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **l’audioconférence**, puis cliquez sur **pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="50212-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="50212-259">Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="50212-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="50212-260">Vous pouvez également définir les langues principales et secondaires qui sont pris en charge lorsque vous sélectionnez Microsoft comme le fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="50212-260">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="50212-261">La commande que vous sélectionnez dans les listes correspond à l’ordre dans lequel les langues seront présentées aux appelants.</span><span class="sxs-lookup"><span data-stu-id="50212-261">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="50212-262">Vous pouvez également définir la langue principale et les langues secondaires prises en charge lorsque vous sélectionnez Microsoft comme fournisseur de conférences rendez-vous. L'ordre que vous sélectionnez dans les listes déroulantes correspondra à l'ordre dans lequel les langues sont proposées aux appelants.</span><span class="sxs-lookup"><span data-stu-id="50212-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="50212-263">Consultez les numéros d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="50212-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="50212-264">Affichage des numéros d'accès pour les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="50212-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-265">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="50212-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-266">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="50212-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="50212-267">Ici, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="50212-267">Here you can:</span></span>
    
  - <span data-ttu-id="50212-268">Permet d’afficher les numéros de téléphone sont définis par Office 365 à utiliser pour les conférences Audio.</span><span class="sxs-lookup"><span data-stu-id="50212-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="50212-269">Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="50212-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="50212-p122">Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="50212-p122">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="50212-272">Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.</span><span class="sxs-lookup"><span data-stu-id="50212-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="50212-273">Reportez-vous à la section [Afficher la liste des numéros d’audioconférence](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="50212-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="50212-274">Afficher la liste des utilisateurs qui sont activés</span><span class="sxs-lookup"><span data-stu-id="50212-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="50212-275">Affichage de la liste des utilisateurs activés</span><span class="sxs-lookup"><span data-stu-id="50212-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50212-276">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="50212-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50212-277">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence**> et ensuite **aux utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="50212-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="50212-278">Consultez [une liste d’utilisateurs qui sont activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="50212-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="50212-279">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="50212-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="50212-280">Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50212-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="50212-281">Cela rend facile à appliquer les paramètres à tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50212-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="50212-282">Plusieurs paramètres peuvent être gérés au niveau de l'organisation à l'aide de Windows PowerShell. Cela facilite la configuration de ces paramètres et leur mise en œuvre pour tous vos utilisateurs. Voici les paramètres de niveau organisation :</span><span class="sxs-lookup"><span data-stu-id="50212-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="50212-283">Voici les paramètres au niveau de l’organisation :</span><span class="sxs-lookup"><span data-stu-id="50212-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="50212-284">**Configuration de notifications d’entrée et de sortie** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="50212-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="50212-285">**Définition d’enregistrement de nom** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="50212-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="50212-286">**Définition de la longueur du code confidentiel** La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="50212-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="50212-287">**Configuration à distance réunions uniquement à partir d’un téléphone** La valeur par défaut _$false_.</span><span class="sxs-lookup"><span data-stu-id="50212-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="50212-288">**Définir s’il faut envoyer un e-mail aux utilisateurs** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="50212-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="50212-289">**Définir s’il faut envoyer un e-mail à partir d’un autre compte** La valeur par défaut est _$false_.</span><span class="sxs-lookup"><span data-stu-id="50212-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="50212-290">**Définition de l’adresse de courrier électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="50212-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="50212-291">**Définition du nom d’affichage de l’e-mail qui sera envoyé aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="50212-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="50212-292">Pour en savoir plus sur Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50212-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="50212-293">Windows PowerShell est la gestion des utilisateurs et les utilisateurs qui sont autorisés ou non à faire.</span><span class="sxs-lookup"><span data-stu-id="50212-293">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="50212-294">Avec Windows PowerShell, vous pouvez gérer Office 365 à l’aide d’un unique point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="50212-294">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="50212-295">Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="50212-295">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="50212-296">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="50212-296">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="50212-297">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="50212-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="50212-298">Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité sur uniquement en utilisant le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="50212-298">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="50212-299">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="50212-299">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="50212-300">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="50212-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="50212-301">Utiliser Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="50212-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="50212-302">Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="50212-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="50212-p126">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="50212-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="50212-305">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="50212-305">Related topics</span></span>

[<span data-ttu-id="50212-306">Gérer les paramètres de l’audioconférence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="50212-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="50212-307">Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50212-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

