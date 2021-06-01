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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Consultez Skype Entreprise la procédure en ligne pour affecter une licence de conférence rendez-vous et un ID de conférence à un utilisateur et de nombreux autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: 3a0f6d37612c345c8561fbd2a64b4c90fdb27957
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237241"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="61064-103">Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="61064-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="61064-104">Si vous souhaitez gérer ces paramètres dans Teams, voir [Gérer les paramètres d'Audioconférence de mon organisation dans Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="61064-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="61064-105">Il peut être plus facile de voir tous les paramètres d’audioconférence Skype Entreprise un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="61064-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="61064-106">Affecter une licence d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="61064-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="61064-107">Vous ne pouvez pas attribuer de licences à l’aide du **Skype Entreprise d’administration.**</span><span class="sxs-lookup"><span data-stu-id="61064-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="61064-108">Vous devez utiliser le Centre Microsoft 365'administration.</span><span class="sxs-lookup"><span data-stu-id="61064-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="61064-109">Consultez [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="61064-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="61064-110">**Pour attribuer une licence à un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="61064-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="61064-111">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-112">Dans le panneau de navigation gauche du Centre d’administration, sélectionnez Utilisateurs actifs, puis sélectionnez le ou les utilisateurs dans la liste  >  des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="61064-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61064-113">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage.</span><span class="sxs-lookup"><span data-stu-id="61064-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="61064-114">Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="61064-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="61064-115">Vous pouvez également affecter des licences à plusieurs utilisateurs à l'aide de Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="61064-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="61064-116">Pour obtenir des instructions et des exemples de scripts PowerShell, voir [Attribuer Skype Entreprise licences.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="61064-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="61064-117">Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="61064-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="61064-118">Sur la page **Licences de produits,** activer **l’audioconférence,** puis cliquer sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="61064-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="61064-119">Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="61064-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="61064-120">Une fois que vous avez attribué la licence, Microsoft peut ne pas apparaître initialement dans la liste en tant que fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="61064-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="61064-121">Dans ce cas, déconnectez-vous du Centre d’administration ou appuyez sur Ctrl+F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="61064-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="61064-122">Activer ou désactiver les messages électroniques envoyés aux utilisateurs de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="61064-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="61064-123">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="61064-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="61064-124">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-125">Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="61064-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="61064-126">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="61064-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="61064-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61064-127">Click **Save**.</span></span>

    <span data-ttu-id="61064-p105">Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres d'audioconférence en accédant aux propriétés d'audioconférence de l’utilisateur et en cliquant sur **Envoyer les informations de conférence par courrier électronique**. L'ID de conférence et le numéro de téléphone d'audioconférence par défaut seront inclus dans l’invitation à la réunion, mais pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="61064-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="61064-130">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="61064-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="61064-131">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="61064-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="61064-132">Utilisation de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61064-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="61064-133">Vous pouvez également utiliser Windows PowerShell et exécuter :[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="61064-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="61064-134">Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="61064-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="61064-135">Vous pouvez apporter des modifications aux courriers électroniques envoyés automatiquement à vos utilisateurs, y compris l’adresse de messagerie réelle et le nom d’affichage des informations de contact de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="61064-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="61064-136">Par défaut, l’expéditeur des courriers électroniques est Microsoft 365 ou Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de la cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="61064-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="61064-137">Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier électronique aux utilisateurs, vous devez :</span><span class="sxs-lookup"><span data-stu-id="61064-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="61064-138">Entrez l’adresse de courrier dans le _paramètre SendEmailFromAddress._</span><span class="sxs-lookup"><span data-stu-id="61064-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="61064-139">entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="61064-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="61064-140">Définissez le paramètre _SendEmailOverride_ à _True_.</span><span class="sxs-lookup"><span data-stu-id="61064-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="61064-141">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="61064-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="61064-142">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :</span><span class="sxs-lookup"><span data-stu-id="61064-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="61064-143">Vous pouvez utiliser l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) pour gérer d’autres paramètres de votre organisation, y compris le courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="61064-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="61064-144">Consultez les messages électroniques envoyés automatiquement aux utilisateurs en cas de modification de [leurs paramètres d’audioconférence.](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="61064-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="61064-145">Réinitialisation de l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="61064-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="61064-146">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-147">Dans le centre d’administration, > **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61064-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="61064-148">Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence**, et dans le volet Actions, sous d'**ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="61064-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="61064-149">Dans la fenêtre **Réinitialiser l’ID de conférence** ? cliquez sur **Oui.**</span><span class="sxs-lookup"><span data-stu-id="61064-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="61064-150">Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé.</span><span class="sxs-lookup"><span data-stu-id="61064-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="61064-151">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="61064-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="61064-152">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="61064-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="61064-153">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="61064-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="61064-154">Les utilisateurs peuvent utiliser l’outil Skype Entreprise migration de réunions pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="61064-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="61064-155">Pour découvrir comment télécharger, installer et exécuter l’outil de mise à jour de réunion Skype Entreprise, voir : Outil de mise à jour des réunions pour Skype Entreprise et [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype Entreprise Online, Outil de migration de réunions [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et Skype Entreprise Online, outil de migration de réunion [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="61064-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="61064-156">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="61064-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="61064-157">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="61064-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="61064-158">Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="61064-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="61064-159">Bien qu’un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu’un utilisateur ne souhaite pas l’utiliser et que vous le définissez sur un nombre donné, ou que vos utilisateurs ne se souvenent pas ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="61064-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="61064-160">Vous pouvez utiliser le centre d’administration Skype Entreprise et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="61064-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="61064-161">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-162">Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="61064-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="61064-163">Cliquez **sur** Utilisateurs, puis sélectionnez l’utilisateur pour qui vous voulez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="61064-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="61064-164">Dans le volet Action, sous Code **confidentiel,** cliquez sur **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="61064-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="61064-165">Les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="61064-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="61064-166">Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, le message de réinitialisation du code confidentiel ne sera pas envoyé et vous de aurez à envoyer manuellement le code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61064-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="61064-167">Le code confidentiel ne sera affiché qu'après avoir été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="61064-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="61064-168">Une fois qu’il s’affiche juste après la réinitialisation, le code confidentiel n’est plus affiché dans les propriétés de l’utilisateur. \*\*\*\*\* s’affiche à la place.</span><span class="sxs-lookup"><span data-stu-id="61064-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="61064-169">Consultez [réinitialiser le code confidentiel de l’audioconférence.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="61064-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="61064-170">Envoyer un courrier électronique avec des informations d’audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="61064-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="61064-171">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-172">Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="61064-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="61064-173">Cliquez **sur** Utilisateurs, puis sélectionnez l’utilisateur pour qui vous voulez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="61064-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="61064-174">Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="61064-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61064-175">Ainsi, le code confidentiel de l’audioconférence n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61064-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="61064-176">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="61064-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="61064-177">Définition des numéros de téléphone inclus dans les invitations</span><span class="sxs-lookup"><span data-stu-id="61064-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="61064-178">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-179">Dans le centre d’administration, > **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61064-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="61064-180">Dans le groupe de navigation de gauche, allez à Utilisateurs de **l’audioconférence.**  >  </span><span class="sxs-lookup"><span data-stu-id="61064-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="61064-181">Sélectionnez l’utilisateur que vous voulez activer pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="61064-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="61064-182">Dans le volet Action, vous pouvez définir le **Numéro payant** et, si permis, le **Numéro gratuit**.</span><span class="sxs-lookup"><span data-stu-id="61064-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="61064-183">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61064-183">Click **Save**.</span></span>

<span data-ttu-id="61064-184">Consultez [Définir les numéros de téléphone inclus dans les invitations.](set-the-phone-numbers-included-on-invites.md)</span><span class="sxs-lookup"><span data-stu-id="61064-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="61064-185">Choix des paramètres de pont d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="61064-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="61064-186">**Définir l’expérience de réunion lorsque les appelants participent à une réunion**</span><span class="sxs-lookup"><span data-stu-id="61064-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="61064-187">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-188">Dans le centre d’administration, > **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61064-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="61064-189">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez aux paramètres du pont Microsoft d’audioconférence.   >  </span><span class="sxs-lookup"><span data-stu-id="61064-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="61064-190">Sous **Expérience de rejoindre une réunion,** sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="61064-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="61064-p112">Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="61064-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="61064-193">Ce paramètre peut être réglé réunion par réunion lorsqu’un utilisateur participe à une réunion  à l’aide d’une application Skype Entreprise et qu’il modifie le paramètre Annoncer l’entrée ou le départ des personnes dans le menu **Options** Réunion Skype de la réunion.</span><span class="sxs-lookup"><span data-stu-id="61064-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="61064-p113">**Demander aux appelants d'enregistrer leur nom avant de se joindre à la réunion**. C'est le choix par défaut. Si vous effacer cette case à cocher, les appelants ne se verront pas demander d'enregistrer leur nom avant de se joindre à une réunion.</span><span class="sxs-lookup"><span data-stu-id="61064-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="61064-196">Après avoir fait vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61064-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="61064-197">Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="61064-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="61064-198">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="61064-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="61064-199">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-200">Dans le centre d’administration, > **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61064-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="61064-201">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez aux paramètres du pont Microsoft d’audioconférence.   >  </span><span class="sxs-lookup"><span data-stu-id="61064-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="61064-202">Sous **Sécurité,** entrez le nombre de chiffres  que vous souhaitez pour le code confidentiel dans la liste de longueur du code confidentiel, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="61064-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="61064-203">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="61064-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="61064-204">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="61064-204">The default is 5.</span></span>
    
<span data-ttu-id="61064-205">Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="61064-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="61064-206">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="61064-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="61064-207">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-208">Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="61064-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="61064-209">Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.</span><span class="sxs-lookup"><span data-stu-id="61064-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="61064-210">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61064-210">Click **Save**.</span></span>

    <span data-ttu-id="61064-211">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61064-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="61064-212">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="61064-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="61064-213">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="61064-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="61064-214">Consulter et définir la langue principale (par défaut) et les langues secondaires (secondaires) d’un pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="61064-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="61064-215">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-216">Dans le centre d’administration, > **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61064-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="61064-217">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, cliquez sur **Audioconférence,** puis sur **Pont Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="61064-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="61064-218">Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="61064-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="61064-219">Vous pouvez également définir la langue principale et les langues secondaires qui sont pris en charge lorsque vous sélectionnez Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="61064-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="61064-220">L’ordre que vous sélectionnez dans les listes sera l’ordre dans lequel les langues seront présentées aux appelants.</span><span class="sxs-lookup"><span data-stu-id="61064-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="61064-221">Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="61064-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="61064-222">Consulter les numéros d’accès pour les conférences audio</span><span class="sxs-lookup"><span data-stu-id="61064-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="61064-223">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-224">Dans le centre d’administration, > **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61064-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="61064-225">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez au pont Microsoft de l’audioconférence.   >  </span><span class="sxs-lookup"><span data-stu-id="61064-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="61064-226">Depuis cette section, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="61064-226">Here you can:</span></span>

   - <span data-ttu-id="61064-227">Affichez les numéros de téléphone Microsoft 365 ou Office 365 à utiliser pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="61064-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="61064-228">Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="61064-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="61064-p117">Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="61064-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="61064-231">Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié. > </span><span class="sxs-lookup"><span data-stu-id="61064-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="61064-232">Consultez [la liste des numéros d’audioconférence.](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="61064-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="61064-233">Affichage de la liste des utilisateurs activés</span><span class="sxs-lookup"><span data-stu-id="61064-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="61064-234">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61064-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="61064-235">Dans le centre d’administration, > **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61064-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="61064-236">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez à Conférence **audio** et> puis **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="61064-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="61064-237">Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="61064-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="61064-238">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="61064-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="61064-239">Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation à l’aide Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61064-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="61064-240">Cela facilite l’application des paramètres à tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="61064-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="61064-241">Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](/previous-versions//mt228132(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="61064-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="61064-242">Voici les paramètres au niveau de l’organisation :</span><span class="sxs-lookup"><span data-stu-id="61064-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="61064-243">**Configuration des notifications d’entrée/de sortie** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="61064-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="61064-244">**Définition de l’enregistrement des noms** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="61064-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="61064-245">**Définition de la longueur du code confidentiel** La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="61064-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="61064-246">**Définition seulement des réunions téléphoniques à partir d’un téléphone** La valeur par défaut _$false_.</span><span class="sxs-lookup"><span data-stu-id="61064-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="61064-247">**Définition de savoir s’il faut envoyer un message électronique aux utilisateurs** La valeur par défaut est _$true_.</span><span class="sxs-lookup"><span data-stu-id="61064-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="61064-248">**Définition de savoir s’il faut envoyer un message électronique à partir d’un compte différent** La valeur par défaut est _$false_.</span><span class="sxs-lookup"><span data-stu-id="61064-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="61064-249">**Définition de l’adresse de messagerie De qui est envoyée aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="61064-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="61064-250">**Définition du nom d'affichage du message électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.</span><span class="sxs-lookup"><span data-stu-id="61064-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="61064-251">Vous voulez en savoir plus sur Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61064-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="61064-252">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="61064-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="61064-253">En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="61064-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="61064-254">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="61064-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="61064-255">Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="61064-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="61064-256">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="61064-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="61064-257">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du centre d’administration uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="61064-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="61064-258">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="61064-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="61064-259">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="61064-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="61064-260">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="61064-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="61064-261">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="61064-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="61064-p121">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="61064-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="61064-264">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="61064-264">Related topics</span></span>

[<span data-ttu-id="61064-265">Gestion des paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="61064-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)
