---
title: Configurer les stratégies client pour votre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814353"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="50f78-103">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="50f78-103">Set up client policies for your organization</span></span>

<span data-ttu-id="50f78-104">Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50f78-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="50f78-105">Vous pouvez configurer les paramètres de stratégie de client lors de la création d’une stratégie ou utiliser l’applet de connexion **Set-CsClientPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="50f78-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="50f78-106">Définir vos stratégies de client</span><span class="sxs-lookup"><span data-stu-id="50f78-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="50f78-107">Pour tous les paramètres de stratégie de client dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="50f78-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="50f78-108">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50f78-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="50f78-109">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="50f78-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="50f78-110">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="50f78-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="50f78-111">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="50f78-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="50f78-p101">Si vous n’avez pas la version 3,0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="50f78-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="50f78-115">Vous devrez également installer le module Windows PowerShell pour les équipes qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="50f78-115">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="50f78-116">Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="50f78-116">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="50f78-117">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="50f78-117">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="50f78-118">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="50f78-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="50f78-119">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="50f78-119">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50f78-120">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="50f78-120">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="50f78-121">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="50f78-121">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
<span data-ttu-id="50f78-122">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="50f78-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="50f78-123">Désactiver les émoticônes et des notifications de présence et empêcher l’enregistrement des messages instantanés</span><span class="sxs-lookup"><span data-stu-id="50f78-123">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="50f78-124">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="50f78-124">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="50f78-125">En savoir plus sur l’applet de [nouvelle cmdlet New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="50f78-125">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="50f78-126">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="50f78-126">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="50f78-127">En savoir plus sur l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="50f78-127">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="50f78-128">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50f78-128">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="50f78-129">Activer l'interactivité des URL ou des liens hypertextes dans les messages instantanés</span><span class="sxs-lookup"><span data-stu-id="50f78-129">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="50f78-130">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="50f78-130">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="50f78-131">En savoir plus sur l’applet de [nouvelle cmdlet New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="50f78-131">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="50f78-132">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="50f78-132">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="50f78-133">En savoir plus sur l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="50f78-133">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="50f78-134">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50f78-134">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="50f78-135">Bloquer l'affichage des contacts récents</span><span class="sxs-lookup"><span data-stu-id="50f78-135">Prevent showing recent contacts</span></span>

- <span data-ttu-id="50f78-136">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="50f78-136">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="50f78-137">En savoir plus sur l’applet de [nouvelle cmdlet New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="50f78-137">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="50f78-138">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="50f78-138">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="50f78-139">En savoir plus sur l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="50f78-139">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="50f78-140">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50f78-140">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="50f78-141">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="50f78-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="50f78-142">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="50f78-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="50f78-143">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="50f78-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="50f78-144">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="50f78-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="50f78-145">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="50f78-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="50f78-146">Six raisons d’utiliser Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="50f78-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="50f78-147">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="50f78-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="50f78-148">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="50f78-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="50f78-149">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50f78-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="50f78-150">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="50f78-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="50f78-151">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="50f78-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="50f78-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50f78-152">Related topics</span></span>
[<span data-ttu-id="50f78-153">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="50f78-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="50f78-154">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="50f78-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="50f78-155">Configuration des stratégies de conférence au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="50f78-155">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
