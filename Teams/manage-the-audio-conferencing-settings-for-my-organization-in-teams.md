---
title: Gérer les paramètres d'audioconférence de mon organisation dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Cette section explique la procédure d’attribution d’une licence de conférence rendez-vous et d’un ID de conférence Microsoft Teams à un utilisateur, ainsi que les autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: b63650833c7c844de11ecb833288b6568604f919
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375862"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="9974c-103">Gérer les paramètres d'audioconférence de mon organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9974c-103">Manage the Audio Conferencing settings for my organization in Microsoft Teams</span></span>

<span data-ttu-id="9974c-104">Il peut être plus simple pour vous d'afficher tous les paramètres de conférence rendez-vous à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="9974c-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="9974c-105">Attribuer une licence d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="9974c-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="9974c-106">Vous ne pouvez pas attribuer de licences par le biais de Teams.</span><span class="sxs-lookup"><span data-stu-id="9974c-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="9974c-107">Vous devez utiliser le centre d'administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="9974c-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="9974c-108">Reportez-vous à la rubrique [Attribuer des licences Skype Entreprise et Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)</span><span class="sxs-lookup"><span data-stu-id="9974c-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="9974c-109">**Pour attribuer une licence à un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="9974c-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="9974c-110">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="9974c-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9974c-111">Dans le volet de navigation de gauche du **centre d’administration Office 365**, accédez à **Utilisateurs** > **Utilisateurs actifs**, puis sélectionnez le ou les utilisateurs dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="9974c-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9974c-112">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage.</span><span class="sxs-lookup"><span data-stu-id="9974c-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="9974c-113">Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="9974c-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="9974c-114">Dans le volet Action sous **Licences de produits**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9974c-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="9974c-p103">Sur la page **Affecter une licence**, cochez **Conférence RTC Skype Entreprise**, puis cliquez sur **Enregistrer**. Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="9974c-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9974c-p104">Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="9974c-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="9974c-119">Activer ou désactiver l'envoi de courriers électroniques aux utilisateurs d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="9974c-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="9974c-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**</span><span class="sxs-lookup"><span data-stu-id="9974c-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-121">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="9974c-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9974c-122">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="9974c-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9974c-123">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="9974c-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="9974c-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9974c-124">Click **Save**.</span></span>

    
<span data-ttu-id="9974c-125">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9974c-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="9974c-126">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9974c-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="9974c-127">Modifier les coordonnées de l'expéditeur dans les courriers électroniques envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9974c-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="9974c-128">Vous pouvez apporter des modifications aux courriers électroniques envoyés automatiquement à vos utilisateurs, dont l'adresse électronique et le nom d'affichage figurant dans les informations de contact de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="9974c-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="9974c-129">Par défaut, l'envoi des courriers électroniques se fera à partir d'Office 365, mais vous pouvez modifier l'adresse électronique et le nom d'affichage à l'aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9974c-129">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="9974c-130">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9974c-130">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="9974c-131">Réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="9974c-131">Reset the meeting conference ID</span></span>

<span data-ttu-id="9974c-132">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="9974c-132">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-133">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="9974c-133">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9974c-134">Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="9974c-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="9974c-135">Dans la fenêtre **Réinitialiser l’ID de conférence ?**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="9974c-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="9974c-136">Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé.</span><span class="sxs-lookup"><span data-stu-id="9974c-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="9974c-137">Cette option est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="9974c-137">It's enabled by default.</span></span>

