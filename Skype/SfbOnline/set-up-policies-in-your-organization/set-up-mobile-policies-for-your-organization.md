---
title: Définir des stratégies mobiles pour votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Vous pouvez configurer comment vos utilisateurs se connectent à Skype pour Business Online à l’aide de la Skype pour application de gestion sur des appareils mobiles, tels que d’une fonctionnalité qui permet aux utilisateurs d’émettre et recevoir des appels téléphoniques sur son téléphone mobile à l’aide de leur numéro de téléphone professionnel plutôt que de leur nu téléphone mobile bre. Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.
ms.openlocfilehash: 4e52230ed6f3255b9dbe929086ada6a63cfd66ce
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500580"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="728f3-104">Définir des stratégies mobiles pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="728f3-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="728f3-105">Vous pouvez configurer comment vos utilisateurs se connectent à Skype pour Business Online à l’aide de la Skype pour application de gestion sur des appareils mobiles, tels que d’une fonctionnalité qui permet aux utilisateurs d’émettre et recevoir des appels téléphoniques sur son téléphone mobile à l’aide de leur numéro de téléphone professionnel plutôt que de leur nu téléphone mobile bre.</span><span class="sxs-lookup"><span data-stu-id="728f3-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="728f3-106">Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.</span><span class="sxs-lookup"><span data-stu-id="728f3-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="728f3-107">Paramètres de stratégie mobile peuvent être configurés au niveau de la création d’une stratégie, ou vous pouvez utiliser l’applet de commande **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="728f3-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="728f3-108">Définir vos stratégies mobiles</span><span class="sxs-lookup"><span data-stu-id="728f3-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="728f3-109">Pour tous les paramètres de stratégie mobile dans Skype pour Business Online, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype entreprise centre d’administration**.</span><span class="sxs-lookup"><span data-stu-id="728f3-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="728f3-110">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="728f3-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="728f3-111">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="728f3-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="728f3-112">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="728f3-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="728f3-113">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="728f3-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="728f3-p103">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="728f3-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="728f3-p104">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="728f3-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="728f3-120">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="728f3-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="728f3-121">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="728f3-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="728f3-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="728f3-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="728f3-123">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="728f3-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="728f3-124">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="728f3-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="728f3-125">Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="728f3-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="728f3-126">Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos</span><span class="sxs-lookup"><span data-stu-id="728f3-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="728f3-127">Pour créer une nouvelle stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="728f3-127">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  <span data-ttu-id="728f3-128">Voir plus d’informations sur l’applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="728f3-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="728f3-129">Pour accorder à la nouvelle stratégie que vous avez créée pour tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="728f3-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  <span data-ttu-id="728f3-130">Voir plus d’informations sur l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="728f3-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="728f3-131">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et puis utiliser l’applet de commande[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="728f3-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="728f3-132">Empêcher un utilisateur d'utiliser l'application Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="728f3-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="728f3-133">Pour créer une nouvelle stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="728f3-133">To create a new policy for these settings, run:</span></span>
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  <span data-ttu-id="728f3-134">Voir plus d’informations sur l’applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="728f3-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="728f3-135">Pour autoriser la nouvelle stratégie que vous avez créé à Amos marbre, exécutez :</span><span class="sxs-lookup"><span data-stu-id="728f3-135">To grant the new policy you created to Amos Marble, run:</span></span>  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  <span data-ttu-id="728f3-136">Voir plus d’informations sur l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="728f3-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="728f3-137">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et puis utiliser l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="728f3-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="728f3-138">Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="728f3-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="728f3-139">Pour créer une nouvelle stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="728f3-139">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  <span data-ttu-id="728f3-140">Voir plus d’informations sur l’applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="728f3-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="728f3-141">Pour accorder à la nouvelle stratégie que vous avez créée pour tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="728f3-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  <span data-ttu-id="728f3-142">Voir plus d’informations sur l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="728f3-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="728f3-143">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et puis utiliser l’applet de commande[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="728f3-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="728f3-144">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="728f3-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="728f3-145">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="728f3-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="728f3-146">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="728f3-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="728f3-147">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="728f3-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="728f3-148">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="728f3-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="728f3-149">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="728f3-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="728f3-p106">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="728f3-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="728f3-152">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="728f3-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="728f3-153">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="728f3-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="728f3-154">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="728f3-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="728f3-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="728f3-155">Related topics</span></span>
[<span data-ttu-id="728f3-156">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="728f3-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="728f3-157">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="728f3-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="728f3-158">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="728f3-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="728f3-159">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="728f3-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 