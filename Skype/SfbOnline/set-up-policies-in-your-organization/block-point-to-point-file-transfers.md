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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Dans Skype Entreprise Online, vous pouvez contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cela permet ou bloque les transferts de fichiers pour les utilisateurs, qu’ils transférent ou non des fichiers à un utilisateur de la même organisation ou à un utilisateur fédéré d’une autre organisation. En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814633"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="f8f81-105">Bloquer les transferts de fichiers point à point</span><span class="sxs-lookup"><span data-stu-id="f8f81-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="f8f81-106">Dans Skype Entreprise Online, vous pouvez contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants.</span><span class="sxs-lookup"><span data-stu-id="f8f81-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="f8f81-107">Toutefois, cela permet ou bloque les transferts de fichiers pour les utilisateurs, qu’ils transférent ou non des fichiers à un utilisateur de la même organisation ou à un utilisateur fédéré d’une autre organisation.</span><span class="sxs-lookup"><span data-stu-id="f8f81-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="f8f81-108">En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="f8f81-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="f8f81-109">Un scénario très courant est celui où vous voulez autoriser les utilisateurs internes à utiliser le transfert de fichiers P2P mais bloquer le transfert de fichiers avec des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="f8f81-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="f8f81-110">Dans ce scénario, vous devez :</span><span class="sxs-lookup"><span data-stu-id="f8f81-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="f8f81-111">Affectez une stratégie de conférence avec le transfert de fichiers P2P activé _(EnableP2PFileTransfer_ définie sur _True)_ aux utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f8f81-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="f8f81-112">Créez une stratégie de communication utilisateur externe globale définie pour bloquer les transferts de fichiers P2P externes _(EnableP2PFileTransfer_ définie sur _False)_ et l’affecter à un utilisateur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f8f81-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="f8f81-113">Pour en savoir plus sur ces paramètres, [cliquez ici.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="f8f81-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="f8f81-114">Si un utilisateur fédéré en dehors de votre organisation tente d’envoyer un fichier à un utilisateur pour lequel la stratégie a été appliquée, il reçoit un message d’erreur « Échec **du** transfert ».</span><span class="sxs-lookup"><span data-stu-id="f8f81-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="f8f81-115">Et si un utilisateur tente d’envoyer un fichier, il reçoit une erreur de transfert de fichier **désactivée.**</span><span class="sxs-lookup"><span data-stu-id="f8f81-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="f8f81-116">Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’une application Skype Entreprise « Exécuter en un clic » 2016 qui la prend en charge.</span><span class="sxs-lookup"><span data-stu-id="f8f81-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="f8f81-117">La version minimale suivante du client Skype Entreprise 2016 « Click-to-Run ) est requise :</span><span class="sxs-lookup"><span data-stu-id="f8f81-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="f8f81-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="f8f81-118">**Type**</span></span>|<span data-ttu-id="f8f81-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="f8f81-119">**Release date**</span></span>|<span data-ttu-id="f8f81-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="f8f81-120">**Version**</span></span>|<span data-ttu-id="f8f81-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="f8f81-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8f81-122">First Release pour Canal actuel</span><span class="sxs-lookup"><span data-stu-id="f8f81-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="f8f81-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="f8f81-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="f8f81-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="f8f81-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="f8f81-125">Version 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="f8f81-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="f8f81-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="f8f81-126">Current Channel</span></span>  <br/> |<span data-ttu-id="f8f81-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="f8f81-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="f8f81-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="f8f81-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="f8f81-129">Version 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="f8f81-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="f8f81-130">Canal différé</span><span class="sxs-lookup"><span data-stu-id="f8f81-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="f8f81-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="f8f81-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="f8f81-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="f8f81-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="f8f81-133">Version 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="f8f81-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="f8f81-134">Les utilisateurs qui utilisent des versions antérieures des applications Windows skype Entreprise ou des clients Mac pourront toujours transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="f8f81-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="f8f81-135">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8f81-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="f8f81-136">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f8f81-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="f8f81-137">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f8f81-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="f8f81-138">Vérifiez la version en tapant _Get-Host_ dans la **Windows PowerShell’accueil.**</span><span class="sxs-lookup"><span data-stu-id="f8f81-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="f8f81-139">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8f81-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="f8f81-140">Voir [Windows Management Framework 4.0 pour](https://go.microsoft.com/fwlink/?LinkId=716845) télécharger et mettre à jour Windows PowerShell vers la version 4.0.</span><span class="sxs-lookup"><span data-stu-id="f8f81-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="f8f81-141">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="f8f81-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="f8f81-142">Vous devrez également installer le module Windows PowerShell teams qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="f8f81-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="f8f81-143">Pour en savoir plus, consultez Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx)dans une Windows PowerShell unique.</span><span class="sxs-lookup"><span data-stu-id="f8f81-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="f8f81-144">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f8f81-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="f8f81-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f8f81-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="f8f81-146">Dans la **Windows PowerShell,** connectez-vous à votre Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="f8f81-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="f8f81-147">Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="f8f81-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="f8f81-148">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="f8f81-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="f8f81-149">Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="f8f81-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="f8f81-150">Désactiver les transferts de fichiers P2P pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="f8f81-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="f8f81-151">Par défaut, _EnableP2PFileTransfer_ est activé sur la stratégie globale de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="f8f81-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="f8f81-152">Lors de sa création, la stratégie _BposSAllModality_ a été affectée à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f8f81-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="f8f81-153">Pour autoriser les transferts de fichiers P2P au sein de votre organisation, mais bloquer les transferts de fichiers externes vers une autre organisation, vous devez simplement le modifier au niveau global.</span><span class="sxs-lookup"><span data-stu-id="f8f81-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="f8f81-154">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8f81-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="f8f81-155">Désactiver les transferts de fichiers P2P pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f8f81-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="f8f81-156">Vous pouvez l’appliquer à un utilisateur en créant une stratégie et en l’octroyant à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f8f81-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="f8f81-157">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8f81-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f8f81-158">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="f8f81-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="f8f81-159">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="f8f81-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f8f81-160">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="f8f81-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f8f81-161">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="f8f81-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f8f81-162">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f8f81-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f8f81-163">Pourquoi utiliser Microsoft 365 ou PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="f8f81-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f8f81-164">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="f8f81-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f8f81-165">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8f81-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f8f81-166">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8f81-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f8f81-167">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f8f81-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f8f81-168">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f8f81-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f8f81-169">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f8f81-169">Related topics</span></span>
[<span data-ttu-id="f8f81-170">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="f8f81-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="f8f81-171">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="f8f81-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="f8f81-172">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="f8f81-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
