---
title: Installer Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les contrôles PowerShell pour gérer les Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947565"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="69c6f-103">Installer Microsoft Teams module PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c6f-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="69c6f-104">Cet article explique comment installer le module PowerShell Microsoft Teams’aide de la Galerie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69c6f-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="69c6f-105">Le Microsoft Teams module PowerShell est pris en charge sur toutes Windows plateformes.</span><span class="sxs-lookup"><span data-stu-id="69c6f-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="69c6f-106">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="69c6f-106">Requirements</span></span>

<span data-ttu-id="69c6f-107">Microsoft Teams Le module PowerShell requiert PowerShell 5.1 ou une plateforme supérieure sur toutes les plateformes.</span><span class="sxs-lookup"><span data-stu-id="69c6f-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="69c6f-108">Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell)   disponible pour votre système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="69c6f-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="69c6f-109">Pour vérifier votre version de PowerShell, exécutez la commande suivante à partir d’une session PowerShell :</span><span class="sxs-lookup"><span data-stu-id="69c6f-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="69c6f-110">Nous vous recommandons d’utiliser Install-Module cmdlet pour installer Microsoft Teams module PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69c6f-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="69c6f-111">Si la Galerie PowerShell (PSGallery) n’est pas configurée comme référentiel approuvé pour **PowerShellGet,** la première fois que vous utilisez PSGallery, vous verrez le message suivant :</span><span class="sxs-lookup"><span data-stu-id="69c6f-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="69c6f-112">Répondez **Oui** ou **Oui à Tous pour** poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="69c6f-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="69c6f-113">Installation à l’aide de PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="69c6f-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="69c6f-114">Microsoft Teams Le module PowerShell est actuellement pris en charge pour une utilisation avec PowerShell 5.1 sur Windows.</span><span class="sxs-lookup"><span data-stu-id="69c6f-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="69c6f-115">Pour installer le module, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="69c6f-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="69c6f-116">Mettre à [jour Windows PowerShell 5.1.](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="69c6f-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="69c6f-117">Si vous avez la Windows 10 1607 ou une version supérieure, powerShell 5.1 est déjà installé.</span><span class="sxs-lookup"><span data-stu-id="69c6f-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="69c6f-118">Installez [.NET Framework 4.7.2 ou une ultérieure.](/dotnet/framework/install)</span><span class="sxs-lookup"><span data-stu-id="69c6f-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="69c6f-119">Exécutez la commande suivante pour installer la dernière version de PowerShellGet :</span><span class="sxs-lookup"><span data-stu-id="69c6f-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="69c6f-120">Installez le Teams module PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69c6f-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="69c6f-121">Installation hors connexion</span><span class="sxs-lookup"><span data-stu-id="69c6f-121">Offline Installation</span></span> 

<span data-ttu-id="69c6f-122">Dans certains environnements, il n’est pas possible de se connecter à la galerie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69c6f-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="69c6f-123">Dans ces situations, suivez ces étapes [d’installation manuelle.](https://aka.ms/psgallery-manualdownload)</span><span class="sxs-lookup"><span data-stu-id="69c6f-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="69c6f-124">Connexion</span><span class="sxs-lookup"><span data-stu-id="69c6f-124">Sign in</span></span>

<span data-ttu-id="69c6f-125">Pour commencer à travailler avec Microsoft Teams module PowerShell, connectez-vous avec vos informations d’identification Azure.</span><span class="sxs-lookup"><span data-stu-id="69c6f-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="69c6f-126">Mettre à jour Teams module PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c6f-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="69c6f-127">Pour mettre à jour un module PowerShell, vous devez utiliser la même méthode que lors de l’installation du module.</span><span class="sxs-lookup"><span data-stu-id="69c6f-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="69c6f-128">Par exemple, si vous utilisiez le module d’installation à l’origine, vous devez utiliser [Update-Module](/powershell/module/powershellget/update-module) pour obtenir la dernière version.</span><span class="sxs-lookup"><span data-stu-id="69c6f-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="69c6f-129">Si Teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue.</span><span class="sxs-lookup"><span data-stu-id="69c6f-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="69c6f-130">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.</span><span class="sxs-lookup"><span data-stu-id="69c6f-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="69c6f-131">Désinstaller Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c6f-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="69c6f-132">Pour désinstaller Microsoft Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="69c6f-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="69c6f-133">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="69c6f-133">Next Steps</span></span> 

<span data-ttu-id="69c6f-134">Vous êtes maintenant prêt à gérer votre travail Microsoft Teams’Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69c6f-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="69c6f-135">Consultez [Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md) pour commencer.</span><span class="sxs-lookup"><span data-stu-id="69c6f-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="69c6f-136">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="69c6f-136">Related topics</span></span>

[<span data-ttu-id="69c6f-137">Gestion des Teams à l’Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c6f-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="69c6f-138">Teams Notes de publication de PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c6f-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="69c6f-139">Microsoft Teams des cmdlet</span><span class="sxs-lookup"><span data-stu-id="69c6f-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="69c6f-140">Skype Entreprise des cmdlet</span><span class="sxs-lookup"><span data-stu-id="69c6f-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
