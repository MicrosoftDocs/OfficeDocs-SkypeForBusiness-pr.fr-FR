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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Voir les étapes de Skype Entreprise Online pour affecter une licence de conférence téléphonique et un ID de conférence à un utilisateur et de nombreux autres paramètres de conférence téléphonique. '
ms.openlocfilehash: 9babf0d9df978708f231e0e3dced1329ce0af437
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851466"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="01ad3-103">Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="01ad3-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="01ad3-104">Si vous souhaitez gérer ces paramètres dans Teams, voir [Gérer les paramètres d'Audioconférence de mon organisation dans Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="01ad3-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="01ad3-105">Il pourra être plus facile pour vous de voir tous les paramètres d’audioconférence de Skype Entreprise à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="01ad3-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="01ad3-106">Attribuer une licence d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="01ad3-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="01ad3-107">Vous ne pouvez pas attribuer de licences à l'aide du **centre d’administration de Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-107">You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center.</span></span> <span data-ttu-id="01ad3-108">Vous devez utiliser le centre d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="01ad3-108">You can use the Office 365 admin center though too.</span></span> <span data-ttu-id="01ad3-109">Consultez [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="01ad3-110">**Pour attribuer une licence à un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="01ad3-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="01ad3-111">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-112">Dans le volet de navigation de gauche du **Centre d'administration Office 365**, allez à **Utilisateurs** > **Utilisateurs actifs**, puis sélectionnez le ou les utilisateurs dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="01ad3-112">In the left navigation of the Office 365 admin center, go to Users  Active users > and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01ad3-113">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage.</span><span class="sxs-lookup"><span data-stu-id="01ad3-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="01ad3-114">Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="01ad3-115">Vous pouvez également attribuer des licences à plusieurs utilisateurs à l'aide de Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="01ad3-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="01ad3-116">Pour des instructions et des exemples de scripts Powershell, reportez-vous à la rubrique [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-116">For for instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="01ad3-117">Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="01ad3-118">Dans la page **Licences de produits**, activez l’**audioconférence**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see Skype for Business and Microsoft Teams add-on licensing.</span></span> <span data-ttu-id="01ad3-119">Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="01ad3-p104">Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="01ad3-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="01ad3-122">Activer ou désactiver les courriers électroniques envoyés aux utilisateurs d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="01ad3-122">Enable or disable emails from being sent to dial-in users</span></span>

<span data-ttu-id="01ad3-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d’administration de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="01ad3-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="01ad3-124">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-125">Allez dans le **Centre d'administration Office 365** > **Skype Entreprise** et dans le volet de navigation de gauche, cliquez sur **Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="01ad3-126">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="01ad3-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-127">Click **Save**.</span></span>

    <span data-ttu-id="01ad3-p105">Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres d'audioconférence en accédant aux propriétés d'audioconférence de l’utilisateur et en cliquant sur **Envoyer les informations de conférence par courrier électronique**. L'ID de conférence et le numéro de téléphone d'audioconférence par défaut seront inclus dans l’invitation à la réunion, mais pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="01ad3-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="01ad3-130">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations d'audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="01ad3-131">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="01ad3-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="01ad3-132">Vous pouvez aussi utiliser Windows PowerShell et exécuter :</span><span class="sxs-lookup"><span data-stu-id="01ad3-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="01ad3-133">Vous pouvez également utiliser Windows PowerShell et exécuter :[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="01ad3-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="01ad3-134">Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="01ad3-134">Change the senders contact information of email messages sent to users</span></span>

<span data-ttu-id="01ad3-p106">Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="01ad3-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="01ad3-138">Entrez l’adresse e-mail dans le paramètre _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-138">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="01ad3-139">Entrez le nom d'affichage de l'e-mail dans le paramètre  _SendEmailFromDisplayName_ .</span><span class="sxs-lookup"><span data-stu-id="01ad3-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="01ad3-140">Définissez le paramètre _SendEmailOverride_ à _True_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="01ad3-141">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="01ad3-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="01ad3-142">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="01ad3-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="01ad3-143">Vous pouvez utiliser le cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d'autres paramètres pour votre organisation, y compris le courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="01ad3-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="01ad3-144">Voir [Messages électroniques envoyés automatiquement aux utilisateurs lorsque leurs paramètres d’audioconférence sont modifiés](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-144">See [Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="01ad3-145">Réinitialisation de l'ID de conférence de la réunion</span><span class="sxs-lookup"><span data-stu-id="01ad3-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="01ad3-146">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-147">Allez dans le **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01ad3-148">Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence**, et dans le volet Actions, sous d'**ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="01ad3-149">Dans la fenêtre **Réinitialiser l’ID de conférence ?**, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-149">In the \*\* Reset conference ID?\*\* window, click **Yes**.</span></span> <span data-ttu-id="01ad3-150">Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé.</span><span class="sxs-lookup"><span data-stu-id="01ad3-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="01ad3-151">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="01ad3-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="01ad3-152">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="01ad3-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="01ad3-153">Vous devez inviter les utilisateurs à reprogrammer leurs invitations à la réunion, pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="01ad3-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="01ad3-154">Les utilisateurs peuvent utiliser l’Outil de migration de réunions de Skype Entreprise pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="01ad3-154">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="01ad3-155">Pour savoir comment télécharger, installer et exécuter l’Outil de migration de réunions de Skype Entreprise, voir : [Outil de migration de réunions de Skype Entreprise et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype Entreprise Online, Outil de migration de réunions (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et [Skype Entreprise Online, Outil de migration de réunions (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="01ad3-155">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

<span data-ttu-id="01ad3-156">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="01ad3-157">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="01ad3-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="01ad3-158">Chaque réunion qu’un utilisateur planifie se verra affecter un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="01ad3-158">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="01ad3-159">Bien qu'un ID de conférence soit automatiquement créé et attribué à un utilisateur, il peut arriver qu'un utilisateur ne veuille pas utiliser celui-ci et que vous souhaitiez le définir sur un certain nombre, ou que vos utilisateurs ne puissent plus se souvenir ou aient perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="01ad3-159">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="01ad3-160">Vous pouvez utiliser le centre d’administration Skype Entreprise et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="01ad3-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="01ad3-161">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-162">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="01ad3-163">Cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dont vous voulez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="01ad3-163">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="01ad3-164">Dans le volet Actions, sous **Code confidentiel**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-164">In the Action pane, click **Reset PIN**.</span></span>

<span data-ttu-id="01ad3-165">Les utilisateurs recevront un courrier électronique avec leur code confidentiel lorsqu'ils seront autorisés pour l'audioconférence ou lorsque le code confidentiel sera réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="01ad3-165">Users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="01ad3-166">Mais si vous avez désactivé l’envoi automatique de courriers électroniques, aucun message de réinitialisation du code confidentiel ne sera envoyé, et vous devrez envoyer manuellement le code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="01ad3-166">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="01ad3-167">Le code confidentiel ne sera affiché qu'après avoir été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="01ad3-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="01ad3-168">Une fois qu’il aura été affiché juste après avoir été réinitialisé, le code confidentiel ne sera plus affiché dans les propriétés de l’utilisateur ; au lieu de cela, \*\*\*\*\* sera affiché.</span><span class="sxs-lookup"><span data-stu-id="01ad3-168">Once it's displayed just after being reset, the PIN won't be shown anymore on the user properties and instead \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="01ad3-169">Voir [Réinitialiser le code confidentiel de l'Audioconférence](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-169">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="01ad3-170">Envoyer un message électronique contenant des informations d'audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="01ad3-170">Send an email to a user with their Audio Conferencing information</span></span>

1. <span data-ttu-id="01ad3-171">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-172">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="01ad3-173">Cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dont vous voulez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="01ad3-173">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="01ad3-174">Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="01ad3-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01ad3-175">Quand vous faites cela, le code confidentiel de l’audioconférence n'est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="01ad3-175">When you do this, the dial-in conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="01ad3-176">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations d'audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="01ad3-177">Définir les numéros de téléphone inclus dans les invitations</span><span class="sxs-lookup"><span data-stu-id="01ad3-177">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="01ad3-178">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-179">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01ad3-p111">Dans la navigation de gauche, allez à **Audioconférence** > **Utilisateurs**. Sélectionnez l'utilisateur que vous voulez activer pour l'audioconférence.</span><span class="sxs-lookup"><span data-stu-id="01ad3-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="01ad3-182">Dans le volet Action, vous pouvez définir le **Numéro payant** et, si permis, le **Numéro gratuit**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="01ad3-183">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-183">Click **Save**.</span></span>

<span data-ttu-id="01ad3-184">Voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-184">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md)</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="01ad3-185">Choix des paramètres de pont d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="01ad3-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="01ad3-186">**Définir l'expérience de la réunion lorsque les appelants se joignent à une réunion**</span><span class="sxs-lookup"><span data-stu-id="01ad3-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="01ad3-187">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-188">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01ad3-189">Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-189">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="01ad3-190">Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="01ad3-190">Under **Meeting join experience** select the following actions:</span></span>

  - <span data-ttu-id="01ad3-p112">Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="01ad3-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="01ad3-193">Ce paramètre peut être défini réunion par réunion, lorsqu'un utilisateur participe à une réunion en utilisant une application Skype Entreprise et qu'il modifie le paramètre **Annoncer l’arrivée ou le départ des personnes** dans le menu **Options** Réunion Skype de la réunion.</span><span class="sxs-lookup"><span data-stu-id="01ad3-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business client and they modify the **Announce when people enter or leave** setting in the Skype Meeting Options menu of the meeting.</span></span>

  - <span data-ttu-id="01ad3-p113">**Demander aux appelants d'enregistrer leur nom avant de se joindre à la réunion**. C'est le choix par défaut. Si vous effacer cette case à cocher, les appelants ne se verront pas demander d'enregistrer leur nom avant de se joindre à une réunion.</span><span class="sxs-lookup"><span data-stu-id="01ad3-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="01ad3-196">Après avoir fait vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="01ad3-197">Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="01ad3-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="01ad3-198">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="01ad3-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="01ad3-199">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-200">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01ad3-201">Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-201">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="01ad3-202">Sous **Sécurité**, entrez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste **Longueur du code confidentiel**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-202">Under **Security**PIN length > enter the number of digits you want for the PIN and then click **Save**.</span></span>

    <span data-ttu-id="01ad3-203">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="01ad3-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="01ad3-204">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="01ad3-204">The default is 5.</span></span>
    
<span data-ttu-id="01ad3-205">Voir [Modifier les paramètres d'un pont d'audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="01ad3-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="01ad3-206">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="01ad3-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="01ad3-207">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-208">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="01ad3-209">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="01ad3-210">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-210">Click **Save**.</span></span>

    <span data-ttu-id="01ad3-211">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="01ad3-212">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="01ad3-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="01ad3-213">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations d'audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="01ad3-214">Afficher et définir la langue principale (par défaut) et les langues secondaires (alternatives) pour un pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="01ad3-214">See and set the primary and secondary languages on a dial-in conferencing bridge</span></span>


1. <span data-ttu-id="01ad3-215">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-216">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01ad3-217">Dans le volet de navigation de gauche du **Centre d’administration Skype Entreprise**, sélectionnez **Audioconférence**, puis cliquez sur **Pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-217">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="01ad3-218">Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="01ad3-219">Vous pouvez également définir les langues primaires et secondaires prises en charge lorsque vous sélectionnez Microsoft comme fournisseur d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="01ad3-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="01ad3-220">L’ordre que vous sélectionnez dans les listes sera l’ordre dans lequel les langues seront présentées aux appelants.</span><span class="sxs-lookup"><span data-stu-id="01ad3-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="01ad3-221">Voir [Définir les langues automatiques d'un participant pour une audioconférence](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="01ad3-222">Voir les numéros d’appel d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="01ad3-222">See dial-in conferencing dial-in numbers</span></span>

1. <span data-ttu-id="01ad3-223">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-224">Accédez au **centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01ad3-225">Dans le **Centre d'administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-225">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="01ad3-226">Depuis cette section, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="01ad3-226">Here you can:</span></span>

  - <span data-ttu-id="01ad3-227">Affichez les numéros de téléphone qui sont définis par Office 365 pour l’utilisation en audioconférence.</span><span class="sxs-lookup"><span data-stu-id="01ad3-227">You can view the phone numbers that are set by Office 365 to be used for dial-in conferencing.</span></span>

  - <span data-ttu-id="01ad3-228">Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="01ad3-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  - <span data-ttu-id="01ad3-p117">Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="01ad3-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="01ad3-231">Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="01ad3-232">Voir [Afficher la liste des numéros d’audioconférence](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-232">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md)</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="01ad3-233">Affichage de la liste des utilisateurs activés</span><span class="sxs-lookup"><span data-stu-id="01ad3-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="01ad3-234">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="01ad3-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01ad3-235">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01ad3-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01ad3-236">Dans le **centre d’administration Skype Entreprise**, dans la navigation de gauche, allez à **Audioconférence**>, puis **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="01ad3-236">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing**> and then **Dial-in users**.</span></span>

<span data-ttu-id="01ad3-237">Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les audioconférences](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="01ad3-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="01ad3-238">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="01ad3-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="01ad3-239">Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation, à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01ad3-239">There are several settings that you can manage settings at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="01ad3-240">Cela facilite l’application de paramètres à tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="01ad3-240">This makes it easy to make these settings and have them apply to all of your users.</span></span>

<span data-ttu-id="01ad3-241">Pour en savoir plus sur chaque cmdlet, reportez-vous à la rubrique [cmdlets Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="01ad3-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="01ad3-242">Voici les paramètres de niveau organisation :</span><span class="sxs-lookup"><span data-stu-id="01ad3-242">Here are the organization level settings:</span></span>

- <span data-ttu-id="01ad3-243">**Configuration des notifications d’entrée/de sortie** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="01ad3-244">**Définition de l’enregistrement des noms** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="01ad3-245">**Définition de la longueur du code confidentiel** La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="01ad3-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="01ad3-246">**Définition seulement des réunions téléphoniques à partir d’un téléphone** La valeur par défaut _$false_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="01ad3-247">**Définition de savoir s’il faut envoyer un message électronique aux utilisateurs** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="01ad3-248">**Définition de savoir s’il faut envoyer un message électronique à partir d’un compte différent** La valeur par défaut est _$false_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="01ad3-249">**Définition de l’adresse de messagerie De qui est envoyée aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="01ad3-250">**Définition du nom d'affichage du message électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="01ad3-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="01ad3-251">Vous souhaitez en savoir plus sur Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01ad3-251">Want to know more about Windows Powershell?</span></span>
- <span data-ttu-id="01ad3-p119">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="01ad3-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="01ad3-255">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="01ad3-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="01ad3-256">Meilleures façons de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01ad3-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="01ad3-257">Windows PowerShell présente de nombreux avantages en termes de rapidité, de simplicité et de productivité par rapport à l'utilisation exclusive du centre d'administration Office 365, par exemple lorsque vous modifiez les paramètres de plusieurs utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="01ad3-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="01ad3-258">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="01ad3-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="01ad3-259">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="01ad3-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="01ad3-260">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="01ad3-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="01ad3-261">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="01ad3-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="01ad3-p121">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="01ad3-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="01ad3-264">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="01ad3-264">Related topics</span></span>

[<span data-ttu-id="01ad3-265">Gérer les paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="01ad3-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


