---
title: Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.
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
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Cette section explique la procédure d’attribution d’une licence de conférence rendez-vous et d’un ID de conférence Microsoft Teams à un utilisateur, ainsi que les autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: 201da13370852b6506fe7aa32f695d973bcc637a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202764"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="61fb2-103">Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="61fb2-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="61fb2-104">Il peut être plus simple pour vous d'afficher tous les paramètres de conférence rendez-vous à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="61fb2-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="61fb2-105">Attribuer une licence d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="61fb2-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="61fb2-106">Vous ne pouvez pas attribuer de licences par le biais de Teams.</span><span class="sxs-lookup"><span data-stu-id="61fb2-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="61fb2-107">Vous devez utiliser le centre d'administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="61fb2-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="61fb2-108">Reportez-vous à la rubrique [Attribuer des licences Skype Entreprise et Microsoft Teams](assign-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="61fb2-108">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="61fb2-109">**Pour attribuer une licence à un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="61fb2-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="61fb2-110">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="61fb2-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="61fb2-111">Dans le volet de navigation de gauche du **centre d’administration Office 365**, accédez à **Utilisateurs** > **Utilisateurs actifs**, puis sélectionnez le ou les utilisateurs dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="61fb2-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="61fb2-112">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage.</span><span class="sxs-lookup"><span data-stu-id="61fb2-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="61fb2-113">Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="61fb2-114">Dans le volet Action sous **Licences de produits**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="61fb2-115">Dans la page **Licences de produits** , activer la **Conférence Audio** , puis sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="61fb2-116">Pour plus d’informations sur les licences, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-116">For more on licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="61fb2-p104">Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="61fb2-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="61fb2-119">Activer ou désactiver l'envoi de courriers électroniques aux utilisateurs d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="61fb2-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="61fb2-120">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-121">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="61fb2-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="61fb2-122">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="61fb2-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="61fb2-123">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="61fb2-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-124">Click **Save**.</span></span>

    
<span data-ttu-id="61fb2-125">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="61fb2-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="61fb2-126">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="61fb2-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="61fb2-127">Réinitialisation de l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="61fb2-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="61fb2-128">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-128">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-129">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="61fb2-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="61fb2-130">Sous **Conférence Audio**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="61fb2-131">Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="61fb2-132">Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé.</span><span class="sxs-lookup"><span data-stu-id="61fb2-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="61fb2-133">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="61fb2-133">It's enabled by default.</span></span>

<span data-ttu-id="61fb2-134">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="61fb2-135">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="61fb2-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="61fb2-136">Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="61fb2-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="61fb2-137">Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou vos utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="61fb2-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="61fb2-138">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-138">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-139">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="61fb2-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="61fb2-140">Sous **Conférence Audio**, cliquez sur **Réinitialiser le code confidentiel**, puis cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="61fb2-141">Les utilisateurs recevront un message électronique avec leur code confidentiel lorsqu’ils sont activés pour les services d’audioconférence ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="61fb2-141">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="61fb2-142">Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un message électronique de réinitialisation du code confidentiel ne seront pas envoyé et vous devez envoyer manuellement le code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61fb2-142">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="61fb2-143">Le code confidentiel ne sera affiché qu'après avoir été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="61fb2-143">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="61fb2-144">Une fois qu’il est affiché juste après la réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur ; au lieu de cela, \*\*\* s’affichera.</span><span class="sxs-lookup"><span data-stu-id="61fb2-144">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="61fb2-145">Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="61fb2-146">Envoyer un message électronique avec des informations de conférence Audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="61fb2-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="61fb2-147">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-147">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-148">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="61fb2-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="61fb2-149">**Conférence Audio**, cliquez sur **Envoyer les informations de conférence dans le message électronique**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="61fb2-150">Lorsque vous faites cela, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61fb2-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="61fb2-151">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="61fb2-152">Définir les numéros de téléphone inclus dans les invitations</span><span class="sxs-lookup"><span data-stu-id="61fb2-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="61fb2-153">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-153">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-154">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="61fb2-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="61fb2-155">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="61fb2-156">Dans le volet de **Conférence Audio** , vous pouvez définir le **numéro de téléphone payant** et, si Oui, le **numéro d’appel gratuit**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="61fb2-157">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-157">Click **Save**.</span></span>
    
