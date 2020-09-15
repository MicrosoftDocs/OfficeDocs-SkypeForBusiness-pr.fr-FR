---
title: Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814583"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="16d10-103">Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook</span><span class="sxs-lookup"><span data-stu-id="16d10-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="16d10-104">Les utilisateurs peuvent précharger le contenu, les fichiers ou les pièces jointes jointes à une invitation à une réunion dans Skype entreprise Online, mais vous pouvez les activer ou les désactiver.</span><span class="sxs-lookup"><span data-stu-id="16d10-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="16d10-105">Cette option est activée par défaut pour toutes les organisations qui utilisent Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="16d10-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="16d10-106">Découvrez comment [Préchargement des pièces jointes pour une réunion Skype Entreprise](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="16d10-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="16d10-107">Pour l’instant, il n’existe aucune cmdlet disponible dans Skype entreprise Online pour définir ou afficher des valeurs en ligne pour  _MaxContentStorageMB_ et _MaxUploadFileMB_.</span><span class="sxs-lookup"><span data-stu-id="16d10-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="16d10-108">Elles ne sont disponibles que pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="16d10-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="16d10-109">Il est important de savoir que le contenu n’est pas chargé dans une réunion si le contenu joint dépasse le  _MaxUploadFileSizeMB_ ou si la limite _MaxContentStorageMB_ est atteinte.</span><span class="sxs-lookup"><span data-stu-id="16d10-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="16d10-110">Pour commencer</span><span class="sxs-lookup"><span data-stu-id="16d10-110">To get you started</span></span>

### 

 <span data-ttu-id="16d10-111">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="16d10-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="16d10-112">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="16d10-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="16d10-113">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="16d10-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="16d10-114">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16d10-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="16d10-115">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="16d10-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="16d10-116">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="16d10-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="16d10-p104">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="16d10-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="16d10-120">Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="16d10-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="16d10-121">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="16d10-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="16d10-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="16d10-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="16d10-123">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="16d10-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
> [!NOTE]
> <span data-ttu-id="16d10-124">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="16d10-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="16d10-125">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="16d10-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
  
```PowerShell
Import-Module -Name MicrosoftTeams
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="16d10-126">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="16d10-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="16d10-127">Activation ou désactivation des applications intégrées</span><span class="sxs-lookup"><span data-stu-id="16d10-127">Turning it on or off</span></span>

<span data-ttu-id="16d10-128">La possibilité de précharger le contenu joint à une invitation à une réunion Outlook dans les réunions Skype entreprise Online est activée par défaut, mais il est possible que vous deviez éviter que les utilisateurs de votre organisation préchargent du contenu dans leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="16d10-128">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="16d10-129">Ce paramètre ne peut être activé ou désactivé que pour l’ensemble de votre organisation. vous ne pouvez pas l’activer ou le désactiver pour un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="16d10-129">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="16d10-130">**Pour le désactiver, ouvrez Windows PowerShell et procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="16d10-130">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="16d10-131">**Si vous voulez le réactiver, ouvrez Windows PowerShell et procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="16d10-131">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="16d10-132">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="16d10-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="16d10-133">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="16d10-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="16d10-134">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="16d10-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="16d10-135">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="16d10-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="16d10-136">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="16d10-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="16d10-137">Six raisons d’utiliser Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="16d10-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="16d10-138">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="16d10-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="16d10-139">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="16d10-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="16d10-140">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16d10-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="16d10-141">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="16d10-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="16d10-142">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="16d10-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="16d10-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16d10-143">Related topics</span></span>
[<span data-ttu-id="16d10-144">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="16d10-144">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="16d10-145">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="16d10-145">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
