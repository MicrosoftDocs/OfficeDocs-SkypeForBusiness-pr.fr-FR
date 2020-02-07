---
title: Modifier les paramètres d’un pont d’audioconférence.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
description: 'Découvrez les étapes dont vous avez besoin pour modifier les paramètres d’un pont de conférence qui est utilisé pour inviter les appelants et rassembler des noms et des codes confidentiels pour les organisateurs de la réunion lorsque ces derniers n’utilisent pas les applications Skype entreprise ou Microsoft Teams. '
ms.openlocfilehash: d872bf3d0db2e19089716ab65fc487db601c48ea
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825112"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="9d3b6-103">Modifier les paramètres d’un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="9d3b6-p101">Lorsque vous configurez l’audioconférence dans Office 365, vous recevez des numéros de téléphone pour vos utilisateurs à partir d’un pont de conférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Ces numéros de téléphone permettent aux appelants de se connecter à une réunion. Le numéro de téléphone est inclus en bas de l’invitation à la réunion Skype entreprise ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="9d3b6-p102">Le pont de conférence répond à un appel et invite l’appelant à utiliser les invites vocales à l’aide d’un standard automatique de réunion, puis, en fonction de vos paramètres, il peut lire les notifications, demander aux appelants d’enregistrer leur nom et de contrôler les paramètres de code confidentiel. Des broches sont fournies aux organisateurs de la réunion pour leur permettre de démarrer une réunion lorsqu’elles ne sont pas à l’aide d’une application Skype entreprise ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="9d3b6-p103">Un code confidentiel est requis uniquement pour l’organisateur de la réunion lorsqu’un utilisateur de l’application Skype entreprise ou Microsoft teams n’a pas encore commencé la réunion. Si tout le monde se connecte à la réunion, le code confidentiel est requis pour l’organisateur de la réunion pour démarrer la réunion.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-p103">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](media/teams-logo-30x30.png) <span data-ttu-id="9d3b6-113">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="9d3b6-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9d3b6-114">Dans le volet de navigation de gauche, accédez à **conférences** > **conférences.**</span><span class="sxs-lookup"><span data-stu-id="9d3b6-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="9d3b6-115">Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9d3b6-116">Dans le volet **paramètres du pont** , sélectionnez :</span><span class="sxs-lookup"><span data-stu-id="9d3b6-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="9d3b6-117">**Notifications d’entrée et de sortie de réunion** Si vous désactivez cette fonctionnalité, les utilisateurs qui ont déjà rejoint la réunion ne seront pas avertis lorsqu’une personne entre ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="9d3b6-118">Lorsque vous activez les **notifications d’entrée et de sortie**de la réunion, vous pouvez sélectionner les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d3b6-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="9d3b6-119">**Nom ou numéro de téléphone** Lorsqu’un utilisateur appelle pour rejoindre une réunion, son numéro de téléphone est diffusé lorsqu’il rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="9d3b6-120">**Tonalités** Lorsque des utilisateurs se connectent à une réunion, une sonnerie est diffusée quand ils la rejoignent.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="9d3b6-121">**Demander aux appelants d’enregistrer leur nom avant de participer à la réunion** Si vous désactivez cette fonctionnalité, les appelants ne seront pas invités à enregistrer leur nom avant de participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="9d3b6-122">Pour définir la longueur du code confidentiel pour les réunions, sélectionnez le nombre de chiffres souhaité pour le code confidentiel dans la liste **longueur du code confidentiel** .</span><span class="sxs-lookup"><span data-stu-id="9d3b6-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="9d3b6-123">Pour indiquer si vous souhaitez envoyer des courriers électroniques à vos utilisateurs, activez ou désactivez l' **envoi automatique de messages électroniques aux utilisateurs en cas de modification de la configuration**de votre audioconférence.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="9d3b6-124">Pour plus d’informations, voir [messages électroniques envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence audio sont modifiés dans Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .</span><span class="sxs-lookup"><span data-stu-id="9d3b6-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="9d3b6-125">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-125">Click **Save**.</span></span> 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![Icône illustrant le logo Skype entreprise](media/sfb-logo-30x30.png)  <span data-ttu-id="9d3b6-127">Utilisation du centre d'administration Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="9d3b6-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="9d3b6-128">**Configurer l’interface de réunion lorsque les appelants rejoignent une réunion**</span><span class="sxs-lookup"><span data-stu-id="9d3b6-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="9d3b6-129">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, accédez à**paramètres du pont Microsoft** **Conferencing** > .</span><span class="sxs-lookup"><span data-stu-id="9d3b6-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="9d3b6-130">Dans la page **paramètres du pont Microsoft** , sous **qualité de participation**à une réunion, sélectionnez :</span><span class="sxs-lookup"><span data-stu-id="9d3b6-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="9d3b6-131">**Activer ou désactiver les annonces d'entrée et de sortie des réunions**: cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="9d3b6-132">Si vous désactivez cette case à cocher, les utilisateurs qui ont déjà rejoint la réunion ne seront pas avertis lorsqu’une personne entre ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="9d3b6-133">Lorsque vous sélectionnez **activer ou désactiver les notifications d’entrée et de sortie de la réunion**, vous pouvez sélectionner ces options dans la liste **type d’annonce d’entrée/sortie** :</span><span class="sxs-lookup"><span data-stu-id="9d3b6-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="9d3b6-134">**Nom ou numéro de téléphone** Lorsqu’un utilisateur appelle pour rejoindre une réunion, son numéro de téléphone est diffusé lorsqu’il rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="9d3b6-135">**Tonalités** Lorsque des utilisateurs se connectent à une réunion, une sonnerie est diffusée quand ils la rejoignent.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="9d3b6-136">**Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="9d3b6-137">Si vous désactivez la case à cocher, les appelants ne seront pas invités à enregistrer leur nom avant de participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="9d3b6-138">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="9d3b6-139">**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**</span><span class="sxs-lookup"><span data-stu-id="9d3b6-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="9d3b6-140">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9d3b6-141">Accédez au >  **Centre d’administration Microsoft 365\*\*\*\*Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9d3b6-142">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation gauche, accédez à**paramètres du pont Microsoft** **Conferencing** > .</span><span class="sxs-lookup"><span data-stu-id="9d3b6-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="9d3b6-143">Dans la page **paramètres du pont Microsoft** , sous **sécurité**, entrez le nombre de chiffres souhaités pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9d3b6-144">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="9d3b6-145">**Indiquez si vous souhaitez envoyer un courrier électronique à vos utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="9d3b6-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="9d3b6-146">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9d3b6-147">Accédez au >  **Centre d’administration Microsoft 365\*\*\*\*Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9d3b6-148">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation gauche, accédez à**paramètres du pont Microsoft** **Conferencing** > .</span><span class="sxs-lookup"><span data-stu-id="9d3b6-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="9d3b6-149">Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement les messages électroniques aux utilisateurs en cas de modification de leurs informations de connexion**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="9d3b6-150">Pour plus d’informations, voir [messages électroniques envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence audio sont modifiés dans Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .</span><span class="sxs-lookup"><span data-stu-id="9d3b6-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9d3b6-151">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="9d3b6-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9d3b6-152">Pour gagner du temps ou automatiser le processus, vous pouvez utiliser l’applet de connexion [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .</span><span class="sxs-lookup"><span data-stu-id="9d3b6-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="9d3b6-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d3b6-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9d3b6-156">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d3b6-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9d3b6-157">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d3b6-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="9d3b6-158">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="9d3b6-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9d3b6-159">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d3b6-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="9d3b6-160">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9d3b6-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9d3b6-161">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9d3b6-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9d3b6-162">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9d3b6-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="9d3b6-p109">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="9d3b6-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9d3b6-165">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9d3b6-165">Related topics</span></span>

[<span data-ttu-id="9d3b6-166">Configurer Audioconférence pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d3b6-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="9d3b6-167">Configurer l’audioconférence pour Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9d3b6-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
