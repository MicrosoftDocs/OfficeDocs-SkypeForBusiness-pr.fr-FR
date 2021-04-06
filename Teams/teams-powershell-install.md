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
description: Découvrez comment utiliser les contrôles PowerShell pour gérer Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6679cd22800307ec95ac242c190d6483411413a9
ms.sourcegitcommit: 109b3869afb5ff1ca4eaf771399d7cda70a43bea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51586543"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="429d5-103">Installer Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="429d5-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="429d5-104">Cet article explique comment installer le module Microsoft Teams PowerShell à l’aide [de PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="429d5-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="429d5-105">Ces instructions s’utilisent sur les plateformes [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS et Windows.</span><span class="sxs-lookup"><span data-stu-id="429d5-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="429d5-106">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="429d5-106">Requirements</span></span>

<span data-ttu-id="429d5-107">Teams PowerShell requiert PowerShell 5.1 ou une plateforme supérieure sur toutes les plateformes.</span><span class="sxs-lookup"><span data-stu-id="429d5-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="429d5-108">Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="429d5-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="429d5-109">Il existe des problèmes connus avec PowerShell 7 et Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="429d5-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="429d5-110">Pour une expérience la plus agréable possible, nous vous recommandons d’utiliser PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="429d5-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="429d5-111">Installer le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="429d5-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="429d5-112">Pour une expérience accrue, utilisez les modules Disponibilité générale (GA) ou Prévisualisation publique, et non les deux.</span><span class="sxs-lookup"><span data-stu-id="429d5-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="429d5-113">Ils n’ont pas l’intention de collaborer.</span><span class="sxs-lookup"><span data-stu-id="429d5-113">They're not intended to work together.</span></span>


<span data-ttu-id="429d5-114">Utilisez les **cmdlets PowerShellGet** pour installer le module Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="429d5-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="429d5-115">L’installation du module pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="429d5-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="429d5-116">Démarrez la session PowerShell à l’aide **de l’outil** Exécuter en tant qu’administrateur dans Windows ou utilisez la `sudo` commande sur macOS ou Linux :</span><span class="sxs-lookup"><span data-stu-id="429d5-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="429d5-117">Par défaut, la Galerie PowerShell (PSGallery) n’est pas configurée comme référentiel fiable **pour PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="429d5-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="429d5-118">La première fois que vous utilisez PSGallery, vous verrez le message suivant :</span><span class="sxs-lookup"><span data-stu-id="429d5-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="429d5-119">Répondez **Oui** **ou Oui à Tous pour** poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="429d5-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="429d5-120">Connexion</span><span class="sxs-lookup"><span data-stu-id="429d5-120">Sign in</span></span>

<span data-ttu-id="429d5-121">Pour commencer à travailler avec Teams PowerShell, connectez-vous avec vos informations d’identification Azure.</span><span class="sxs-lookup"><span data-stu-id="429d5-121">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="429d5-122">Si vous utilisez la dernière version d’aperçu [public de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="429d5-122">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="429d5-123">Se connectez à l’aide de l’authentification multifacteur et de l’authentification moderne</span><span class="sxs-lookup"><span data-stu-id="429d5-123">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="429d5-124">Si votre compte utilise l’authentification multifacteur, utilisez les étapes de cette section.</span><span class="sxs-lookup"><span data-stu-id="429d5-124">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="429d5-125">Mettre à jour Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="429d5-125">Update Teams PowerShell</span></span>

<span data-ttu-id="429d5-126">Pour mettre à jour Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="429d5-126">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="429d5-127">Si Teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue.</span><span class="sxs-lookup"><span data-stu-id="429d5-127">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="429d5-128">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.</span><span class="sxs-lookup"><span data-stu-id="429d5-128">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="429d5-129">Désinstaller Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="429d5-129">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="429d5-130">Pour désinstaller Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="429d5-130">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="429d5-131">Si Teams PowerShell a déjà été importé dans votre session PowerShell, la désinstallation du module échoue.</span><span class="sxs-lookup"><span data-stu-id="429d5-131">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="429d5-132">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.</span><span class="sxs-lookup"><span data-stu-id="429d5-132">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="429d5-133">Installer la prévisualisation publique de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="429d5-133">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="429d5-134">Si vous utilisez la version d’aperçu public de Teams PowerShell, nous vous recommandons vivement de désinstaller Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="429d5-134">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="429d5-135">L’installation du module d’aperçu public Teams PowerShell pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="429d5-135">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="429d5-136">Démarrez la session PowerShell à l’aide **de l’outil** Exécuter en tant qu’administrateur dans Windows ou utilisez la `sudo` commande sur macOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="429d5-136">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="429d5-137">Si vous utilisez PowerShell 5.1, vous devez mettre à jour le module **PowerShellGet** au préalable.</span><span class="sxs-lookup"><span data-stu-id="429d5-137">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="429d5-138">Après avoir mis **à jour PowerShellGet,** fermez et rouvrez une session PowerShell avec élévation de charge pour vous assurer que la dernière **version de PowerShellGet** est chargée.</span><span class="sxs-lookup"><span data-stu-id="429d5-138">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="429d5-139">Pour installer la prévisualisation publique de Teams PowerShell, exécutez la commande PowerShell ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="429d5-139">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="429d5-140">Vous pouvez trouver la dernière version d’aperçu dans la [galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou dans PowerShell en exécutant « Find-Module MicrosoftTeams -AllowPrerelease -AllVersions »</span><span class="sxs-lookup"><span data-stu-id="429d5-140">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="429d5-141">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="429d5-141">Next Steps</span></span>

<span data-ttu-id="429d5-142">Vous êtes maintenant prêt à gérer Teams à l’aide de Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="429d5-142">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="429d5-143">Consultez [Gérer les équipes avec Teams PowerShell](teams-powershell-managing-teams.md) pour commencer.</span><span class="sxs-lookup"><span data-stu-id="429d5-143">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="429d5-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="429d5-144">Related topics</span></span>

[<span data-ttu-id="429d5-145">Gestion des équipes avec Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="429d5-145">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="429d5-146">Notes de publication de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="429d5-146">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="429d5-147">Référence de l’cmdlet Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="429d5-147">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="429d5-148">Référence de l’cmdlet Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="429d5-148">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)