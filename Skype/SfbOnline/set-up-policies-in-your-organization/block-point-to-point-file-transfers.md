---
title: Bloquer les transferts de fichiers point à point
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: Dans Skype pour Business Online, vous avez capacité à contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existante. Toutefois, ceci permet ou bloque pour les utilisateurs si elles sont transfert de fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d’une autre organisation, les transferts de fichiers. Suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec les organisations fédérées ou des partenaires.
ms.openlocfilehash: 6ca79b45c4e068ae6999db24cf6a0dd54e9e3aa6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372102"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="39824-105">Bloquer les transferts de fichiers point à point</span><span class="sxs-lookup"><span data-stu-id="39824-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="39824-106">Dans Skype pour Business Online, vous avez capacité à contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existante.</span><span class="sxs-lookup"><span data-stu-id="39824-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="39824-107">Toutefois, ceci permet ou bloque pour les utilisateurs si elles sont transfert de fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d’une autre organisation, les transferts de fichiers.</span><span class="sxs-lookup"><span data-stu-id="39824-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="39824-108">Suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec les organisations fédérées ou des partenaires.</span><span class="sxs-lookup"><span data-stu-id="39824-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="39824-109">Un scénario très fréquent est lorsque vous souhaitez autoriser les utilisateurs internes à utiliser P2P le transfert de fichiers, mais le transfert de fichiers bloquées avec les partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="39824-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="39824-110">Dans ce scénario, vous devez faire :</span><span class="sxs-lookup"><span data-stu-id="39824-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="39824-111">Affecter une stratégie de conférence P2P transfert de fichiers activé (_EnableP2PFileTransfer_ la valeur _True_) pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="39824-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="39824-112">Créer une stratégie de communication utilisateur externe globale définie pour bloquer les transferts de fichiers externes P2P (_EnableP2PFileTransfer_ définie sur _False_) et l’affecter à un utilisateur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="39824-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="39824-113">Vous trouverez plus d’informations sur ces paramètres [ici](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="39824-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="39824-114">Si un utilisateur fédéré à l’extérieur de votre organisation tente d’envoyer un fichier à un utilisateur dont la stratégie a été appliquée, ils recevront une erreur **Échec de transfert** .</span><span class="sxs-lookup"><span data-stu-id="39824-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="39824-115">Et si un utilisateur tente d’envoyer un fichier, ils reçoivent une erreur de **transfert de fichiers est désactivé** .</span><span class="sxs-lookup"><span data-stu-id="39824-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="39824-116">Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’un Skype de Click-to-Run 2016 pour l’application de gestion qui prend en charge.</span><span class="sxs-lookup"><span data-stu-id="39824-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="39824-117">La version minimale suivante Skype pour Business 2016 Click-to-Run client est requise :</span><span class="sxs-lookup"><span data-stu-id="39824-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="39824-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="39824-118">**Type**</span></span>|<span data-ttu-id="39824-119">**Date de publication**</span><span class="sxs-lookup"><span data-stu-id="39824-119">**Release date**</span></span>|<span data-ttu-id="39824-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="39824-120">**Version**</span></span>|<span data-ttu-id="39824-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="39824-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39824-122">Première version de canal en cours</span><span class="sxs-lookup"><span data-stu-id="39824-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="39824-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="39824-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="39824-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="39824-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="39824-125">Version 1611 (version 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="39824-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="39824-126">Canal actuel</span><span class="sxs-lookup"><span data-stu-id="39824-126">Current Channel</span></span>  <br/> |<span data-ttu-id="39824-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="39824-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="39824-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="39824-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="39824-129">Version 1611 (version 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="39824-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="39824-130">Canal différée</span><span class="sxs-lookup"><span data-stu-id="39824-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="39824-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="39824-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="39824-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="39824-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="39824-133">Version 1609 (version 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="39824-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="39824-134">Les utilisateurs qui utilisent des versions antérieures de Skype pour les applications métiers Windows ou Mac pourront transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="39824-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="39824-135">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39824-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="39824-136">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="39824-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="39824-137">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="39824-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="39824-138">Vérifier la version en tapant _l’Obtention de l’hôte_ dans la fenêtre **Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="39824-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="39824-p106">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="39824-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="39824-p107">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="39824-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="39824-145">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="39824-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="39824-146">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="39824-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="39824-147">Depuis le **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="39824-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="39824-148">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="39824-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39824-149">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="39824-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="39824-150">Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="39824-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="39824-151">Désactiver les transferts de fichiers P2P pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="39824-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="39824-152">Par défaut, _EnableP2PFileTransfer_ est activée sur la stratégie globale de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="39824-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="39824-153">Lors de sa création, vos utilisateurs ont été affectés à la stratégie _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="39824-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="39824-154">Pour autoriser les transferts P2P pour à l’intérieur de votre organisation, mais bloquer les transferts de fichiers externes à une autre organisation, il vous suffit de la modifier à un niveau global.</span><span class="sxs-lookup"><span data-stu-id="39824-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="39824-155">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="39824-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="39824-156">Désactiver les transferts de fichiers P2P pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="39824-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="39824-157">Vous pouvez appliquer cette à un utilisateur en créant une nouvelle stratégie et lui accorder à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="39824-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="39824-158">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="39824-158">To do that, run:</span></span> 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="39824-159">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="39824-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="39824-160">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="39824-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="39824-161">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="39824-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="39824-162">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="39824-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="39824-163">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="39824-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="39824-164">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="39824-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="39824-p112">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="39824-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="39824-167">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39824-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="39824-168">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="39824-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="39824-169">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="39824-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="39824-170">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="39824-170">Related topics</span></span>
[<span data-ttu-id="39824-171">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="39824-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="39824-172">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="39824-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="39824-173">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="39824-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 