<span data-ttu-id="9974c-138">Reportez-vous à la section [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="9974c-139">Réinitialiser le code confidentiel d’un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="9974c-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="9974c-140">Chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="9974c-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="9974c-141">Bien qu'un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu'un utilisateur ne souhaite pas utiliser cet ID et préfère le définir sur un numéro spécifique, ou qu’il ne se rappelle pas de son ID de conférence ou l’ait perdu.</span><span class="sxs-lookup"><span data-stu-id="9974c-141">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="9974c-142">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="9974c-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-143">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="9974c-143">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9974c-144">Sous **Audioconférence**, cliquez sur **Réinitialiser le code confidentiel**, puis cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="9974c-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="9974c-145">Les utilisateurs recevront un courrier électronique avec leur code confidentiel lorsqu'ils seront activés pour l’audioconférence ou lorsque le code confidentiel sera réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="9974c-145">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="9974c-146">Si vous avez désactivé l'envoi automatique de courriers électroniques, aucun message de réinitialisation du code confidentiel ne sera envoyé, ce qui vous obligera à lui envoyer manuellement.</span><span class="sxs-lookup"><span data-stu-id="9974c-146">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="9974c-147">Le code confidentiel ne sera affiché qu'après avoir été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="9974c-147">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="9974c-148">Lorsqu'il s'affiche après sa réinitialisation, le code confidentiel n'apparaît plus dans les propriétés de l'utilisateur. Il apparaît à la place sous la forme \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="9974c-148">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="9974c-149">Reportez-vous à la section [Réinitialiser le code confidentiel d'audioconférence](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-149">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="9974c-150">Envoyer à un utilisateur un courrier électronique qui contient les informations d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="9974c-150">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="9974c-151">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="9974c-151">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-152">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="9974c-152">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9974c-153">Sous **Audioconférence**, cliquez sur **Envoyer les informations de la conférence dans un courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="9974c-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9974c-154">Dans ce cas, le code confidentiel d’audioconférence n'est pas envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9974c-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="9974c-155">Reportez-vous à la section [Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="9974c-156">Définir les numéros de téléphone inclus dans les invitations</span><span class="sxs-lookup"><span data-stu-id="9974c-156">Set the phone numbers included on invites</span></span>

<span data-ttu-id="9974c-157">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="9974c-157">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-158">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="9974c-158">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9974c-159">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9974c-159">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="9974c-160">Dans le volet de **Conférence Audio** , vous pouvez définir le **numéro de téléphone payant** et, si Oui, le **numéro d’appel gratuit**.</span><span class="sxs-lookup"><span data-stu-id="9974c-160">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="9974c-161">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9974c-161">Click **Save**.</span></span>
    
<span data-ttu-id="9974c-162">Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-162">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="9974c-163">Choisir les paramètres de pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="9974c-163">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="9974c-164">Configuration des paramètres du pont de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="9974c-164">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="9974c-165">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="9974c-165">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-166">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="9974c-166">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9974c-167">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="9974c-167">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9974c-168">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).</span><span class="sxs-lookup"><span data-stu-id="9974c-168">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="9974c-169">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="9974c-169">This is enabled by default.</span></span> <span data-ttu-id="9974c-170">Si vous désactivez cette option, les utilisateurs qui ont déjà joint la réunion par défaut ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="9974c-170">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="9974c-171">Sous **type d’entrée/sortie annonce**, choisissez **tonalités** ou **les noms ou les numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="9974c-171">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="9974c-172">Si vous choisissez des **noms ou des numéros de téléphone**, vous pouvez également choisir activer ou désactiver **les appelants Ask à enregistrer leur nom avant de participer à la réunion**.</span><span class="sxs-lookup"><span data-stu-id="9974c-172">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="9974c-173">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9974c-173">Click **Save**.</span></span>

    
<span data-ttu-id="9974c-174">Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-174">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="9974c-175">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="9974c-175">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="9974c-176">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="9974c-176">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9974c-177">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="9974c-177">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9974c-178">Dans le volet **paramètres du pont** , entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9974c-178">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="9974c-179">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="9974c-179">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="9974c-180">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="9974c-180">The default is 5.</span></span>

    
<span data-ttu-id="9974c-181">Le code confidentiel doit comporter de 4 à 12 chiffres. La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="9974c-181">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="9974c-182">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="9974c-182">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="9974c-183">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="9974c-183">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9974c-184">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="9974c-184">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9974c-185">Dans le volet **paramètres du pont** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="9974c-185">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="9974c-186">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9974c-186">Click **Save**.</span></span> 
 
    <span data-ttu-id="9974c-187">Vous pouvez également envoyer courrier électronique à l’utilisateur avec les paramètres de conférence audio, en accédant aux propriétés de conférence audio de l’utilisateur et en cliquant sur **Envoyer les informations de conférence dans le message électronique**.</span><span class="sxs-lookup"><span data-stu-id="9974c-187">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="9974c-188">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="9974c-188">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="9974c-189">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-189">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="9974c-190">Afficher et définir principal (par défaut) et secondaires (autres) langues sur un pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="9974c-190">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="9974c-191">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="9974c-191">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-192">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="9974c-192">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9974c-193">Sélectionnez un numéro de téléphone dans la liste, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9974c-193">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="9974c-194">Choisir les langues sous **langue par défaut** et **d’autres langues (facultatifs)**.</span><span class="sxs-lookup"><span data-stu-id="9974c-194">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="9974c-195">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9974c-195">Click **Save**.</span></span>


<span data-ttu-id="9974c-196">Vous pouvez également définir la langue principale et les langues secondaires prises en charge lorsque vous sélectionnez Microsoft comme fournisseur de conférences rendez-vous. L'ordre que vous sélectionnez dans les listes déroulantes correspondra à l'ordre dans lequel les langues sont proposées aux appelants.</span><span class="sxs-lookup"><span data-stu-id="9974c-196">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="9974c-197">Voir les numéros de services d’audioconférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="9974c-197">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="9974c-198">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="9974c-198">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9974c-199">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="9974c-199">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9974c-200">Sélectionnez un numéro de téléphone dans la liste, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9974c-200">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="9974c-201">Depuis cette section, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="9974c-201">Here you can:</span></span>
    
   - <span data-ttu-id="9974c-202">Afficher les numéros de téléphone qui sont définis par Office 365 à utiliser pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="9974c-202">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="9974c-203">Afficher l’emplacement et la langue principale, qui sera utilisée par le standard automatique de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="9974c-203">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="9974c-204">Consultez la rubrique [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-204">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9974c-205">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="9974c-205">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9974c-p112">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9974c-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9974c-209">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9974c-209">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9974c-210">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9974c-210">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9974c-211">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9974c-211">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="9974c-212">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9974c-212">Related topics</span></span>

[<span data-ttu-id="9974c-213">Gérer les paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="9974c-213">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


