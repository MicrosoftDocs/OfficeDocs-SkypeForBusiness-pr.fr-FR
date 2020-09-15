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
description: Skype entreprise Online vous permet de créer des stratégies d’accès externe supplémentaires. Contrairement aux stratégies de client ou de conférence, dans lesquelles vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinies qui peuvent couvrir la plupart des scénarios.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814193"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="de58e-104">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="de58e-104">Create custom external access policies</span></span>

<span data-ttu-id="de58e-105">Skype entreprise Online vous permet de créer des stratégies d’accès externe supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="de58e-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="de58e-106">Contrairement aux stratégies de client ou de conférence, dans lesquelles vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinies qui peuvent couvrir la plupart des scénarios.</span><span class="sxs-lookup"><span data-stu-id="de58e-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="de58e-107">Il s’agit des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="de58e-107">These are:</span></span>
  
- <span data-ttu-id="de58e-108">Aucun accès public fédéré ou Skype (_balise : NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="de58e-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="de58e-109">Accès fédéré uniquement (_balise : FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="de58e-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="de58e-110">Accès fédéré et au grand public (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="de58e-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="de58e-111">Les stratégies externes personnalisées vous permettent de créer des stratégies supplémentaires qui ne sont pas couvertes par les paramètres ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="de58e-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="de58e-112">Lorsque la stratégie a été créée, vous devez définir tous les paramètres requis et ne pouvez pas les modifier plus tard.</span><span class="sxs-lookup"><span data-stu-id="de58e-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="de58e-113">La création de stratégies personnalisées vous permet de contrôler les fonctionnalités telles que l’accès au grand public Skype ou une stratégie de désactivation de l’audio et de la vidéo dans le cloud public, qui n’était pas couvert par des paramètres prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="de58e-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="de58e-114">Les stratégies d’accès externe personnalisé suivent la même syntaxe que les stratégies de client, de mobilité et de conférence.</span><span class="sxs-lookup"><span data-stu-id="de58e-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="de58e-115">Vous pouvez en savoir plus sur [ces paramètres.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="de58e-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="de58e-116">Pour ce faire, l’utilisateur doit utiliser une version prise en charge d' 2016 de l’application Skype entreprise pour une utilisation compatible.</span><span class="sxs-lookup"><span data-stu-id="de58e-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="de58e-117">La version minimum suivante du client « démarrer en un clic » Skype entreprise 2016 est requise :</span><span class="sxs-lookup"><span data-stu-id="de58e-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="de58e-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="de58e-118">**Type**</span></span>|<span data-ttu-id="de58e-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="de58e-119">**Release date**</span></span>|<span data-ttu-id="de58e-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="de58e-120">**Version**</span></span>|<span data-ttu-id="de58e-121">**Appui**</span><span class="sxs-lookup"><span data-stu-id="de58e-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de58e-122">First Release pour canal actuel</span><span class="sxs-lookup"><span data-stu-id="de58e-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="de58e-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="de58e-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="de58e-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="de58e-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="de58e-125">Version 1611 (Build 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="de58e-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="de58e-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="de58e-126">Current Channel</span></span>  <br/> |<span data-ttu-id="de58e-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="de58e-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="de58e-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="de58e-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="de58e-129">Version 1611 (Build 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="de58e-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="de58e-130">Canal différé</span><span class="sxs-lookup"><span data-stu-id="de58e-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="de58e-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="de58e-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="de58e-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="de58e-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="de58e-133">Version 1609 (Build 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="de58e-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="de58e-134">Les utilisateurs qui utilisent des versions plus anciennes de Skype entreprise Windows ou les clients Mac pourront toujours transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="de58e-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="de58e-135">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de58e-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="de58e-136">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="de58e-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="de58e-137">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="de58e-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="de58e-138">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="de58e-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="de58e-139">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de58e-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="de58e-140">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://www.microsoft.com/download/details.aspx?id=40855) .</span><span class="sxs-lookup"><span data-stu-id="de58e-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="de58e-141">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="de58e-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="de58e-142">Vous devrez également installer le module Windows PowerShell pour les équipes qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="de58e-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="de58e-143">Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="de58e-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="de58e-144">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="de58e-144">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="de58e-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="de58e-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="de58e-146">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="de58e-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="de58e-147">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="de58e-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="de58e-148">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="de58e-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business  Online Connector.</span></span>

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="de58e-149">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="de58e-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="de58e-150">Créer une stratégie d’accès externe personnalisée pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="de58e-150">Create a custom external access policy for a user</span></span>

<span data-ttu-id="de58e-151">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="de58e-151">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="de58e-152">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="de58e-152">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="de58e-153">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="de58e-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="de58e-154">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="de58e-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="de58e-155">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="de58e-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="de58e-156">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="de58e-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="de58e-157">Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="de58e-157">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="de58e-158">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="de58e-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="de58e-159">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="de58e-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="de58e-160">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de58e-160">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="de58e-161">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="de58e-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="de58e-162">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="de58e-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="de58e-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de58e-163">Related topics</span></span>
[<span data-ttu-id="de58e-164">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="de58e-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="de58e-165">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="de58e-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="de58e-166">Configuration des stratégies de conférence au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="de58e-166">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
