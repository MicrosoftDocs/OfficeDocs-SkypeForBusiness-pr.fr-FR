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
ms.openlocfilehash: 9a2e18ad23eaa08813c87e83058ecc0dcd1dfec1
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569206"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="3623b-103">Configurer les stratégies de conférence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="3623b-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="3623b-104">La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.</span><span class="sxs-lookup"><span data-stu-id="3623b-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="3623b-105">Il est important de garder le contrôle sur les conférences et les paramètres de conférence.</span><span class="sxs-lookup"><span data-stu-id="3623b-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="3623b-106">Dans certains cas, il peut y avoir des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés, peuvent participer aux réunions et enregistrer les diapositives ou les distribuer pendant ces réunions.</span><span class="sxs-lookup"><span data-stu-id="3623b-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="3623b-107">De plus, il peut y avoir des problèmes juridiques occasionnels.</span><span class="sxs-lookup"><span data-stu-id="3623b-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="3623b-108">Par exemple, par défaut, les participants à la réunion sont autorisés à ajouter des annotations sur le contenu partagé. toutefois, ces annotations ne sont pas enregistrées lorsque la réunion est archivée.</span><span class="sxs-lookup"><span data-stu-id="3623b-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="3623b-109">Si votre organisation est tenue de conserver un enregistrement de toutes les communications électroniques, vous pouvez désactiver les annotations.</span><span class="sxs-lookup"><span data-stu-id="3623b-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="3623b-110">Dans Skype Entreprise Online, les conférences sont gérées à l’aide de stratégies de conférence.</span><span class="sxs-lookup"><span data-stu-id="3623b-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="3623b-111">Les stratégies de conférence déterminent les fonctionnalités et fonctions pouvant être utilisées lors d'une conférence, y compris la possibilité, pour la conférence, d'inclure de l'audio et de la vidéo IP à destination du nombre maximum de personnes pouvant participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="3623b-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="3623b-112">Les stratégies de conférence peuvent être configurées à l'échelle globale ou individuelle.</span><span class="sxs-lookup"><span data-stu-id="3623b-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="3623b-113">Les administrateurs bénéficient ainsi d'une très grande souplesse en ce qui concerne les fonctions qu'ils souhaitent mettre à la disposition des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3623b-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="3623b-114">Les paramètres de stratégie peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsConferencingPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="3623b-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="3623b-115">Définir vos stratégies de conférence</span><span class="sxs-lookup"><span data-stu-id="3623b-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="3623b-116">Pour tous les paramètres de stratégie de conférence dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre **d’administration** **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="3623b-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="3623b-117">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3623b-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="3623b-118">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="3623b-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="3623b-119">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="3623b-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="3623b-120">Installez le [module Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="3623b-120">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="3623b-121">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3623b-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="3623b-122">Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3623b-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="3623b-123">Bloquer les transferts de fichiers et le partage de bureau pendant les réunions</span><span class="sxs-lookup"><span data-stu-id="3623b-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="3623b-124">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3623b-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="3623b-125">En savoir plus sur [l’cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="3623b-125">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="3623b-126">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3623b-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="3623b-127">En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="3623b-127">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="3623b-128">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3623b-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="3623b-129">Bloquer l’enregistrement des conférences et empêcher les participants anonymes à la réunion</span><span class="sxs-lookup"><span data-stu-id="3623b-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="3623b-130">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3623b-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="3623b-131">En savoir plus sur [l’cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="3623b-131">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="3623b-132">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3623b-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="3623b-133">En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="3623b-133">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="3623b-134">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3623b-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="3623b-135">Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="3623b-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="3623b-136">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3623b-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="3623b-137">En savoir plus sur [l’cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="3623b-137">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="3623b-138">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3623b-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="3623b-139">En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="3623b-139">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="3623b-140">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3623b-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3623b-141">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="3623b-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="3623b-142">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="3623b-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3623b-143">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="3623b-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3623b-144">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="3623b-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3623b-145">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3623b-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3623b-146">Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="3623b-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3623b-147">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="3623b-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3623b-148">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3623b-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3623b-149">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3623b-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3623b-150">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3623b-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3623b-151">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3623b-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="3623b-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3623b-152">Related topics</span></span>
[<span data-ttu-id="3623b-153">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="3623b-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="3623b-154">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="3623b-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="3623b-155">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="3623b-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
