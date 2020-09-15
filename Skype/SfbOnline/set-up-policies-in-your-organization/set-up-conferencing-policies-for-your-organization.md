---
title: Configurer les stratégies de conférence pour votre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: "La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer."
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814753"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="cc437-103">Configurer les stratégies de conférence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="cc437-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="cc437-104">La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.</span><span class="sxs-lookup"><span data-stu-id="cc437-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="cc437-p101">Il est important de garder le contrôle sur les conférences et les paramètres de conférence. Dans certains cas, il peut y avoir des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés, peut participer aux réunions et enregistrer les diapositives ou documents distribuées lors de ces réunions. Par ailleurs, il peut y avoir des problèmes légaux occasionnels. Par exemple, les participants à la réunion peuvent par défaut faire des annotations sur le contenu partagé. Toutefois, ces annotations ne sont pas enregistrées lors de l’archivage de la réunion. Si votre organisation est tenue de conserver une trace de toutes les communications électroniques, il peut être préférable de désactiver les annotations.</span><span class="sxs-lookup"><span data-stu-id="cc437-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="cc437-p102">Dans Skype entreprise Online, les conférences sont gérées à l’aide de stratégies de conférence. Les stratégies de conférence déterminent les fonctionnalités qui peuvent être utilisées dans une conférence, y compris le nombre de fois que la Conférence peut inclure les appels audio et vidéo IP vers le nombre maximal de personnes qui peuvent participer à une réunion. Les stratégies de conférence peuvent être configurées au niveau de l’étendue globale ou par utilisateur. Cela fournit aux administrateurs une souplesse énorme pour décider quelles fonctionnalités seront mises à la disposition des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc437-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="cc437-114">Vous pouvez configurer les paramètres de stratégie lors de la création d’une stratégie ou utiliser l’applet de connexion **Set-CsConferencingPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="cc437-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="cc437-115">Définir vos stratégies de conférence</span><span class="sxs-lookup"><span data-stu-id="cc437-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="cc437-116">Pour tous les paramètres de stratégie de conférence dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="cc437-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="cc437-117">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc437-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="cc437-118">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cc437-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="cc437-119">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="cc437-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="cc437-120">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="cc437-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="cc437-p103">Si vous n’avez pas la version 3,0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="cc437-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="cc437-124">Vous devrez également installer le module Windows PowerShell pour les équipes qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="cc437-124">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="cc437-125">Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="cc437-125">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="cc437-126">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cc437-126">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="cc437-127">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="cc437-127">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="cc437-128">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="cc437-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
     > [!NOTE]
     > <span data-ttu-id="cc437-129">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="cc437-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
     >
     > <span data-ttu-id="cc437-130">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="cc437-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="cc437-131">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cc437-131">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="cc437-132">Bloquer les transferts de fichiers et le partage de bureau pendant les réunions</span><span class="sxs-lookup"><span data-stu-id="cc437-132">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="cc437-133">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cc437-133">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="cc437-134">En savoir plus sur l’applet de [nouvelle cmdlet New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cc437-134">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="cc437-135">Pour permettre à tous les utilisateurs de votre organisation d’avoir la nouvelle stratégie créée, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cc437-135">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="cc437-136">En savoir plus sur l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cc437-136">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="cc437-137">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc437-137">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="cc437-138">Bloquer l’enregistrement des conférences et les participants aux réunions anonymes</span><span class="sxs-lookup"><span data-stu-id="cc437-138">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="cc437-139">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cc437-139">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="cc437-140">En savoir plus sur l’applet de [nouvelle cmdlet New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cc437-140">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="cc437-141">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cc437-141">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="cc437-142">En savoir plus sur l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cc437-142">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="cc437-143">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc437-143">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="cc437-144">Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="cc437-144">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="cc437-145">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cc437-145">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="cc437-146">En savoir plus sur l’applet de [nouvelle cmdlet New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cc437-146">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="cc437-147">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cc437-147">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="cc437-148">En savoir plus sur l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cc437-148">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="cc437-149">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc437-149">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="cc437-150">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="cc437-150">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="cc437-151">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="cc437-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="cc437-152">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="cc437-152">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="cc437-153">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="cc437-153">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cc437-154">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc437-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="cc437-155">Six raisons d’utiliser Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="cc437-155">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="cc437-156">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="cc437-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="cc437-157">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="cc437-157">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="cc437-158">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc437-158">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="cc437-159">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc437-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cc437-160">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc437-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="cc437-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc437-161">Related topics</span></span>
[<span data-ttu-id="cc437-162">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="cc437-162">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="cc437-163">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="cc437-163">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="cc437-164">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="cc437-164">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
