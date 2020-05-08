---
title: Configurer les stratégies mobiles pour votre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype entreprise Online à l’aide de l’application Skype entreprise sur les appareils mobiles, par exemple une fonctionnalité qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone professionnel plutôt que leur numéro de téléphone mobile. Les stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lors de la création ou de la réception d’appels.
ms.openlocfilehash: cfd9232943aebc9e4565b0ebfe1b46872c4bad65
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164843"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="0eed5-104">Configurer les stratégies mobiles pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="0eed5-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="0eed5-p102">Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype entreprise Online à l’aide de l’application Skype entreprise sur les appareils mobiles, par exemple une fonctionnalité qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone professionnel plutôt que leur numéro de téléphone mobile. Les stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lors de la création ou de la réception d’appels.</span><span class="sxs-lookup"><span data-stu-id="0eed5-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="0eed5-107">Vous pouvez configurer les paramètres de stratégie mobile lors de la création d’une stratégie ou utiliser l’applet de connexion **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="0eed5-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="0eed5-108">Définir vos stratégies mobiles</span><span class="sxs-lookup"><span data-stu-id="0eed5-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="0eed5-109">Pour tous les paramètres de stratégie mobile dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="0eed5-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="0eed5-110">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0eed5-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="0eed5-111">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0eed5-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="0eed5-112">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0eed5-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="0eed5-113">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0eed5-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="0eed5-p103">Si vous n’avez pas la version 3,0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="0eed5-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="0eed5-p104">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="0eed5-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="0eed5-120">Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="0eed5-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="0eed5-121">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0eed5-121">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="0eed5-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0eed5-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="0eed5-123">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="0eed5-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="0eed5-124">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="0eed5-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="0eed5-125">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0eed5-125">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="0eed5-126">Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos</span><span class="sxs-lookup"><span data-stu-id="0eed5-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="0eed5-127">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0eed5-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="0eed5-128">En savoir plus sur l’applet de [nouvelle cmdlet New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0eed5-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0eed5-129">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0eed5-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="0eed5-130">En savoir plus sur l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0eed5-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="0eed5-131">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0eed5-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="0eed5-132">Empêcher un utilisateur d'utiliser l'application Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="0eed5-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="0eed5-133">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0eed5-133">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="0eed5-134">En savoir plus sur l’applet de [nouvelle cmdlet New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0eed5-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0eed5-135">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0eed5-135">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="0eed5-136">En savoir plus sur l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0eed5-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="0eed5-137">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0eed5-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="0eed5-138">Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="0eed5-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="0eed5-139">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0eed5-139">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="0eed5-140">En savoir plus sur l’applet de [nouvelle cmdlet New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0eed5-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0eed5-141">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0eed5-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="0eed5-142">En savoir plus sur l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0eed5-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0eed5-143">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0eed5-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0eed5-144">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="0eed5-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0eed5-145">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="0eed5-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0eed5-146">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="0eed5-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0eed5-147">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="0eed5-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0eed5-148">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0eed5-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0eed5-149">Six raisons d’utiliser Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="0eed5-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0eed5-150">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="0eed5-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0eed5-151">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0eed5-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0eed5-152">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0eed5-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0eed5-153">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0eed5-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0eed5-154">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0eed5-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="0eed5-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0eed5-155">Related topics</span></span>
[<span data-ttu-id="0eed5-156">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="0eed5-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="0eed5-157">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="0eed5-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="0eed5-158">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="0eed5-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="0eed5-159">Configuration des stratégies de conférence au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="0eed5-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
