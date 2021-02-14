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
description: Skype Entreprise Online vous permet de créer des stratégies d’accès externe supplémentaires. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinie qui peuvent couvrir la plupart des scénarios.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814193"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="b3b1a-104">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="b3b1a-104">Create custom external access policies</span></span>

<span data-ttu-id="b3b1a-105">Skype Entreprise Online vous permet de créer des stratégies d’accès externe supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="b3b1a-106">Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinie qui peuvent couvrir la plupart des scénarios.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="b3b1a-107">Voici ce qui s’intait :</span><span class="sxs-lookup"><span data-stu-id="b3b1a-107">These are:</span></span>
  
- <span data-ttu-id="b3b1a-108">Pas d’accès fédéré ou skype grand public (_balise :NoFederationAndPIC)_</span><span class="sxs-lookup"><span data-stu-id="b3b1a-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="b3b1a-109">Accès fédéré uniquement (_Balise:FédérationOnly)_</span><span class="sxs-lookup"><span data-stu-id="b3b1a-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="b3b1a-110">Accès fédéré et grand public _(FederationAndPICDefault)_</span><span class="sxs-lookup"><span data-stu-id="b3b1a-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="b3b1a-111">Les stratégies externes personnalisées vous permettent de créer des polices supplémentaires qui ne sont pas couvertes par les paramètres ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="b3b1a-112">Lorsque la stratégie a été créée, vous devez définir tous les paramètres requis et vous n’avez pas pu les modifier ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="b3b1a-113">La création de stratégies personnalisées vous permet de contrôler des fonctionnalités telles que l’accès grand public à Skype ou une stratégie de désactivation de l’audio/vidéo dans le cloud public, ce qui n’était pas couvert par les paramètres prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="b3b1a-114">Les stratégies d’accès externe personnalisées suivent la même syntaxe que les stratégies de client, de mobilité et de conférence.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="b3b1a-115">Pour en savoir plus sur ces paramètres, [cliquez ici.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3b1a-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="b3b1a-116">Pour que cela fonctionne, l’utilisateur doit utiliser une version prise en charge de l’application Skype Entreprise « Exécuter en un clic » 2016 qui la prend en charge.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="b3b1a-117">La version minimale suivante du client Skype Entreprise 2016 « Click-to-Run ) est requise :</span><span class="sxs-lookup"><span data-stu-id="b3b1a-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="b3b1a-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3b1a-118">**Type**</span></span>|<span data-ttu-id="b3b1a-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="b3b1a-119">**Release date**</span></span>|<span data-ttu-id="b3b1a-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="b3b1a-120">**Version**</span></span>|<span data-ttu-id="b3b1a-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="b3b1a-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3b1a-122">First Release pour Canal actuel</span><span class="sxs-lookup"><span data-stu-id="b3b1a-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="b3b1a-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="b3b1a-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="b3b1a-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="b3b1a-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="b3b1a-125">Version 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="b3b1a-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="b3b1a-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="b3b1a-126">Current Channel</span></span>  <br/> |<span data-ttu-id="b3b1a-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="b3b1a-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="b3b1a-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="b3b1a-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="b3b1a-129">Version 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="b3b1a-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="b3b1a-130">Canal différé</span><span class="sxs-lookup"><span data-stu-id="b3b1a-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="b3b1a-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="b3b1a-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="b3b1a-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="b3b1a-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="b3b1a-133">Version 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="b3b1a-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="b3b1a-134">Les utilisateurs qui utilisent des versions antérieures des applications Windows skype Entreprise ou des clients Mac pourront toujours transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="b3b1a-135">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3b1a-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="b3b1a-136">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b3b1a-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="b3b1a-137">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b3b1a-138">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="b3b1a-139">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="b3b1a-140">Voir [Windows Management Framework 4.0 pour](https://www.microsoft.com/download/details.aspx?id=40855) télécharger et mettre à jour Windows PowerShell vers la version 4.0.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="b3b1a-141">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="b3b1a-142">Vous devrez également installer le module Windows PowerShell teams qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="b3b1a-143">Pour en savoir plus, consultez Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx)dans une Windows PowerShell unique.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="b3b1a-144">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b3b1a-144">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="b3b1a-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b3b1a-146">Dans la **Windows PowerShell,** connectez-vous à votre Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="b3b1a-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="b3b1a-147">Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="b3b1a-148">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business  Online Connector.</span></span>

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="b3b1a-149">Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="b3b1a-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="b3b1a-150">Créer une stratégie d’accès externe personnalisée pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b3b1a-150">Create a custom external access policy for a user</span></span>

<span data-ttu-id="b3b1a-151">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="b3b1a-151">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b3b1a-152">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="b3b1a-152">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b3b1a-153">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b3b1a-154">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b3b1a-155">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="b3b1a-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b3b1a-156">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b3b1a-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b3b1a-157">Pourquoi utiliser Microsoft 365 ou PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="b3b1a-157">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="b3b1a-158">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="b3b1a-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b3b1a-159">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3b1a-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b3b1a-160">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3b1a-160">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b3b1a-161">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b3b1a-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b3b1a-162">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b3b1a-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="b3b1a-163">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b3b1a-163">Related topics</span></span>
[<span data-ttu-id="b3b1a-164">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="b3b1a-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="b3b1a-165">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="b3b1a-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="b3b1a-166">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="b3b1a-166">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
