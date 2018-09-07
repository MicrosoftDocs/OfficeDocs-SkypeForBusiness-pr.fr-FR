---
title: Créer des stratégies d'accès externe personnalisées
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype pour Business Online vous permet de créer des stratégies d’accès externe supplémentaires. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfini qui peuvent couvrir la plupart des scénarios.
ms.openlocfilehash: e0af31d015c69ebd91c28a229a20d3d2c6c926c4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850156"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="4c19c-104">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="4c19c-104">Create custom external access policies</span></span>

<span data-ttu-id="4c19c-105">Skype pour Business Online vous permet de créer des stratégies d’accès externe supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="4c19c-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="4c19c-106">Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfini qui peuvent couvrir la plupart des scénarios.</span><span class="sxs-lookup"><span data-stu-id="4c19c-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="4c19c-107">Il s’agit :</span><span class="sxs-lookup"><span data-stu-id="4c19c-107">These are:</span></span>
  
- <span data-ttu-id="4c19c-108">Non fédéré ou Access Skype consommateur (_Balise : NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="4c19c-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="4c19c-109">Accès fédéré uniquement (_Balise : FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="4c19c-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="4c19c-110">Fédérés et consommateur accéder (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="4c19c-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="4c19c-111">Permettent de stratégies externes personnalisées pour créer d’autres stratégies qui ne sont pas couverts par les paramètres ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="4c19c-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="4c19c-112">Lorsque la stratégie a été créée, vous doit définir tous les paramètres requis et n’a pas pu modifier ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="4c19c-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="4c19c-113">Création de nouvelles stratégies personnalisées vous permettent de fonctionnalités de contrôle de l’accès consommateur Skype ou une stratégie pour désactiver public cloud audio/vidéo, qui est un élément qui n’a pas été abordées avec les paramètres prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="4c19c-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="4c19c-114">Stratégies d’accès externe personnalisé suivent la même syntaxe que les stratégies de client, de mobilité et de conférence.</span><span class="sxs-lookup"><span data-stu-id="4c19c-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="4c19c-115">Vous trouverez plus d’informations sur ces paramètres [ici](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="4c19c-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="4c19c-116">Pour ce faire, l’utilisateur doit utiliser une version prise en charge de 2016 Click-to-Run Skype pour l’application de gestion qui prend en charge.</span><span class="sxs-lookup"><span data-stu-id="4c19c-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="4c19c-117">La version minimale suivante Skype pour Business 2016 Click-to-Run client est requise :</span><span class="sxs-lookup"><span data-stu-id="4c19c-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="4c19c-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="4c19c-118">**Type**</span></span>|<span data-ttu-id="4c19c-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="4c19c-119">**Release date**</span></span>|<span data-ttu-id="4c19c-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="4c19c-120">**Version**</span></span>|<span data-ttu-id="4c19c-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="4c19c-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c19c-122">Première version de canal en cours</span><span class="sxs-lookup"><span data-stu-id="4c19c-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="4c19c-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="4c19c-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="4c19c-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="4c19c-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="4c19c-125">Version 1611 (version 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="4c19c-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="4c19c-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="4c19c-126">Current Channel</span></span>  <br/> |<span data-ttu-id="4c19c-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="4c19c-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="4c19c-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="4c19c-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="4c19c-129">Version 1611 (version 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="4c19c-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="4c19c-130">Canal différée</span><span class="sxs-lookup"><span data-stu-id="4c19c-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="4c19c-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="4c19c-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="4c19c-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="4c19c-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="4c19c-133">Version 1609 (version 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="4c19c-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="4c19c-134">Les utilisateurs qui utilisent des versions antérieures de Skype pour les applications métiers Windows ou Mac pourront transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="4c19c-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="4c19c-135">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c19c-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="4c19c-136">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4c19c-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="4c19c-137">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4c19c-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4c19c-138">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4c19c-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="4c19c-p105">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="4c19c-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="4c19c-p106">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="4c19c-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="4c19c-145">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="4c19c-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="4c19c-146">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4c19c-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="4c19c-147">Depuis le **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4c19c-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4c19c-148">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="4c19c-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c19c-149">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="4c19c-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="4c19c-150">Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4c19c-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="4c19c-151">Créer une stratégie d’accès externe personnalisé pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4c19c-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="4c19c-152">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4c19c-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4c19c-153">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="4c19c-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4c19c-154">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="4c19c-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4c19c-155">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="4c19c-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4c19c-156">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="4c19c-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4c19c-157">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4c19c-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4c19c-158">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c19c-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4c19c-p108">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c19c-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4c19c-161">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c19c-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4c19c-162">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4c19c-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4c19c-163">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4c19c-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4c19c-164">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4c19c-164">Related topics</span></span>
[<span data-ttu-id="4c19c-165">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="4c19c-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="4c19c-166">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="4c19c-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="4c19c-167">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="4c19c-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 