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
- m365initiative-meetings
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
ms.openlocfilehash: f2d056ffd2c3b40b8e39f6d4727859b45e675ebf
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031800"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="eb061-103">Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eb061-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="eb061-104">Il peut être plus simple pour vous d'afficher tous les paramètres de conférence rendez-vous à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="eb061-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="eb061-105">Attribuer une licence d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="eb061-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="eb061-106">Vous ne pouvez pas attribuer de licences par le biais de Teams.</span><span class="sxs-lookup"><span data-stu-id="eb061-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="eb061-107">Vous devez utiliser le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb061-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="eb061-108">Voir [Attribuer des licences de modules add-on Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="eb061-108">See [Assign Microsoft Teams add-on licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span> 
  
 <span data-ttu-id="eb061-109">**Pour attribuer une licence à un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="eb061-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="eb061-110">Connectez-vous à Microsoft 365 à l’aide de votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="eb061-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb061-111">Dans le panneau de navigation gauche du Centre d’administration **Microsoft 365,** sélectionnez Utilisateurs actifs, puis sélectionnez le ou les utilisateurs dans la liste des  >  utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="eb061-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb061-112">Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage.</span><span class="sxs-lookup"><span data-stu-id="eb061-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="eb061-113">Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="eb061-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="eb061-114">Dans le volet Action sous **Licences de produits**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="eb061-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="eb061-p103">Dans la page **Licences de produits,** activer **l’audioconférence,** puis cliquer sur **Enregistrer.** Pour plus d’informations sur les licences, voir [Licences de modules logiciels de la suite Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="eb061-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="eb061-p104">Une fois que vous avez attribué la licence, Microsoft peut ne pas apparaître initialement dans la liste en tant que fournisseur de services d’audioconférence. Dans ce cas, déconnectez-vous du Centre d’administration ou appuyez sur Ctrl+F5 pour actualiser la fenêtre du navigateur.</span><span class="sxs-lookup"><span data-stu-id="eb061-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="eb061-119">Activer ou désactiver l'envoi de courriers électroniques aux utilisateurs d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="eb061-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="eb061-120">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-121">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="eb061-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="eb061-122">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="eb061-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="eb061-123">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="eb061-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="eb061-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb061-124">Click **Save**.</span></span>

    
<span data-ttu-id="eb061-125">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="eb061-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="eb061-126">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="eb061-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="eb061-127">Réinitialisation de l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="eb061-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="eb061-128">![Icône montrant le logo Teams à ](media/teams-logo-30x30.png) **l’aide du Centre d’administration Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-129">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="eb061-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="eb061-130">Sous **Audioconférence,** cliquez sur **Réinitialiser l’ID de conférence.**</span><span class="sxs-lookup"><span data-stu-id="eb061-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="eb061-131">Dans la fenêtre **Réinitialiser l’ID de conférence?** , cliquez sur **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="eb061-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="eb061-132">Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé.</span><span class="sxs-lookup"><span data-stu-id="eb061-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="eb061-133">Il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="eb061-133">It's enabled by default.</span></span>

<span data-ttu-id="eb061-134">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="eb061-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="eb061-135">Réinitialisation du code confidentiel d'un organisateur de conférence</span><span class="sxs-lookup"><span data-stu-id="eb061-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="eb061-136">Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="eb061-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="eb061-137">Bien qu’un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu’un utilisateur ne souhaite pas l’utiliser et que vous le définissez sur un nombre donné, ou que vos utilisateurs ne se souvenent pas ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="eb061-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="eb061-138">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-139">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="eb061-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="eb061-140">Sous **Audioconférence,** cliquez sur **Réinitialiser** le code confidentiel, puis sur **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="eb061-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="eb061-141">Les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="eb061-141">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="eb061-142">Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, le message de réinitialisation du code confidentiel ne sera pas envoyé et vous de aurez à envoyer manuellement le code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eb061-142">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="eb061-143">Le code confidentiel ne sera affiché qu'après avoir été réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="eb061-143">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="eb061-144">Une fois qu’il s’affiche juste après la réinitialisation, le code confidentiel n’est plus affiché dans les propriétés de l’utilisateur. \*\*\*\*\* s’affiche à la place.</span><span class="sxs-lookup"><span data-stu-id="eb061-144">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="eb061-145">Consultez [réinitialiser le code confidentiel de l’audioconférence.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="eb061-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="eb061-146">Envoyer un courrier électronique avec des informations d’audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="eb061-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="eb061-147">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-148">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="eb061-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="eb061-149">Sous **Audioconférence,** cliquez sur Envoyer les informations sur **la conférence par courrier électronique.**</span><span class="sxs-lookup"><span data-stu-id="eb061-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="eb061-150">Ainsi, le code confidentiel de l’audioconférence n’est pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eb061-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="eb061-151">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="eb061-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="eb061-152">Définir les numéros de téléphone inclus dans les invitations</span><span class="sxs-lookup"><span data-stu-id="eb061-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="eb061-153">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-154">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="eb061-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="eb061-155">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="eb061-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="eb061-156">Dans le **volet Audioconférence,** vous  pouvez définir le numéro gratuit et, si cette est autorisée, **le numéro gratuit.**</span><span class="sxs-lookup"><span data-stu-id="eb061-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="eb061-157">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb061-157">Click **Save**.</span></span>
    
<span data-ttu-id="eb061-158">Consultez [Définir les numéros de téléphone inclus dans les invitations.](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="eb061-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="eb061-159">Choisir les paramètres du pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="eb061-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="eb061-160">**Définir l’expérience de réunion lorsque les appelants participent à une réunion**</span><span class="sxs-lookup"><span data-stu-id="eb061-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="eb061-161">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-162">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="eb061-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="eb061-163">En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.**</span><span class="sxs-lookup"><span data-stu-id="eb061-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="eb061-164">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).</span><span class="sxs-lookup"><span data-stu-id="eb061-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="eb061-165">Cette option est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="eb061-165">This is enabled by default.</span></span> <span data-ttu-id="eb061-166">Si vous désactivez cette option, les utilisateurs qui ont déjà rejoint la réunion par défaut ne seront pas informés de l’arrivée ou du départ des autres personnes.</span><span class="sxs-lookup"><span data-stu-id="eb061-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="eb061-167">Sous Type **d’annonce d’entrée/sortie,** sélectionnez **Sonnerie** **ou Noms ou des numéros de téléphone.**</span><span class="sxs-lookup"><span data-stu-id="eb061-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="eb061-168">Si vous choisissez Noms ou numéros **de téléphone,** vous pouvez également choisir d’activer ou de désactiver l’enregistrement du nom des appelants avant **de rejoindre la réunion.**</span><span class="sxs-lookup"><span data-stu-id="eb061-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="eb061-169">Par défaut, les participants externes ne peuvent pas voir les numéros de téléphone des participants appelés.</span><span class="sxs-lookup"><span data-stu-id="eb061-169">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="eb061-170">Si vous voulez conserver la confidentialité de ces numéros de téléphone, sélectionnez **Tonalités** pour le **type d’annonce d’entrée/sortie** (cela permet d’éviter que les numéros soient lus par les équipes).</span><span class="sxs-lookup"><span data-stu-id="eb061-170">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>


5. <span data-ttu-id="eb061-171">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb061-171">Click **Save**.</span></span>

    
<span data-ttu-id="eb061-172">Reportez-vous à la section [Modifier les paramètres d’un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="eb061-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="eb061-173">**Modifier la longueur du code confidentiel pour les réunions**</span><span class="sxs-lookup"><span data-stu-id="eb061-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="eb061-174">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="eb061-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="eb061-175">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="eb061-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="eb061-176">Dans le volet **Bridge settings** (Paramètres du pont), entrez le nombre de chiffres que vous voulez pour le code confidentiel dans la liste **Longueur du code confidentiel**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb061-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="eb061-177">Le code confidentiel doit comprendre entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="eb061-177">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="eb061-178">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="eb061-178">The default is 5.</span></span>

    
<span data-ttu-id="eb061-179">Reportez-vous à la section [Modifier les paramètres d’un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="eb061-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="eb061-180">**Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs d’audioconférence**</span><span class="sxs-lookup"><span data-stu-id="eb061-180">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="eb061-181">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="eb061-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="eb061-182">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="eb061-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="eb061-183">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Automatically send emails to users if their audio conferencing settings change** (Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres d’audioconférence).</span><span class="sxs-lookup"><span data-stu-id="eb061-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="eb061-184">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb061-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="eb061-185">Vous pouvez aussi envoyer à l’utilisateur un courrier électronique avec les paramètres d’audioconférence, en accédant aux propriétés d’audioconférence de l’utilisateur puis en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="eb061-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="eb061-186">Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.</span><span class="sxs-lookup"><span data-stu-id="eb061-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="eb061-187">Reportez-vous à la section [Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="eb061-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="eb061-188">Afficher et définir la langue principale (par défaut) et les langues secondaires sur un pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="eb061-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="eb061-189">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-189">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-190">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="eb061-190">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="eb061-191">Sélectionnez un numéro de téléphone dans la liste, puis cliquez **sur Modifier.**</span><span class="sxs-lookup"><span data-stu-id="eb061-191">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="eb061-192">Sélectionnez les langues de votre choix sous **Langue par** défaut et **Autres langues (facultatif).**</span><span class="sxs-lookup"><span data-stu-id="eb061-192">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="eb061-193">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb061-193">Click **Save**.</span></span>


<span data-ttu-id="eb061-194">Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="eb061-194">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="eb061-195">Consulter les numéros d’accès pour les conférences audio</span><span class="sxs-lookup"><span data-stu-id="eb061-195">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="eb061-196">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="eb061-196">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb061-197">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="eb061-197">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="eb061-198">Sélectionnez un numéro de téléphone dans la liste, puis cliquez **sur Modifier.**</span><span class="sxs-lookup"><span data-stu-id="eb061-198">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="eb061-199">Depuis cette section, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="eb061-199">Here you can:</span></span>
    
   - <span data-ttu-id="eb061-200">Affichez les numéros de téléphone à utiliser pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="eb061-200">View the phone numbers that are to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="eb061-201">Affichez l’emplacement et la langue principale qui seront utilisés par le attendant automatique de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="eb061-201">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="eb061-202">Consultez [la liste des numéros d’audioconférence.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="eb061-202">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="eb061-203">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="eb061-203">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="eb061-204">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="eb061-204">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="eb061-205">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 avec un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="eb061-205">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="eb061-206">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="eb061-206">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eb061-207">Pourquoi utiliser Microsoft 365 ou PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="eb061-207">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="eb061-208">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb061-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="eb061-209">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="eb061-209">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="eb061-210">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="eb061-210">Related topics</span></span>

[<span data-ttu-id="eb061-211">Gestion des paramètres d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="eb061-211">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


