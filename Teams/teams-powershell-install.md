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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768337"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="d12f3-103">Installer Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d12f3-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="d12f3-104">Cet article explique comment installer le module Microsoft Teams PowerShell à l’aide [de PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="d12f3-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="d12f3-105">Ces instructions s’utilisent [sur Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS et Windows plateformes.</span><span class="sxs-lookup"><span data-stu-id="d12f3-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="d12f3-106">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="d12f3-106">Requirements</span></span>

<span data-ttu-id="d12f3-107">Teams PowerShell requiert PowerShell 5.1 ou une plateforme supérieure sur toutes les plateformes.</span><span class="sxs-lookup"><span data-stu-id="d12f3-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="d12f3-108">Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d12f3-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="d12f3-109">Pour une expérience la plus agréable possible, nous vous recommandons d’utiliser PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="d12f3-109">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="d12f3-110">Installer le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d12f3-110">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="d12f3-111">Pour une expérience accrue, utilisez les modules Disponibilité générale (GA) ou Prévisualisation publique, et non les deux.</span><span class="sxs-lookup"><span data-stu-id="d12f3-111">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="d12f3-112">Ils n’ont pas l’intention de collaborer.</span><span class="sxs-lookup"><span data-stu-id="d12f3-112">They're not intended to work together.</span></span>


<span data-ttu-id="d12f3-113">Utilisez les **cmdlets PowerShellGet** pour installer le module Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d12f3-113">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="d12f3-114">L’installation du module pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="d12f3-114">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="d12f3-115">Démarrez la session PowerShell à l’aide **de** l’Windows ou utilisez la `sudo` commande sur macOS ou Linux :</span><span class="sxs-lookup"><span data-stu-id="d12f3-115">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="d12f3-116">Par défaut, la Galerie PowerShell (PSGallery) n’est pas configurée comme référentiel fiable **pour PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="d12f3-116">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="d12f3-117">La première fois que vous utilisez PSGallery, vous verrez le message suivant :</span><span class="sxs-lookup"><span data-stu-id="d12f3-117">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="d12f3-118">Répondez **Oui** **ou Oui à Tous pour** poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="d12f3-118">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="d12f3-119">Connexion</span><span class="sxs-lookup"><span data-stu-id="d12f3-119">Sign in</span></span>

<span data-ttu-id="d12f3-120">Pour commencer à travailler avec Teams PowerShell, connectez-vous avec vos informations d’identification Azure.</span><span class="sxs-lookup"><span data-stu-id="d12f3-120">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="d12f3-121">Si vous utilisez la dernière version d’Teams public [PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d12f3-121">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="d12f3-122">Se connectez à l’aide de l’authentification multifacteur et de l’authentification moderne</span><span class="sxs-lookup"><span data-stu-id="d12f3-122">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="d12f3-123">Si votre compte utilise l’authentification multifacteur, utilisez les étapes de cette section.</span><span class="sxs-lookup"><span data-stu-id="d12f3-123">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a><span data-ttu-id="d12f3-124">Mise à Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d12f3-124">Update Teams PowerShell</span></span>

<span data-ttu-id="d12f3-125">Pour mettre à Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d12f3-125">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="d12f3-126">Si Teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue.</span><span class="sxs-lookup"><span data-stu-id="d12f3-126">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="d12f3-127">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.</span><span class="sxs-lookup"><span data-stu-id="d12f3-127">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="d12f3-128">Désinstaller Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d12f3-128">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="d12f3-129">Pour désinstaller Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d12f3-129">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="d12f3-130">Si Teams PowerShell a déjà été importé dans votre session PowerShell, la désinstallation du module échoue.</span><span class="sxs-lookup"><span data-stu-id="d12f3-130">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="d12f3-131">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.</span><span class="sxs-lookup"><span data-stu-id="d12f3-131">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="d12f3-132">Installer Teams prévisualisation publique de PowerShell</span><span class="sxs-lookup"><span data-stu-id="d12f3-132">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="d12f3-133">Si vous utilisez la version d’aperçu public de Teams PowerShell, nous vous recommandons vivement de désinstaller d’abord Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d12f3-133">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="d12f3-134">L’installation Teams module d’aperçu public PowerShell pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="d12f3-134">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="d12f3-135">Démarrez la session PowerShell à l’aide **de** l’outil Exécuter en Windows ou utilisez la `sudo` commande sur macOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="d12f3-135">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="d12f3-136">Si vous utilisez PowerShell 5.1, vous devez mettre à jour le module **PowerShellGet** au préalable.</span><span class="sxs-lookup"><span data-stu-id="d12f3-136">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="d12f3-137">Après avoir mis **à jour PowerShellGet,** fermez et rouvrez une session PowerShell avec élévation de charge pour vous assurer que la dernière **version de PowerShellGet** est chargée.</span><span class="sxs-lookup"><span data-stu-id="d12f3-137">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="d12f3-138">Pour installer Teams aperçu public PowerShell, exécutez la commande PowerShell ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d12f3-138">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="d12f3-139">Vous pouvez trouver la dernière version d’aperçu dans la [galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou dans PowerShell en exécutant « Find-Module MicrosoftTeams -AllowPrerelease -AllVersions »</span><span class="sxs-lookup"><span data-stu-id="d12f3-139">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="d12f3-140">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d12f3-140">Next Steps</span></span>

<span data-ttu-id="d12f3-141">Vous êtes maintenant prêt à gérer vos Teams l’aide Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d12f3-141">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="d12f3-142">Consultez [Gérer Teams avec Teams PowerShell pour](teams-powershell-managing-teams.md) commencer.</span><span class="sxs-lookup"><span data-stu-id="d12f3-142">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d12f3-143">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="d12f3-143">Related topics</span></span>

[<span data-ttu-id="d12f3-144">Gestion des Teams à l’Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d12f3-144">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="d12f3-145">Teams Notes de publication de PowerShell</span><span class="sxs-lookup"><span data-stu-id="d12f3-145">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="d12f3-146">Microsoft Teams des cmdlet</span><span class="sxs-lookup"><span data-stu-id="d12f3-146">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="d12f3-147">Skype Entreprise des cmdlet</span><span class="sxs-lookup"><span data-stu-id="d12f3-147">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
