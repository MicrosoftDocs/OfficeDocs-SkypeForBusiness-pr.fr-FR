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
ms.openlocfilehash: 65a346f0f16892d5995b723431fc796e3faa1a3b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569226"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="472d6-103">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="472d6-103">Set up client policies for your organization</span></span>

<span data-ttu-id="472d6-104">Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="472d6-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="472d6-105">Les paramètres de stratégie de client peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsClientPolicy** pour modifier les paramètres d’une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="472d6-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="472d6-106">Définir vos stratégies de client</span><span class="sxs-lookup"><span data-stu-id="472d6-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="472d6-107">Pour tous les paramètres de stratégie de client dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre **d’administration** **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="472d6-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="472d6-108">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="472d6-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="472d6-109">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="472d6-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="472d6-110">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="472d6-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="472d6-111">Installez le [module Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="472d6-111">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="472d6-112">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="472d6-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="472d6-113">Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="472d6-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="472d6-114">Désactiver les émoticônes et des notifications de présence et empêcher l’enregistrement des messages instantanés</span><span class="sxs-lookup"><span data-stu-id="472d6-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="472d6-115">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="472d6-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="472d6-116">En savoir plus sur [l’cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="472d6-116">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="472d6-117">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="472d6-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="472d6-118">En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="472d6-118">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="472d6-119">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="472d6-119">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="472d6-120">Activer l'interactivité des URL ou des liens hypertextes dans les messages instantanés</span><span class="sxs-lookup"><span data-stu-id="472d6-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="472d6-121">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="472d6-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="472d6-122">En savoir plus sur [l’cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="472d6-122">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="472d6-123">Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="472d6-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="472d6-124">En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="472d6-124">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="472d6-125">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="472d6-125">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="472d6-126">Bloquer l'affichage des contacts récents</span><span class="sxs-lookup"><span data-stu-id="472d6-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="472d6-127">Pour créer une stratégie pour ces paramètres, exécutez :</span><span class="sxs-lookup"><span data-stu-id="472d6-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="472d6-128">En savoir plus sur [l’cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="472d6-128">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="472d6-129">Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="472d6-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="472d6-130">En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="472d6-130">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="472d6-131">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="472d6-131">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="472d6-132">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="472d6-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="472d6-133">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="472d6-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="472d6-134">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="472d6-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="472d6-135">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="472d6-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="472d6-136">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="472d6-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="472d6-137">Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="472d6-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="472d6-138">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="472d6-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="472d6-139">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="472d6-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="472d6-140">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="472d6-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="472d6-141">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="472d6-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="472d6-142">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="472d6-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="472d6-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="472d6-143">Related topics</span></span>
[<span data-ttu-id="472d6-144">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="472d6-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="472d6-145">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="472d6-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="472d6-146">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="472d6-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
