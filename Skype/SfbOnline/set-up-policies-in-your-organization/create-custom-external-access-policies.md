---
title: Créer des stratégies d'accès externe personnalisées
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype Entreprise En ligne vous permet de créer des stratégies d’accès externe supplémentaires. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinie qui peuvent couvrir la plupart des scénarios.
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240143"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="0f157-104">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="0f157-104">Create custom external access policies</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="0f157-105">Skype Entreprise En ligne vous permet de créer des stratégies d’accès externe supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="0f157-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="0f157-106">Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinie qui peuvent couvrir la plupart des scénarios.</span><span class="sxs-lookup"><span data-stu-id="0f157-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="0f157-107">Voici ce qui s’intait :</span><span class="sxs-lookup"><span data-stu-id="0f157-107">These are:</span></span>
  
- <span data-ttu-id="0f157-108">Pas d’accès Skype fédéré ou non _(balise :NoFederationAndPIC)_</span><span class="sxs-lookup"><span data-stu-id="0f157-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="0f157-109">Accès fédéré uniquement (_Balise:FédérationOnly)_</span><span class="sxs-lookup"><span data-stu-id="0f157-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="0f157-110">Accès fédéré et grand public _(FederationAndPICDefault)_</span><span class="sxs-lookup"><span data-stu-id="0f157-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="0f157-111">Les stratégies externes personnalisées vous permettent de créer des polices supplémentaires qui ne sont pas couvertes par les paramètres ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="0f157-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="0f157-112">Lorsque la stratégie a été créée, vous devez définir tous les paramètres requis et vous ne pouvez pas les modifier ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="0f157-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="0f157-113">La création de stratégies personnalisées vous permet de contrôler des fonctionnalités telles que l’accès Skype grand public ou une stratégie de désactivation de l’audio/vidéo cloud public, qui n’était pas couverte par des paramètres prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="0f157-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="0f157-114">Les stratégies d’accès externe personnalisées suivent la même syntaxe que les stratégies de client, de mobilité et de conférence.</span><span class="sxs-lookup"><span data-stu-id="0f157-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="0f157-115">Pour en savoir plus sur ces paramètres, [cliquez ici.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0f157-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="0f157-116">Pour ce faire, l’utilisateur doit utiliser une version prise en charge de l’application « Exécuter en un clic » 2016 Skype Entreprise qui la prend en charge.</span><span class="sxs-lookup"><span data-stu-id="0f157-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="0f157-117">La version minimale suivante du client « Skype Entreprise - Exécuter en un clic 2016 est requise :</span><span class="sxs-lookup"><span data-stu-id="0f157-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="0f157-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="0f157-118">**Type**</span></span>|<span data-ttu-id="0f157-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="0f157-119">**Release date**</span></span>|<span data-ttu-id="0f157-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="0f157-120">**Version**</span></span>|<span data-ttu-id="0f157-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="0f157-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0f157-122">First Release pour Canal actuel</span><span class="sxs-lookup"><span data-stu-id="0f157-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="0f157-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="0f157-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="0f157-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="0f157-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="0f157-125">Version 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="0f157-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="0f157-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="0f157-126">Current Channel</span></span>  <br/> |<span data-ttu-id="0f157-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="0f157-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="0f157-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="0f157-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="0f157-129">Version 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="0f157-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="0f157-130">Canal différé</span><span class="sxs-lookup"><span data-stu-id="0f157-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="0f157-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="0f157-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="0f157-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="0f157-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="0f157-133">Version 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="0f157-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="0f157-134">Les utilisateurs qui utilisent des versions antérieures de Skype Entreprise Windows clients Mac seront toujours en mesure de transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="0f157-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="0f157-135">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f157-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="0f157-136">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="0f157-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="0f157-137">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="0f157-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="0f157-138">Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="0f157-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="0f157-139">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0f157-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="0f157-140">Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0f157-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="0f157-141">Créer une stratégie d’accès externe personnalisée pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="0f157-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="0f157-142">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0f157-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0f157-143">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="0f157-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0f157-144">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="0f157-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0f157-145">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="0f157-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0f157-146">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="0f157-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0f157-147">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0f157-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0f157-148">Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f157-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="0f157-149">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="0f157-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0f157-150">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0f157-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="0f157-151">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0f157-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="0f157-152">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0f157-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0f157-153">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0f157-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="0f157-154">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="0f157-154">Related topics</span></span>
[<span data-ttu-id="0f157-155">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="0f157-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="0f157-156">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="0f157-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="0f157-157">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="0f157-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
