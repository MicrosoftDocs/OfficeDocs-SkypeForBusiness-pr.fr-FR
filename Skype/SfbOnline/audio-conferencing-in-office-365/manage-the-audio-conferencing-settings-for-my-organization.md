---
title: Gestion des paramètres de conférence rendez-vous de mon organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b2759e4ee1f8e8cac2f753eb5afecbf13642abb0
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="69e60-103">Gestion des paramètres de conférence rendez-vous de mon organisation</span><span class="sxs-lookup"><span data-stu-id="69e60-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="69e60-104">[] Il peut être préférable d'afficher tous les paramètres de conférence rendez-vous à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="69e60-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="69e60-105">Affecter une licence de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="69e60-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="69e60-106">Vous ne pouvez attribuer des licences à l’aide de la **Skype entreprise centre d’administration**.</span><span class="sxs-lookup"><span data-stu-id="69e60-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="69e60-107">Vous devez utiliser le centre d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="69e60-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="69e60-108">Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="69e60-109">Pour affecter une licence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="69e60-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="69e60-110">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-111">Dans la navigation de gauche du **Centre d’administration Office 365**, accédez aux **utilisateurs** > **utilisateurs actifs**, puis sélectionnez les utilisateurs dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="69e60-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="69e60-p102">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**. Vous pouvez également affecter des licences à plusieurs utilisateurs à l'aide de Windows Powershell. Pour obtenir des informations et des exemples de scripts Powershell, reportez-vous à la rubrique [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="69e60-116">Dans le volet Action sous **Licence affectée**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="69e60-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="69e60-p103">Sur la page **Affecter une licence**, cochez **Conférence RTC Skype Entreprise**, puis cliquez sur **Enregistrer**. Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="69e60-p104">Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="69e60-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="69e60-121">Affectation d'un ID de conférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="69e60-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="69e60-122">Un ID de conférence est automatiquement attribué à un utilisateur lorsqu’ils sont configurés pour la conférence audio à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="69e60-123">L’ID de conférence est envoyé dans l’invitation à la réunion lorsque la réunion est planifiée.</span><span class="sxs-lookup"><span data-stu-id="69e60-123">The conference ID is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="69e60-124">Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="69e60-124">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>
  
