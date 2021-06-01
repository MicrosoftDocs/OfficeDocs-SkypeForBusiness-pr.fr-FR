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
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239107"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="29eae-103">Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook</span><span class="sxs-lookup"><span data-stu-id="29eae-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="29eae-104">Les utilisateurs peuvent précharger du contenu, des fichiers ou des pièces jointes joints à une invitation à une réunion Outlook à une réunion Skype Entreprise Online, mais vous pouvez activer ou désactiver cette fonction.</span><span class="sxs-lookup"><span data-stu-id="29eae-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="29eae-105">Elle est désactivée par défaut pour toutes les organisations qui utilisent Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="29eae-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="29eae-106">Découvrez comment [Préchargement des pièces jointes pour une réunion Skype Entreprise](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="29eae-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29eae-107">Actuellement, il n’existe aucune cmdlets disponibles dans Skype Entreprise Online pour définir ou afficher les valeurs en ligne pour _MaxContentStorageMB_ et _MaxUploadFileMB._</span><span class="sxs-lookup"><span data-stu-id="29eae-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="29eae-108">Elles ne sont disponibles que pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="29eae-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="29eae-109">Il est important de savoir que le contenu ne sera pas téléchargé dans une réunion si le contenu joint dépasse la limite  _MaxUploadFileSizeMB_ ou si la limite _maxContentStorageMB_ est atteinte.</span><span class="sxs-lookup"><span data-stu-id="29eae-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="29eae-110">Pour commencer</span><span class="sxs-lookup"><span data-stu-id="29eae-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="29eae-111">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29eae-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="29eae-112">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="29eae-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="29eae-113">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="29eae-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="29eae-114">Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="29eae-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="29eae-115">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="29eae-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="29eae-116">Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="29eae-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="29eae-117">Activation ou désactivation des applications intégrées</span><span class="sxs-lookup"><span data-stu-id="29eae-117">Turning it on or off</span></span>

<span data-ttu-id="29eae-118">La possibilité de précharger du contenu joint à une invitation à une réunion Outlook pour des réunions Skype Entreprise Online est désactivée par défaut, mais vous devrez peut-être empêcher les utilisateurs de votre organisation de précharger du contenu dans leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="29eae-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="29eae-119">Ce paramètre ne peut être désactivé que pour l’ensemble de votre organisation. vous ne pouvez pas l’activer ou le désactiver pour un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29eae-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="29eae-120">**Pour le désactiver, ouvrez Windows PowerShell et procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="29eae-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="29eae-121">**Si vous voulez le réactiver, ouvrez Windows PowerShell et procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="29eae-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="29eae-122">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="29eae-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="29eae-123">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="29eae-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="29eae-124">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="29eae-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="29eae-125">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="29eae-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="29eae-126">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="29eae-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="29eae-127">Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365 ou des Office 365</span><span class="sxs-lookup"><span data-stu-id="29eae-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="29eae-128">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="29eae-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="29eae-129">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="29eae-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="29eae-130">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="29eae-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="29eae-131">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="29eae-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="29eae-132">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="29eae-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="29eae-133">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="29eae-133">Related topics</span></span>
[<span data-ttu-id="29eae-134">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="29eae-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="29eae-135">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="29eae-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