<span data-ttu-id="61fb2-158">Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="61fb2-159">Choisir les paramètres de pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="61fb2-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="61fb2-160">**Définir l’expérience lorsque les appelants participer à une réunion**</span><span class="sxs-lookup"><span data-stu-id="61fb2-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="61fb2-161">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-161">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-162">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="61fb2-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="61fb2-163">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="61fb2-164">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).</span><span class="sxs-lookup"><span data-stu-id="61fb2-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="61fb2-165">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="61fb2-165">This is enabled by default.</span></span> <span data-ttu-id="61fb2-166">Si vous désactivez cette option, les utilisateurs qui ont déjà joint la réunion par défaut ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="61fb2-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="61fb2-167">Sous **type d’entrée/sortie annonce**, choisissez **tonalités** ou **les noms ou les numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="61fb2-168">Si vous choisissez des **noms ou des numéros de téléphone**, vous pouvez également choisir activer ou désactiver **les appelants Ask à enregistrer leur nom avant de participer à la réunion**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="61fb2-169">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-169">Click **Save**.</span></span>

    
<span data-ttu-id="61fb2-170">Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="61fb2-171">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="61fb2-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="61fb2-172">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="61fb2-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="61fb2-173">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-173">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="61fb2-174">Dans le volet **paramètres du pont** , entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-174">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="61fb2-175">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="61fb2-175">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="61fb2-176">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="61fb2-176">The default is 5.</span></span>

    
<span data-ttu-id="61fb2-177">Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="61fb2-178">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="61fb2-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="61fb2-179">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="61fb2-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="61fb2-180">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-180">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="61fb2-181">Dans le volet **paramètres du pont** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="61fb2-182">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="61fb2-183">Vous pouvez également envoyer courrier électronique à l’utilisateur avec les paramètres de conférence audio, en accédant aux propriétés de conférence audio de l’utilisateur et en cliquant sur **Envoyer les informations de conférence dans le message électronique**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="61fb2-184">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="61fb2-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="61fb2-185">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="61fb2-186">Afficher et définir principal (par défaut) et secondaires (autres) langues sur un pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="61fb2-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="61fb2-187">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-187">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-188">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="61fb2-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="61fb2-189">Sélectionnez un numéro de téléphone dans la liste, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-189">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="61fb2-190">Choisir les langues sous **langue par défaut** et **d’autres langues (facultatifs)**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="61fb2-191">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-191">Click **Save**.</span></span>


<span data-ttu-id="61fb2-192">Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="61fb2-193">Voir les numéros de services d’audioconférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="61fb2-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="61fb2-194">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="61fb2-194">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="61fb2-195">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="61fb2-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="61fb2-196">Sélectionnez un numéro de téléphone dans la liste, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="61fb2-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="61fb2-197">Depuis cette section, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="61fb2-197">Here you can:</span></span>
    
   - <span data-ttu-id="61fb2-198">Afficher les numéros de téléphone qui sont définis par Office 365 à utiliser pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="61fb2-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="61fb2-199">Afficher l’emplacement et la langue principale, qui sera utilisée par le standard automatique de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="61fb2-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="61fb2-200">Consultez la rubrique [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61fb2-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="61fb2-201">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="61fb2-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="61fb2-p111">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="61fb2-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="61fb2-205">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="61fb2-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="61fb2-206">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61fb2-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="61fb2-207">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="61fb2-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="61fb2-208">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="61fb2-208">Related topics</span></span>

[<span data-ttu-id="61fb2-209">Gestion des paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="61fb2-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


