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
description: Dans Skype Entreprise Online, vous avez la possibilité de contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cela permet ou bloque les transferts de fichiers pour les utilisateurs, qu’ils transférent ou non des fichiers à un utilisateur de la même organisation ou à un utilisateur fédéré d’une autre organisation. En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.
ms.openlocfilehash: e20cf0d5ff7a884e81fe2ee5de57ed026c53552e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240173"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="59da9-105">Bloquer les transferts de fichiers point à point</span><span class="sxs-lookup"><span data-stu-id="59da9-105">Block Point-to-Point file transfers</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="59da9-106">Dans Skype Entreprise Online, vous avez la possibilité de contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants.</span><span class="sxs-lookup"><span data-stu-id="59da9-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="59da9-107">Toutefois, cela permet ou bloque les transferts de fichiers pour les utilisateurs, qu’ils transférent ou non des fichiers à un utilisateur de la même organisation ou à un utilisateur fédéré d’une autre organisation.</span><span class="sxs-lookup"><span data-stu-id="59da9-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="59da9-108">En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="59da9-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="59da9-109">Un scénario très courant est celui où vous voulez autoriser les utilisateurs internes à utiliser le transfert de fichiers P2P mais bloquer le transfert de fichiers avec des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="59da9-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="59da9-110">Dans ce scénario, vous devez :</span><span class="sxs-lookup"><span data-stu-id="59da9-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="59da9-111">Affectez une stratégie de conférence avec le transfert de fichiers P2P activé _(EnableP2PFileTransfer_ définie sur _True)_ aux utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="59da9-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="59da9-112">Créez une stratégie de communication utilisateur externe globale définie pour bloquer les transferts de fichiers P2P externes _(EnableP2PFileTransfer_ définie sur _False)_ et l’affecter à un utilisateur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="59da9-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="59da9-113">Pour en savoir plus sur ces paramètres, [cliquez ici.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="59da9-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="59da9-114">Si un utilisateur fédéré extérieur à votre organisation tente d’envoyer un fichier à un utilisateur pour lequel la stratégie a été appliquée, il reçoit un message d’erreur « Échec **du** transfert ».</span><span class="sxs-lookup"><span data-stu-id="59da9-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="59da9-115">Si un utilisateur tente d’envoyer un fichier, il reçoit une erreur **de transfert de** fichier désactivée.</span><span class="sxs-lookup"><span data-stu-id="59da9-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="59da9-116">Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’une application De Skype Entreprise 2016 qui la prend en charge.</span><span class="sxs-lookup"><span data-stu-id="59da9-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="59da9-117">La version minimale suivante du client « Skype Entreprise - Exécuter en un clic 2016 est requise :</span><span class="sxs-lookup"><span data-stu-id="59da9-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="59da9-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="59da9-118">**Type**</span></span>|<span data-ttu-id="59da9-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="59da9-119">**Release date**</span></span>|<span data-ttu-id="59da9-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="59da9-120">**Version**</span></span>|<span data-ttu-id="59da9-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="59da9-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59da9-122">First Release pour Canal actuel</span><span class="sxs-lookup"><span data-stu-id="59da9-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="59da9-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="59da9-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="59da9-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="59da9-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="59da9-125">Version 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="59da9-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="59da9-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="59da9-126">Current Channel</span></span>  <br/> |<span data-ttu-id="59da9-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="59da9-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="59da9-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="59da9-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="59da9-129">Version 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="59da9-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="59da9-130">Canal différé</span><span class="sxs-lookup"><span data-stu-id="59da9-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="59da9-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="59da9-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="59da9-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="59da9-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="59da9-133">Version 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="59da9-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="59da9-134">Les utilisateurs qui utilisent des versions antérieures de Skype Entreprise Windows clients Mac seront toujours en mesure de transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="59da9-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="59da9-135">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59da9-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="59da9-136">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="59da9-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="59da9-137">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="59da9-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="59da9-138">Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="59da9-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="59da9-139">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="59da9-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="59da9-140">Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="59da9-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="59da9-141">Désactiver les transferts de fichiers P2P pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="59da9-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="59da9-142">Par défaut, _EnableP2PFileTransfer_ est activé sur la stratégie globale de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="59da9-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="59da9-143">Lors de sa création, la stratégie _BposSAllModality_ a été affectée à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="59da9-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="59da9-144">Pour autoriser les transferts de fichiers P2P au sein de votre organisation, mais bloquer les transferts de fichiers externes vers une autre organisation, vous devez simplement le modifier au niveau global.</span><span class="sxs-lookup"><span data-stu-id="59da9-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="59da9-145">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="59da9-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="59da9-146">Désactiver les transferts de fichiers P2P pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="59da9-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="59da9-147">Vous pouvez l’appliquer à un utilisateur en créant une stratégie et en l’octroyant à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="59da9-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="59da9-148">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="59da9-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="59da9-149">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="59da9-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="59da9-150">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="59da9-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="59da9-151">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="59da9-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="59da9-152">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="59da9-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="59da9-153">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="59da9-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="59da9-154">Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="59da9-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="59da9-155">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="59da9-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="59da9-156">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="59da9-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="59da9-157">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="59da9-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="59da9-158">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="59da9-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="59da9-159">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="59da9-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="59da9-160">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="59da9-160">Related topics</span></span>
[<span data-ttu-id="59da9-161">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="59da9-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="59da9-162">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="59da9-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="59da9-163">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="59da9-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
