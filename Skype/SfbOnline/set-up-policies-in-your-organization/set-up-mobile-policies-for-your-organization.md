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
description: Vous pouvez configurer la façon dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui permet aux utilisateurs d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile. Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.
ms.openlocfilehash: 36162c64490edf58bbfac5c7022bebf6f39595ca
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569196"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="be3f6-104">Configurer les stratégies mobiles pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="be3f6-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="be3f6-105">Vous pouvez configurer la façon dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui permet aux utilisateurs d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="be3f6-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="be3f6-106">Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.</span><span class="sxs-lookup"><span data-stu-id="be3f6-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="be3f6-107">Les paramètres de stratégie mobile peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="be3f6-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="be3f6-108">Définir vos stratégies mobiles</span><span class="sxs-lookup"><span data-stu-id="be3f6-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="be3f6-109">Pour tous les paramètres de stratégie mobile dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre **d’administration** **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="be3f6-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="be3f6-110">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be3f6-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="be3f6-111">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="be3f6-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="be3f6-112">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="be3f6-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="be3f6-113">Installez le [module Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="be3f6-113">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="be3f6-114">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="be3f6-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="be3f6-115">Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="be3f6-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="be3f6-116">Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos</span><span class="sxs-lookup"><span data-stu-id="be3f6-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="be3f6-117">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="be3f6-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="be3f6-118">En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="be3f6-118">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="be3f6-119">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="be3f6-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="be3f6-120">En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="be3f6-120">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="be3f6-121">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="be3f6-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="be3f6-122">Empêcher un utilisateur d'utiliser l'application Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="be3f6-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="be3f6-123">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="be3f6-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="be3f6-124">En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="be3f6-124">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="be3f6-125">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="be3f6-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="be3f6-126">En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="be3f6-126">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="be3f6-127">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="be3f6-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="be3f6-128">Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="be3f6-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="be3f6-129">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="be3f6-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="be3f6-130">En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="be3f6-130">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="be3f6-131">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="be3f6-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="be3f6-132">En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="be3f6-132">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="be3f6-133">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="be3f6-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="be3f6-134">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="be3f6-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="be3f6-135">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="be3f6-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="be3f6-136">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="be3f6-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="be3f6-137">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="be3f6-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="be3f6-138">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="be3f6-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="be3f6-139">Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="be3f6-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="be3f6-140">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="be3f6-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="be3f6-141">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="be3f6-141">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="be3f6-142">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be3f6-142">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="be3f6-143">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="be3f6-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="be3f6-144">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="be3f6-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="be3f6-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be3f6-145">Related topics</span></span>
[<span data-ttu-id="be3f6-146">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="be3f6-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="be3f6-147">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="be3f6-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="be3f6-148">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="be3f6-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="be3f6-149">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="be3f6-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
