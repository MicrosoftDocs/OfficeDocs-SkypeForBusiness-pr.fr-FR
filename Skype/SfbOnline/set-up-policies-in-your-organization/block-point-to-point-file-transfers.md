---
title: Bloquer les transferts de fichiers point à point
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Dans Skype entreprise Online, vous pouvez contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cela permet à un utilisateur de transférer des fichiers ou d’en bloquer les transferts de fichiers à des utilisateurs au sein de la même organisation ou à un utilisateur fédéré d’une autre organisation. En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.
ms.openlocfilehash: a92382a2fae3fd439aba4246937f1f6bda3c0b36
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962522"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="dbc5a-105">Bloquer les transferts de fichiers point à point</span><span class="sxs-lookup"><span data-stu-id="dbc5a-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="dbc5a-106">Dans Skype entreprise Online, vous pouvez contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="dbc5a-107">Toutefois, cela permet à un utilisateur de transférer des fichiers ou d’en bloquer les transferts de fichiers à des utilisateurs au sein de la même organisation ou à un utilisateur fédéré d’une autre organisation.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="dbc5a-108">En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="dbc5a-109">Le scénario le plus courant est que vous souhaitez autoriser les utilisateurs internes à utiliser le transfert de fichiers P2P, mais bloquer le transfert de fichiers avec des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="dbc5a-110">Pour ce scénario, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="dbc5a-111">Assigner une stratégie de conférence avec le transfert de fichiers P2P activée (_EnableP2PFileTransfer_ défini sur _true_) aux utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="dbc5a-112">Créer une stratégie de communication utilisateur externe globale définie pour bloquer les transferts de fichiers P2P externes (_EnableP2PFileTransfer_ défini sur _false_) et l’affecter à un utilisateur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="dbc5a-113">Vous pouvez en savoir plus sur [ces paramètres.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="dbc5a-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="dbc5a-114">Si un utilisateur fédéré extérieur à votre organisation tente d’envoyer un fichier à un utilisateur dans lequel la stratégie a été appliquée, il reçoit une erreur de **transfert** .</span><span class="sxs-lookup"><span data-stu-id="dbc5a-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="dbc5a-115">Si un utilisateur tente d’envoyer un fichier, il recevra une erreur de **transfert de fichier** .</span><span class="sxs-lookup"><span data-stu-id="dbc5a-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="dbc5a-116">Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’une application Skype entreprise « démarrer en un clic » de 2016.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="dbc5a-117">La version minimum suivante du client « démarrer en un clic » Skype entreprise 2016 est requise :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="dbc5a-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="dbc5a-118">**Type**</span></span>|<span data-ttu-id="dbc5a-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="dbc5a-119">**Release date**</span></span>|<span data-ttu-id="dbc5a-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="dbc5a-120">**Version**</span></span>|<span data-ttu-id="dbc5a-121">**Appui**</span><span class="sxs-lookup"><span data-stu-id="dbc5a-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dbc5a-122">First Release pour canal actuel</span><span class="sxs-lookup"><span data-stu-id="dbc5a-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="dbc5a-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="dbc5a-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="dbc5a-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="dbc5a-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="dbc5a-125">Version 1611 (Build 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="dbc5a-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="dbc5a-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="dbc5a-126">Current Channel</span></span>  <br/> |<span data-ttu-id="dbc5a-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="dbc5a-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="dbc5a-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="dbc5a-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="dbc5a-129">Version 1611 (Build 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="dbc5a-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="dbc5a-130">Canal différé</span><span class="sxs-lookup"><span data-stu-id="dbc5a-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="dbc5a-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="dbc5a-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="dbc5a-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="dbc5a-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="dbc5a-133">Version 1609 (Build 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="dbc5a-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="dbc5a-134">Les utilisateurs qui utilisent des versions plus anciennes de Skype entreprise Windows ou les clients Mac pourront toujours transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="dbc5a-135">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbc5a-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="dbc5a-136">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dbc5a-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="dbc5a-137">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="dbc5a-138">Vérifiez la version en entrant _Get-Host_ dans la fenêtre **Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="dbc5a-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="dbc5a-139">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="dbc5a-140">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="dbc5a-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="dbc5a-141">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="dbc5a-p107">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="dbc5a-145">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="dbc5a-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="dbc5a-146">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dbc5a-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="dbc5a-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="dbc5a-148">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dbc5a-149">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="dbc5a-150">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="dbc5a-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="dbc5a-151">Désactiver les transferts de fichiers P2P pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="dbc5a-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="dbc5a-152">Par défaut, _EnableP2PFileTransfer_ est activé sur la politique globale de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="dbc5a-153">Lors de la création de ce dernier, vos utilisateurs ont reçu la stratégie _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="dbc5a-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="dbc5a-154">Pour autoriser les transferts P2P au sein de votre organisation, mais bloquer les transferts de fichiers externes vers une autre organisation, il vous suffit de le modifier à un niveau global.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="dbc5a-155">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-155">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="dbc5a-156">Désactiver le transfert de fichiers P2P pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="dbc5a-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="dbc5a-157">Vous pouvez l’appliquer à un utilisateur en créant une nouvelle stratégie et en l’accordant à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="dbc5a-158">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-158">To do that, run:</span></span> 
> 
>   ```PowerShell
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```PowerShell
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="dbc5a-159">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="dbc5a-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="dbc5a-160">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="dbc5a-161">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="dbc5a-162">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dbc5a-163">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="dbc5a-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="dbc5a-164">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="dbc5a-165">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="dbc5a-165">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="dbc5a-166">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbc5a-166">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="dbc5a-167">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbc5a-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="dbc5a-168">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="dbc5a-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="dbc5a-169">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="dbc5a-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="dbc5a-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbc5a-170">Related topics</span></span>
[<span data-ttu-id="dbc5a-171">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="dbc5a-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="dbc5a-172">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="dbc5a-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="dbc5a-173">Configuration des stratégies de conférence au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="dbc5a-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
