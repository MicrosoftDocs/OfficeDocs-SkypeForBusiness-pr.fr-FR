---
title: Configurer les stratégies de conférence pour votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer."
ms.openlocfilehash: 7e53f03a78b1e018323540daa22f8b4af72fb0ac
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373116"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="da717-103">Configurer les stratégies de conférence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="da717-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="da717-104">La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.</span><span class="sxs-lookup"><span data-stu-id="da717-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="da717-p101">Il est important que vous permet de contrôler les conférences et leurs paramètres. Dans certains cas, peuvent poser des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés permettre participer aux réunions et enregistrer des diapositives ou documents distribués durant ces dernières. En outre, il peut y avoir des implications juridiques. Par exemple, par défaut, les participants à la réunion sont autorisés à annoter le contenu partagé ; Toutefois, ces annotations ne sont pas enregistrées lors de la réunion est archivée. Si votre organisation est obligée de conserver un enregistrement de toutes les communications électroniques, vous souhaitez désactiver les annotations.</span><span class="sxs-lookup"><span data-stu-id="da717-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="da717-p102">Dans Skype pour Business Online, les conférences sont gérées à l’aide de stratégies de conférence. Stratégies de conférence déterminent les fonctionnalités qui peuvent être utilisées dans une conférence, y compris tout ou non la conférence peut inclure IP audio et vidéo pour le nombre maximal de personnes qui peuvent participer à une réunion. Stratégies de conférence peuvent être configurées au niveau global ou au niveau de l’étendue par utilisateur. Les administrateurs disposent ainsi d’une flexibilité considérable quand il s’agit de déterminer quelles possibilités seront disponibles pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="da717-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="da717-114">Paramètres de stratégie peuvent être configurées au niveau de la création d’une stratégie, ou vous pouvez utiliser l’applet de commande **Set-CsConferencingPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="da717-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="da717-115">Définir vos stratégies de conférence</span><span class="sxs-lookup"><span data-stu-id="da717-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="da717-116">Pour tous les paramètres de stratégie de conférence dans Skype pour Business Online, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype entreprise centre d’administration**.</span><span class="sxs-lookup"><span data-stu-id="da717-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="da717-117">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da717-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="da717-118">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="da717-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="da717-119">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="da717-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="da717-120">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="da717-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="da717-p103">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="da717-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="da717-p104">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="da717-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="da717-127">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="da717-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="da717-128">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="da717-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="da717-129">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="da717-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="da717-130">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="da717-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da717-131">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="da717-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="da717-132">Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="da717-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="da717-133">Bloquer les transferts de fichiers et le partage de bureau pendant les réunions</span><span class="sxs-lookup"><span data-stu-id="da717-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="da717-134">Pour créer une nouvelle stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="da717-134">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  > ```
  > <span data-ttu-id="da717-135">Voir plus d’informations sur l’applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="da717-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="da717-136">Pour accorder à la nouvelle stratégie que vous avez créée pour tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="da717-136">To grant the new policy you created to all users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  > ```
  > <span data-ttu-id="da717-137">Voir plus d’informations sur l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="da717-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="da717-138">Si vous avez déjà créé une stratégie, vous pourrez utiliser l’applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utilisez l’applet de commande[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="da717-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="da717-139">Bloquer l’enregistrement des conférences et empêcher des participants à la réunion anonyme</span><span class="sxs-lookup"><span data-stu-id="da717-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="da717-140">Pour créer une nouvelle stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="da717-140">To create a new policy for these settings, run:</span></span> 
  > 
  > ```
  > New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  > ```
  > <span data-ttu-id="da717-141">Voir plus d’informations sur l’applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="da717-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="da717-142">Pour autoriser la nouvelle stratégie que vous avez créé à Amos marbre, exécutez :</span><span class="sxs-lookup"><span data-stu-id="da717-142">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```
  >  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  > ```
  > <span data-ttu-id="da717-143">Voir plus d’informations sur l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="da717-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="da717-144">Si vous avez déjà créé une stratégie, vous pourrez utiliser l’applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utilisez l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="da717-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="da717-145">Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="da717-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="da717-146">Pour créer une nouvelle stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="da717-146">To create a new policy for these settings, run:</span></span>  
  > 
  > ```
  > New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  > ```
  > <span data-ttu-id="da717-147">Voir plus d’informations sur l’applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="da717-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="da717-148">Pour accorder à la nouvelle stratégie que vous avez créée pour tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="da717-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
>   ```

<span data-ttu-id="da717-149">Voir plus d’informations sur l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="da717-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="da717-150">Si vous avez déjà créé une stratégie, vous pourrez utiliser l’applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utilisez l’applet de commande[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="da717-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="da717-151">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="da717-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="da717-152">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="da717-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="da717-153">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="da717-153">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="da717-154">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="da717-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="da717-155">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="da717-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="da717-156">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="da717-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="da717-p106">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="da717-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="da717-159">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da717-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="da717-160">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="da717-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="da717-161">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="da717-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="da717-162">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="da717-162">Related topics</span></span>
[<span data-ttu-id="da717-163">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="da717-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="da717-164">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="da717-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="da717-165">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="da717-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 