<span data-ttu-id="69e60-125">Contrairement à l'applet de commande Windows PowerShell, le Centre d'administration Skype Entreprise ne permet pas d'affecter un ID de conférence à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69e60-125">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="69e60-126">Contrairement à l'applet de commande Windows PowerShell, le Centre d'administration Skype Entreprise ne permet pas d'affecter un ID de conférence à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69e60-126">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="69e60-127">Pour définir l'ID de conférence d'un utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="69e60-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="69e60-128">Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="69e60-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="69e60-129">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="69e60-129">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="69e60-130">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="69e60-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="69e60-131">Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="69e60-131">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="69e60-132">Pour savoir comment télécharger, installer et exécuter la Skype pour l’outil de mise à jour de réunion Business, voir : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online réunion Outil de migration (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="69e60-132">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="69e60-133">Reportez-vous à la rubrique [Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-133">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
    
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="69e60-134">Activer ou désactiver les courriers électroniques envoyés à des utilisateurs de conférence audio</span><span class="sxs-lookup"><span data-stu-id="69e60-134">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="69e60-135">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-135">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-136">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="69e60-136">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="69e60-137">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="69e60-137">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="69e60-138">Dans le volet **paramètres du pont** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres de connexion à modifient**.</span><span class="sxs-lookup"><span data-stu-id="69e60-138">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="69e60-139">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-139">Click **Save**.</span></span>

<span data-ttu-id="69e60-140">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="69e60-141">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="69e60-141">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-142">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-142">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="69e60-143">Dans la page **paramètres du pont Microsoft** , activez ou désactivez l' **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="69e60-143">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="69e60-144">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-144">Click **Save**.</span></span>
    
    <span data-ttu-id="69e60-p107">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-p107">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="69e60-147">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-147">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="69e60-148">Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.</span><span class="sxs-lookup"><span data-stu-id="69e60-148">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="69e60-149">Utilisation de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69e60-149">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="69e60-150">Vous pouvez également utiliser Windows PowerShell et exécuter :</span><span class="sxs-lookup"><span data-stu-id="69e60-150">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="69e60-151">Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="69e60-151">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="69e60-p108">Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="69e60-p108">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="69e60-155">Entrez l’adresse de messagerie dans le paramètre _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="69e60-155">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="69e60-156">entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="69e60-156">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="69e60-157">Définissez le paramètre _SendEmailOverride_ sur _True_.</span><span class="sxs-lookup"><span data-stu-id="69e60-157">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="69e60-158">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="69e60-158">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="69e60-159">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="69e60-159">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="69e60-160">Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.</span><span class="sxs-lookup"><span data-stu-id="69e60-160">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="69e60-161">Voir [les messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-161">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="69e60-162">Réinitialisation de l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="69e60-162">Reset the meeting conference ID</span></span>

<span data-ttu-id="69e60-163">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-163">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-164">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="69e60-164">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="69e60-165">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="69e60-165">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="69e60-166">Sous **Conférence Audio**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="69e60-166">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="69e60-167">Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="69e60-167">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="69e60-168">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="69e60-168">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="69e60-169">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="69e60-169">It's enabled by default.</span></span>

<span data-ttu-id="69e60-170">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-170">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="69e60-171">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-171">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-172">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-172">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-173">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="69e60-173">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="69e60-174">Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="69e60-174">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="69e60-175">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="69e60-175">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="69e60-176">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="69e60-176">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="69e60-177">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="69e60-177">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="69e60-178">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="69e60-178">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="69e60-179">Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="69e60-179">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="69e60-180">Pour savoir comment télécharger, installer et exécuter la Skype pour l’outil de mise à jour de réunion Business, voir : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online réunion Outil de migration (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="69e60-180">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="69e60-181">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-181">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="69e60-182">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="69e60-182">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="69e60-183">Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="69e60-183">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="69e60-184">Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou vos utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-184">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="69e60-185">Vous pouvez utiliser la Skype entreprise centre d’administration et de Windows PowerShell pour afficher, modifier et de réinitialiser leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="69e60-186">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-186">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-187">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="69e60-187">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="69e60-188">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="69e60-188">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="69e60-189">Sous **Conférence Audio**, cliquez sur **Réinitialiser le code confidentiel**, puis cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="69e60-189">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="69e60-190">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-190">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="69e60-191">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="69e60-191">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-192">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-192">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="69e60-193">Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.</span><span class="sxs-lookup"><span data-stu-id="69e60-193">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="69e60-194">Dans le volet Actions, sous **code confidentiel**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="69e60-194">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="69e60-195">Les utilisateurs recevront un message électronique avec leur code confidentiel lorsqu’ils sont activés pour les services d’audioconférence ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="69e60-195">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="69e60-196">Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un message électronique de réinitialisation du code confidentiel ne seront pas envoyé et vous devez envoyer manuellement le code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69e60-196">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="69e60-197">Le code confidentiel ne sera affiché qu'après avoir été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="69e60-197">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="69e60-198">Une fois qu’il est affiché juste après la réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur ; au lieu de cela, \*\*\* s’affichera.</span><span class="sxs-lookup"><span data-stu-id="69e60-198">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="69e60-199">Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-199">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="69e60-200">Envoyer un message électronique avec des informations de conférence Audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="69e60-200">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="69e60-201">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-202">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="69e60-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="69e60-203">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="69e60-203">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="69e60-204">**Conférence Audio**, cliquez sur **Envoyer les informations de conférence dans le message électronique**.</span><span class="sxs-lookup"><span data-stu-id="69e60-204">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="69e60-205">Lorsque vous faites cela, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69e60-205">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="69e60-206">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="69e60-207">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="69e60-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-208">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="69e60-209">Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.</span><span class="sxs-lookup"><span data-stu-id="69e60-209">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="69e60-210">Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="69e60-210">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="69e60-211">Lorsque vous faites cela, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69e60-211">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="69e60-212">Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69e60-212">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="69e60-213">Définir le numéro de téléphone de conférence audio par défaut pour les organisateurs de réunions</span><span class="sxs-lookup"><span data-stu-id="69e60-213">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="69e60-214">Définition du numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion</span><span class="sxs-lookup"><span data-stu-id="69e60-214">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="69e60-215">Pour définir le numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion lorsque vous activez un utilisateur pour la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="69e60-215">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-216">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-p114">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="69e60-p114">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="69e60-219">Dans le volet Actions, dans Propriétés de l’utilisateur, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="69e60-219">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="69e60-220">Dans la page **Propriétés** , sous le **nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="69e60-221">Si vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="69e60-221">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="69e60-p115">Si vous sélectionnez Microsoft en tant que fournisseur de conférence rendez-vous, vous pouvez choisir le numéro de téléphone par défaut de la conférence rendez-vous dans la liste.</span><span class="sxs-lookup"><span data-stu-id="69e60-p115">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number. These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="69e60-224">Si vous sélectionnez un fournisseur de services d'audioconférence tiers, vous devrez entrer manuellement le numéro de téléphone payant et, si nécessaire, le numéro de téléphone gratuit. Ces numéros de téléphone constitueront le numéro de téléphone par défaut.</span><span class="sxs-lookup"><span data-stu-id="69e60-224">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="69e60-225">Le numéro de téléphone de conférence rendez-vous par défaut d'un utilisateur correspond au numéro indiqué sur l'invitation à la réunion lors de la planification d'une réunion.</span><span class="sxs-lookup"><span data-stu-id="69e60-225">Click **Save**.</span></span> 
    
<span data-ttu-id="69e60-226">Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-226">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="69e60-227">Reportez-vous à la rubrique **Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion**.</span><span class="sxs-lookup"><span data-stu-id="69e60-227">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="69e60-228">Pour définir le numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion après avoir activé un utilisateur pour la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="69e60-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-229">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-230">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **les utilisateurs**, sélectionnez l’utilisateur que vous voulez, dans la page Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="69e60-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="69e60-231">Dans la page **Propriétés** , sous le **nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-231">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="69e60-232">Si l’utilisateur utilise Microsoft en tant que le fournisseur de services d’audioconférence, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="69e60-232">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="69e60-233">Si l'utilisateur utilise Microsoft en tant que fournisseur de conférence rendez-vous, vous pouvez choisir le numéro de téléphone par défaut de la conférence rendez-vous dans la liste.</span><span class="sxs-lookup"><span data-stu-id="69e60-233">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="69e60-234">Si l'utilisateur utilise un fournisseur de services d'audioconférence tiers, vous devrez entrer manuellement le numéro de téléphone payant et, si nécessaire, le numéro de téléphone gratuit.</span><span class="sxs-lookup"><span data-stu-id="69e60-234">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="69e60-235">Le numéro de téléphone de conférence rendez-vous par défaut d'un utilisateur correspond au numéro indiqué sur l'invitation à la réunion lors de la planification d'une réunion.</span><span class="sxs-lookup"><span data-stu-id="69e60-235">Click **Save**.</span></span> 
    
<span data-ttu-id="69e60-236">Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-236">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="69e60-237">Choix des paramètres de pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="69e60-237">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="69e60-238">Configuration des paramètres du pont de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="69e60-238">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="69e60-239">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-239">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-240">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="69e60-240">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="69e60-241">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="69e60-241">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="69e60-242">Dans le volet **paramètres du pont** , activer ou désactiver **l’entrée de la réunion et quitter des notifications**.</span><span class="sxs-lookup"><span data-stu-id="69e60-242">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="69e60-243">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="69e60-243">This is enabled by default.</span></span> <span data-ttu-id="69e60-244">Si vous désactivez cette option, les utilisateurs qui ont déjà joint la réunion par défaut ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="69e60-244">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="69e60-245">Sous **type d’entrée/sortie annonce**, choisissez **tonalités** ou **les noms ou les numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="69e60-245">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="69e60-246">Si vous choisissez des **noms ou des numéros de téléphone**, vous pouvez également choisir activer ou désactiver **les appelants Ask à enregistrer leur nom avant de participer à la réunion**.</span><span class="sxs-lookup"><span data-stu-id="69e60-246">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="69e60-247">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-247">Click **Save**.</span></span>

<span data-ttu-id="69e60-248">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-248">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="69e60-249">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-249">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-250">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-250">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-251">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69e60-251">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="69e60-252">Sous **l’expérience de participation aux réunions**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="69e60-252">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="69e60-p117">Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="69e60-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="69e60-255">Peut être défini sur une base de réunion par réunion lorsqu’un utilisateur joint à une réunion en utilisant un Skype pour l’application Microsoft Teams ou de l’entreprise et ils modifient le paramètre **annoncer lorsque les utilisateurs entrent ou quittent** dans le menu réunion Skype ou Microsoft Teams **Options** de la la réunion.</span><span class="sxs-lookup"><span data-stu-id="69e60-255">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="69e60-p118">Ce paramètre peut être défini réunion par réunion lorsqu'un utilisateur participe à une réunion par le biais d'un client Skype Entreprise et qu'il modifie le paramètre **Annoncer l'arrivée ou le départ des personnes** dans le menu Options de la réunion Skype.</span><span class="sxs-lookup"><span data-stu-id="69e60-p118">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="69e60-258">**Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="69e60-258">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="69e60-259">Une fois que vous avez effectué vos modifications, cliquez sur [Enregistrer](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-259">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="69e60-260">Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69e60-260">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="69e60-261">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-261">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-262">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="69e60-262">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="69e60-263">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="69e60-263">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="69e60-264">Dans le volet **paramètres du pont** , entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-264">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="69e60-265">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="69e60-265">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="69e60-266">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="69e60-266">The default is 5.</span></span>

<span data-ttu-id="69e60-267">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-267">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="69e60-268">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-268">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-269">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-269">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-270">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69e60-270">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="69e60-271">Sous **sécurité**, entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-271">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="69e60-272">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="69e60-272">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="69e60-273">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="69e60-273">The default is 5.</span></span>
    
<span data-ttu-id="69e60-274">Le code confidentiel doit comporter de 4 à 12 chiffres. La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="69e60-274">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="69e60-275">Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69e60-275">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="69e60-276">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-276">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-277">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="69e60-277">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="69e60-278">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="69e60-278">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="69e60-279">Dans le volet **paramètres du pont** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="69e60-279">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="69e60-280">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-280">Click **Save**.</span></span> 
 
    <span data-ttu-id="69e60-281">Vous pouvez également envoyer courrier électronique à l’utilisateur avec les paramètres de conférence audio, en accédant aux propriétés de conférence audio de l’utilisateur et en cliquant sur **Envoyer les informations de conférence dans le message électronique**.</span><span class="sxs-lookup"><span data-stu-id="69e60-281">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="69e60-282">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-282">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="69e60-283">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-283">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="69e60-284">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="69e60-284">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-285">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-285">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="69e60-286">Dans la page **paramètres du pont Microsoft** , activez ou désactivez l' **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="69e60-286">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="69e60-287">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-287">Click **Save**.</span></span>
    
    <span data-ttu-id="69e60-288">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="69e60-288">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="69e60-289">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-289">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="69e60-290">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-290">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="69e60-291">Afficher et définir principal (par défaut) et secondaires (autres) langues sur un pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="69e60-291">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="69e60-292">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-292">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="69e60-293">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="69e60-293">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="69e60-294">Sélectionnez un numéro de téléphone dans la liste, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="69e60-294">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="69e60-295">Choisir les langues sous **langue par défaut** et **d’autres langues (facultatifs)**.</span><span class="sxs-lookup"><span data-stu-id="69e60-295">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="69e60-296">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="69e60-296">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="69e60-297">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-297">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-298">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-298">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-299">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, puis cliquez sur **Microsoft bridge**.</span><span class="sxs-lookup"><span data-stu-id="69e60-299">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="69e60-300">Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69e60-300">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="69e60-301">Vous pouvez également définir les langues principales et secondaires qui sont prises en charge lorsque vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-301">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="69e60-302">L’ordre que vous sélectionnez dans les listes correspond à l’ordre dans lequel les langues seront présentées aux appelants.</span><span class="sxs-lookup"><span data-stu-id="69e60-302">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="69e60-303">Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-303">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![SFB-logo-30x30.png](../images/sfb-logo-30x30.png)  <span data-ttu-id="69e60-305">Voir les numéros de services d’audioconférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="69e60-305">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="69e60-306">Affichage des numéros d'accès pour les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="69e60-306">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-307">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="69e60-307">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-308">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **Microsoft bridge**.</span><span class="sxs-lookup"><span data-stu-id="69e60-308">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="69e60-309">Ici, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="69e60-309">Here you can:</span></span>
    
  - <span data-ttu-id="69e60-310">Afficher les numéros de téléphone qui sont définis par Office 365 à utiliser pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="69e60-310">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="69e60-311">Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="69e60-311">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="69e60-p123">Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="69e60-p123">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="69e60-314">Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.</span><span class="sxs-lookup"><span data-stu-id="69e60-314">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="69e60-315">Consultez la rubrique [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-315">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="69e60-317">Affichage de la liste des utilisateurs activés</span><span class="sxs-lookup"><span data-stu-id="69e60-317">See a list of users that are enabled</span></span>

1. <span data-ttu-id="69e60-318">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-318">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69e60-319">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="69e60-319">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69e60-320">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**> puis **utilisateurs**et.</span><span class="sxs-lookup"><span data-stu-id="69e60-320">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="69e60-321">Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="69e60-321">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="69e60-322">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="69e60-322">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="69e60-323">Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69e60-323">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="69e60-324">Cela facilite appliquer les paramètres à tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="69e60-324">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="69e60-325">Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="69e60-325">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="69e60-326">Voici les paramètres au niveau de l’organisation :</span><span class="sxs-lookup"><span data-stu-id="69e60-326">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="69e60-327">**Configuration de notifications d’entrée/sortie** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="69e60-327">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="69e60-328">**Définition d’enregistrement de nom** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="69e60-328">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="69e60-329">**Définition de la longueur du code confidentiel** La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="69e60-329">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="69e60-330">**Définition de rendez-vous réunions uniquement à partir d’un téléphone** La valeur par défaut _$false_.</span><span class="sxs-lookup"><span data-stu-id="69e60-330">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="69e60-331">**Définition s’il faut envoyer un message électronique aux utilisateurs** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="69e60-331">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="69e60-332">**Définition s’il faut envoyer un message électronique à partir d’un autre compte** La valeur par défaut est _$false_.</span><span class="sxs-lookup"><span data-stu-id="69e60-332">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="69e60-333">**Définition de l’adresse de messagerie qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="69e60-333">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="69e60-334">**Définition du nom complet pour le message électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="69e60-334">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="69e60-335">Pour en savoir plus sur Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69e60-335">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="69e60-p125">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="69e60-p125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="69e60-339">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="69e60-339">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="69e60-340">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="69e60-340">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="69e60-341">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="69e60-341">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="69e60-342">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="69e60-342">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="69e60-343">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="69e60-343">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="69e60-344">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="69e60-344">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="69e60-345">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="69e60-345">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="69e60-p127">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="69e60-p127">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="69e60-348">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="69e60-348">Related topics</span></span>

[<span data-ttu-id="69e60-349">Gérer les paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="69e60-349">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


