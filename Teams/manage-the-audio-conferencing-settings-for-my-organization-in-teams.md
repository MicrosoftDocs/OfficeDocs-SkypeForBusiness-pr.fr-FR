---
title: Gérer les paramètres d’audioconférence
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Cette section explique la procédure d’attribution d’une licence de conférence rendez-vous et d’un ID de conférence Microsoft Teams à un utilisateur, ainsi que les autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: 513695cf905c7cb21f332f6b025318253b03334d
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141157"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="ace80-103">Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ace80-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="ace80-104">Il peut être plus simple pour vous d'afficher tous les paramètres de conférence rendez-vous à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="ace80-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="ace80-105">Attribuer une licence d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="ace80-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="ace80-106">Vous ne pouvez pas attribuer de licences par le biais de Teams.</span><span class="sxs-lookup"><span data-stu-id="ace80-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="ace80-107">Vous devez utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ace80-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="ace80-108">Reportez-vous à la rubrique [Attribuer des licences Skype Entreprise et Microsoft Teams](assign-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="ace80-108">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="ace80-109">**Pour attribuer une licence à un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ace80-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="ace80-110">Connectez-vous à Microsoft 365 à l’aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="ace80-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ace80-111">Dans le volet de navigation de gauche du **Centre d’administration Microsoft 365**, **accédez à** > utilisateurs**actifs**, puis sélectionnez le ou les utilisateurs dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ace80-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ace80-112">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage.</span><span class="sxs-lookup"><span data-stu-id="ace80-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="ace80-113">Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="ace80-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="ace80-114">Dans le volet Action sous **Licences de produits**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ace80-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="ace80-p103">Sur la page **licences de produits** , activez l' **audioconférence** , puis cliquez sur **Enregistrer**. Pour plus d’informations sur les licences, voir [licences de complément Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ace80-p104">Dès lors que vous attribuez la licence, il est possible que Microsoft n’apparaisse pas dans la liste en tant que fournisseur de services d’audioconférence. Si tel est le cas, déconnectez-vous du centre d’administration ou appuyez sur CTRL + F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="ace80-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="ace80-119">Activer ou désactiver l'envoi de courriers électroniques aux utilisateurs d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="ace80-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="ace80-120">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-121">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="ace80-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ace80-122">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="ace80-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ace80-123">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="ace80-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="ace80-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ace80-124">Click **Save**.</span></span>

    
<span data-ttu-id="ace80-125">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ace80-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="ace80-126">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ace80-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="ace80-127">Réinitialisation de l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="ace80-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="ace80-128">![Icône montrant le logo](media/teams-logo-30x30.png) équipes **à l’aide du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-129">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ace80-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ace80-130">Sous **audioconférence**, cliquez sur **réinitialisation**de l’ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="ace80-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="ace80-131">Dans la fenêtre de **réinitialisation de l’ID de conférence ?** , cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="ace80-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="ace80-132">Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé.</span><span class="sxs-lookup"><span data-stu-id="ace80-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="ace80-133">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="ace80-133">It's enabled by default.</span></span>

<span data-ttu-id="ace80-134">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="ace80-135">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="ace80-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="ace80-136">Un ID de conférence unique est attribué à chaque réunion qu’un utilisateur planifie.</span><span class="sxs-lookup"><span data-stu-id="ace80-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="ace80-137">Même si un ID de conférence est automatiquement créé et attribué à un utilisateur, il peut arriver que l’utilisateur ne l’utilise pas et que vous vouliez le définir sur un certain numéro ou que vos utilisateurs ne se souviens pas ou aient perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="ace80-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="ace80-138">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-139">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ace80-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ace80-140">Sous **audioconférence**, cliquez sur **Réinitialiser le code confidentiel**, puis cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="ace80-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="ace80-141">Les utilisateurs recevront un message électronique contenant leur code confidentiel lorsqu’ils sont activés pour les conférences audio ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="ace80-141">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="ace80-142">En revanche, si vous avez désactivé l’envoi automatique de courriers électroniques, le message de réinitialisation du code confidentiel ne sera pas envoyé et vous devrez envoyer manuellement le code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ace80-142">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="ace80-143">Le code confidentiel ne sera affiché qu'après avoir été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="ace80-143">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="ace80-144">Après sa réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur. au lieu de cela, \* \* \* \* \* sera affiché.</span><span class="sxs-lookup"><span data-stu-id="ace80-144">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="ace80-145">Voir [Réinitialiser le code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="ace80-146">Envoyer un courrier électronique à un utilisateur avec ses informations de conférence audio</span><span class="sxs-lookup"><span data-stu-id="ace80-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="ace80-147">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-148">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ace80-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ace80-149">Sous **audioconférence**, cliquez sur **Envoyer les informations sur la Conférence par courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="ace80-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="ace80-150">Dans ce cas, le code confidentiel de l’audioconférence n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ace80-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="ace80-151">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="ace80-152">Définir les numéros de téléphone inclus dans les invitations</span><span class="sxs-lookup"><span data-stu-id="ace80-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="ace80-153">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-154">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ace80-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ace80-155">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ace80-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="ace80-156">Dans le volet **audioconférence** , vous pouvez définir le **numéro payant** et, s’il est autorisé, le **numéro**gratuit.</span><span class="sxs-lookup"><span data-stu-id="ace80-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="ace80-157">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ace80-157">Click **Save**.</span></span>
    
<span data-ttu-id="ace80-158">Reportez-vous [à la rubrique définition des numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="ace80-159">Sélectionnez Paramètres du pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="ace80-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="ace80-160">**Définir l’accès à la réunion lorsque les appelants rejoignent une réunion**</span><span class="sxs-lookup"><span data-stu-id="ace80-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="ace80-161">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-162">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="ace80-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ace80-163">Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="ace80-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ace80-164">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).</span><span class="sxs-lookup"><span data-stu-id="ace80-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="ace80-165">Cette option est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ace80-165">This is enabled by default.</span></span> <span data-ttu-id="ace80-166">Si vous désactivez cette option, les utilisateurs qui ont déjà rejoint la réunion par défaut ne sont pas avertis lorsqu’une personne entre ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="ace80-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="ace80-167">Sous **type d’annonce d’entrée/sortie**, sélectionnez **tonalités** ou **noms ou numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="ace80-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="ace80-168">Si vous choisissez des **noms ou des numéros de téléphone**, vous pouvez également choisir d’activer ou de désactiver **la demande aux appelants d’enregistrer leur nom avant de participer à la réunion**.</span><span class="sxs-lookup"><span data-stu-id="ace80-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="ace80-169">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ace80-169">Click **Save**.</span></span>

    
<span data-ttu-id="ace80-170">Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="ace80-171">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="ace80-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="ace80-172">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="ace80-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ace80-173">Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="ace80-173">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ace80-174">Dans le volet **paramètres du pont** , entrez le nombre de chiffres souhaités pour le code confidentiel dans la liste longueur du **code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ace80-174">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="ace80-175">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="ace80-175">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="ace80-176">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="ace80-176">The default is 5.</span></span>

    
<span data-ttu-id="ace80-177">Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="ace80-178">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="ace80-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="ace80-179">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="ace80-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ace80-180">Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="ace80-180">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ace80-181">Dans le volet **paramètres du pont** , activez ou désactivez l' **envoi automatique de messages électroniques aux utilisateurs en cas de modification de leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="ace80-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="ace80-182">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ace80-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="ace80-183">Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres de l’audioconférence en accédant aux propriétés de l’audioconférence de l’utilisateur, puis en cliquant sur envoyer les informations sur la **Conférence par courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="ace80-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="ace80-184">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="ace80-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="ace80-185">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="ace80-186">Afficher et définir les langues principales (par défaut) et secondaires (de remplacement) sur un pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="ace80-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="ace80-187">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-187">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-188">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="ace80-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ace80-189">Sélectionnez un numéro de téléphone dans la liste, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="ace80-189">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="ace80-190">Choisissez les langues de votre choix dans **langue par défaut** et **autres langues (facultatif)**.</span><span class="sxs-lookup"><span data-stu-id="ace80-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="ace80-191">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ace80-191">Click **Save**.</span></span>


<span data-ttu-id="ace80-192">Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="ace80-193">Afficher les numéros d’accès pour les conférences audio</span><span class="sxs-lookup"><span data-stu-id="ace80-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="ace80-194">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ace80-194">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ace80-195">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="ace80-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ace80-196">Sélectionnez un numéro de téléphone dans la liste, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="ace80-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="ace80-197">Depuis cette section, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="ace80-197">Here you can:</span></span>
    
   - <span data-ttu-id="ace80-198">Affichez les numéros de téléphone définis par Office 365 pour être utilisés pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="ace80-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="ace80-199">Affichez l’emplacement, ainsi que la langue principale, qui sera utilisée par le standard automatique de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="ace80-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="ace80-200">Voir [la liste des numéros de conférence audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ace80-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ace80-201">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="ace80-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ace80-p111">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ace80-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ace80-205">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ace80-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ace80-206">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ace80-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ace80-207">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ace80-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="ace80-208">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ace80-208">Related topics</span></span>

[<span data-ttu-id="ace80-209">Gestion des paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="ace80-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


