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
ms.openlocfilehash: 59bc9ab406d530bc09803b61cfc4341617dc911d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240086"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="95783-103">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="95783-103">Set up client policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="95783-104">Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="95783-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="95783-105">Les paramètres de stratégie de client peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsClientPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="95783-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="95783-106">Définir vos stratégies de client</span><span class="sxs-lookup"><span data-stu-id="95783-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="95783-107">Pour tous les paramètres de stratégie client dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous ne pouvez pas utiliser le **Centre Skype Entreprise d’administration.** </span><span class="sxs-lookup"><span data-stu-id="95783-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="95783-108">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95783-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="95783-109">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="95783-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="95783-110">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="95783-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="95783-111">Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="95783-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="95783-112">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="95783-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="95783-113">Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="95783-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="95783-114">Désactiver les émoticônes et des notifications de présence et empêcher l’enregistrement des messages instantanés</span><span class="sxs-lookup"><span data-stu-id="95783-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="95783-115">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="95783-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="95783-116">En savoir plus sur [l’cmdlet New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="95783-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="95783-117">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="95783-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="95783-118">En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="95783-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="95783-119">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="95783-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="95783-120">Activer l'interactivité des URL ou des liens hypertextes dans les messages instantanés</span><span class="sxs-lookup"><span data-stu-id="95783-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="95783-121">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="95783-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="95783-122">En savoir plus sur [l’cmdlet New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="95783-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="95783-123">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="95783-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="95783-124">En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="95783-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="95783-125">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="95783-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="95783-126">Bloquer l'affichage des contacts récents</span><span class="sxs-lookup"><span data-stu-id="95783-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="95783-127">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="95783-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="95783-128">En savoir plus sur [l’cmdlet New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="95783-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="95783-129">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="95783-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="95783-130">En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="95783-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="95783-131">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="95783-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="95783-132">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="95783-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="95783-133">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="95783-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="95783-134">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="95783-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="95783-135">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="95783-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="95783-136">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="95783-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="95783-137">Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365 ou des Office 365</span><span class="sxs-lookup"><span data-stu-id="95783-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="95783-138">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="95783-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="95783-139">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="95783-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="95783-140">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="95783-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="95783-141">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="95783-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="95783-142">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="95783-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="95783-143">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="95783-143">Related topics</span></span>
[<span data-ttu-id="95783-144">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="95783-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="95783-145">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="95783-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="95783-146">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="95783-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
