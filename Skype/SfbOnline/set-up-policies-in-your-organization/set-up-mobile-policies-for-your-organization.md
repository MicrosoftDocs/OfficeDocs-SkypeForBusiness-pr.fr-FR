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
description: Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui leur permet d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile. Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.
ms.openlocfilehash: e29a02bddcb9ace29ebd059f8cbc42c5a85c3f12
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240066"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="3421d-104">Configurer les stratégies mobiles pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="3421d-104">Set up mobile policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="3421d-105">Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui leur permet d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="3421d-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="3421d-106">Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.</span><span class="sxs-lookup"><span data-stu-id="3421d-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="3421d-107">Les paramètres de stratégie mobile peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="3421d-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="3421d-108">Définir vos stratégies mobiles</span><span class="sxs-lookup"><span data-stu-id="3421d-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="3421d-109">Pour tous les paramètres de stratégie mobile dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous ne pouvez pas utiliser le Centre **d’administration** **Skype Entreprise'**</span><span class="sxs-lookup"><span data-stu-id="3421d-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="3421d-110">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3421d-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="3421d-111">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="3421d-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="3421d-112">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="3421d-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="3421d-113">Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="3421d-113">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="3421d-114">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3421d-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="3421d-115">Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3421d-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="3421d-116">Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos</span><span class="sxs-lookup"><span data-stu-id="3421d-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="3421d-117">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3421d-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="3421d-118">En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="3421d-118">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="3421d-119">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3421d-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="3421d-120">En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="3421d-120">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="3421d-121">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3421d-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="3421d-122">Empêcher un utilisateur d'utiliser l'application Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="3421d-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="3421d-123">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3421d-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="3421d-124">En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="3421d-124">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="3421d-125">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3421d-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="3421d-126">En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="3421d-126">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="3421d-127">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3421d-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="3421d-128">Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="3421d-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="3421d-129">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3421d-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="3421d-130">En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="3421d-130">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="3421d-131">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3421d-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="3421d-132">En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="3421d-132">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
<span data-ttu-id="3421d-133">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) pour appliquer le paramètre à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3421d-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3421d-134">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="3421d-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="3421d-135">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="3421d-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3421d-136">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="3421d-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3421d-137">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="3421d-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3421d-138">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3421d-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="3421d-139">Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365 ou des Office 365</span><span class="sxs-lookup"><span data-stu-id="3421d-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="3421d-140">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="3421d-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3421d-141">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3421d-141">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="3421d-142">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="3421d-142">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="3421d-143">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3421d-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="3421d-144">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3421d-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="3421d-145">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="3421d-145">Related topics</span></span>
[<span data-ttu-id="3421d-146">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="3421d-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="3421d-147">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="3421d-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="3421d-148">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="3421d-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="3421d-149">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="3421d-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
