---
title: Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Voir Skype pour obtenir la procédure Business Online pour affecter un ID de conférence et de licence de conférence rendez-vous à un utilisateur et de nombreux autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: ed5d2cb2115c47ba84dd91ebc45561aa93e4c023
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229358"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="53d08-103">Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="53d08-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="53d08-104">Si vous souhaitez gérer ces paramètres dans Teams, voir [Gérer les paramètres d'Audioconférence de mon organisation dans Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="53d08-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="53d08-105">Il peut être plus facile à voir tous les paramètres de conférence audio pour Skype pour les entreprises à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="53d08-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="53d08-106">Attribuer une licence d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="53d08-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="53d08-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="53d08-110">**Pour attribuer une licence pour un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="53d08-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="53d08-111">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-112">Dans la navigation de gauche du **Centre d’administration Office 365**, accédez aux **utilisateurs** > **utilisateurs actifs**, puis sélectionnez les utilisateurs dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="53d08-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53d08-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="53d08-117">Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="53d08-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="53d08-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53d08-p104">Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="53d08-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="53d08-122">Activer ou désactiver les courriers électroniques envoyés à des utilisateurs de conférence audio</span><span class="sxs-lookup"><span data-stu-id="53d08-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="53d08-123">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="53d08-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="53d08-124">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-125">Allez dans le **Centre d'administration Office 365** > **Skype Entreprise** et dans le volet de navigation de gauche, cliquez sur **Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="53d08-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="53d08-126">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="53d08-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="53d08-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d08-127">Click **Save**.</span></span>

    <span data-ttu-id="53d08-p105">Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres d'audioconférence en accédant aux propriétés d'audioconférence de l’utilisateur et en cliquant sur **Envoyer les informations de conférence par courrier électronique**. L'ID de conférence et le numéro de téléphone d'audioconférence par défaut seront inclus dans l’invitation à la réunion, mais pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="53d08-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="53d08-130">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="53d08-131">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="53d08-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="53d08-132">Utilisation de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53d08-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="53d08-133">Vous pouvez également utiliser Windows PowerShell et exécuter :[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="53d08-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="53d08-134">Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="53d08-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="53d08-p106">Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="53d08-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="53d08-138">Entrez l’adresse de messagerie dans le paramètre _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="53d08-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="53d08-139">entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="53d08-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="53d08-140">Définissez le paramètre _SendEmailOverride_ à _True_.</span><span class="sxs-lookup"><span data-stu-id="53d08-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="53d08-141">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="53d08-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="53d08-142">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="53d08-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="53d08-143">Vous pouvez utiliser l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer les autres paramètres pour votre organisation, y compris le courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="53d08-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="53d08-144">Voir [les messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="53d08-145">Réinitialisation de l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="53d08-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="53d08-146">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-147">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\* \*\* > \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="53d08-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="53d08-148">Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence**, et dans le volet Actions, sous d'**ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="53d08-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="53d08-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="53d08-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="53d08-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="53d08-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="53d08-156">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="53d08-157">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="53d08-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="53d08-p109">Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="53d08-p109">Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="53d08-161">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-162">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53d08-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="53d08-163">Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.</span><span class="sxs-lookup"><span data-stu-id="53d08-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="53d08-164">Dans le volet Actions, sous **code confidentiel**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="53d08-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="53d08-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span><span class="sxs-lookup"><span data-stu-id="53d08-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="53d08-169">Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="53d08-170">Envoyer un message électronique avec des informations de conférence Audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="53d08-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="53d08-171">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-172">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53d08-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="53d08-173">Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.</span><span class="sxs-lookup"><span data-stu-id="53d08-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="53d08-174">Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="53d08-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53d08-175">Lorsque vous faites cela, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53d08-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="53d08-176">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="53d08-177">Configuration du téléphone numéros inclus sur invite</span><span class="sxs-lookup"><span data-stu-id="53d08-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="53d08-178">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-179">Connectez-vous à Office \*\* 365 à l'aide de votre compte professionnel ou scolaire. \*\* > \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="53d08-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="53d08-180">In the left navigation, go to **Audio conferencing** > **Users**.</span><span class="sxs-lookup"><span data-stu-id="53d08-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="53d08-181">Select the user that you want to enable for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="53d08-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="53d08-182">Dans le volet Action, vous pouvez définir le **Numéro payant** et, si permis, le **Numéro gratuit**.</span><span class="sxs-lookup"><span data-stu-id="53d08-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="53d08-183">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d08-183">Click **Save**.</span></span>

<span data-ttu-id="53d08-184">Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="53d08-185">Choix des paramètres de pont d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="53d08-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="53d08-186">**Définir l’expérience lorsque les appelants participer à une réunion**</span><span class="sxs-lookup"><span data-stu-id="53d08-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="53d08-187">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-188">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\* \*\* > \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="53d08-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="53d08-189">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="53d08-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="53d08-190">Sous **l’expérience de participation aux réunions**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="53d08-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="53d08-p112">Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="53d08-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="53d08-193">Cela peut être définie sur une base de réunion par réunion lorsqu’un utilisateur joint à une réunion en utilisant un Skype pour l’application de gestion et ils modifient le paramètre **annoncer lorsque les utilisateurs entrent ou quittent** dans le menu **Options** de la réunion de Skype de la réunion.</span><span class="sxs-lookup"><span data-stu-id="53d08-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="53d08-p113">**Demander aux appelants d'enregistrer leur nom avant de se joindre à la réunion**. C'est le choix par défaut. Si vous effacer cette case à cocher, les appelants ne se verront pas demander d'enregistrer leur nom avant de se joindre à une réunion.</span><span class="sxs-lookup"><span data-stu-id="53d08-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="53d08-196">Après avoir fait vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d08-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="53d08-197">Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="53d08-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="53d08-198">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="53d08-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="53d08-199">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-200">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\* \*\* > \*\*  \*\*.</span><span class="sxs-lookup"><span data-stu-id="53d08-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="53d08-201">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="53d08-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="53d08-202">Sous **sécurité**, entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d08-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="53d08-p114">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="53d08-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="53d08-205">Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="53d08-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="53d08-206">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="53d08-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="53d08-207">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-208">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53d08-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="53d08-209">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="53d08-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="53d08-210">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d08-210">Click **Save**.</span></span>

    <span data-ttu-id="53d08-211">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="53d08-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="53d08-212">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="53d08-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="53d08-213">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="53d08-214">Afficher et définir principal (par défaut) et secondaires (autres) langues sur un pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="53d08-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="53d08-215">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-216">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\* \*\* > \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="53d08-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="53d08-217">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, puis cliquez sur **Microsoft bridge**.</span><span class="sxs-lookup"><span data-stu-id="53d08-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="53d08-218">Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="53d08-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="53d08-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span><span class="sxs-lookup"><span data-stu-id="53d08-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="53d08-221">Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="53d08-222">Voir les numéros de services d’audioconférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="53d08-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="53d08-223">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-224">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="53d08-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="53d08-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span><span class="sxs-lookup"><span data-stu-id="53d08-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

   - <span data-ttu-id="53d08-227">Afficher les numéros de téléphone qui sont définis par Office 365 à utiliser pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="53d08-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="53d08-228">Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="53d08-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="53d08-p117">Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="53d08-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="53d08-231">Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53d08-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="53d08-232">Consultez la rubrique [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="53d08-233">Affichage de la liste des utilisateurs activés</span><span class="sxs-lookup"><span data-stu-id="53d08-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="53d08-234">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="53d08-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="53d08-235">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\* \*\* > \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="53d08-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="53d08-236">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à > de **conférence Audio**, puis sur **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="53d08-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="53d08-237">Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="53d08-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="53d08-238">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="53d08-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="53d08-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span><span class="sxs-lookup"><span data-stu-id="53d08-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="53d08-241">Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="53d08-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="53d08-242">Voici les paramètres au niveau de l’organisation :</span><span class="sxs-lookup"><span data-stu-id="53d08-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="53d08-243">**Configuration des notifications d’entrée/de sortie** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="53d08-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="53d08-244">**Définition de l’enregistrement des noms** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="53d08-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="53d08-245">**Définition de la longueur du code confidentiel** La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="53d08-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="53d08-246">**Définition seulement des réunions téléphoniques à partir d’un téléphone** La valeur par défaut _$false_.</span><span class="sxs-lookup"><span data-stu-id="53d08-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="53d08-247">**Définition de savoir s’il faut envoyer un message électronique aux utilisateurs** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="53d08-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="53d08-248">**Définition de savoir s’il faut envoyer un message électronique à partir d’un compte différent** La valeur par défaut est _$false_.</span><span class="sxs-lookup"><span data-stu-id="53d08-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="53d08-249">**Définition de l’adresse de messagerie De qui est envoyée aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="53d08-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="53d08-250">**Définition du nom d'affichage du message électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="53d08-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="53d08-251">Pour en savoir plus sur Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53d08-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="53d08-p119">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="53d08-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="53d08-255">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="53d08-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="53d08-256">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53d08-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="53d08-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="53d08-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="53d08-259">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="53d08-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="53d08-260">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="53d08-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="53d08-261">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="53d08-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="53d08-p121">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="53d08-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="53d08-264">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53d08-264">Related topics</span></span>

[<span data-ttu-id="53d08-265">Gestion des paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="53d08-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


