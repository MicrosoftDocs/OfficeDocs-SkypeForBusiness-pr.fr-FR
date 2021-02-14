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
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662019"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="57f4e-103">Installer Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="57f4e-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="57f4e-104">Cet article explique comment installer le module Microsoft Teams PowerShell à l’aide [de PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="57f4e-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="57f4e-105">Ces instructions s’utilisent sur les plateformes [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS et Windows.</span><span class="sxs-lookup"><span data-stu-id="57f4e-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="57f4e-106">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="57f4e-106">Requirements</span></span>

<span data-ttu-id="57f4e-107">Teams PowerShell requiert PowerShell 5.1 ou une plateforme supérieure sur toutes les plateformes.</span><span class="sxs-lookup"><span data-stu-id="57f4e-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="57f4e-108">Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="57f4e-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="57f4e-109">Il existe des problèmes connus avec PowerShell 7 et Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57f4e-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="57f4e-110">Pour une expérience la plus agréable possible, nous vous recommandons d’utiliser PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="57f4e-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="57f4e-111">Installer le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="57f4e-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="57f4e-112">Pour une expérience accrue, utilisez les modules Disponibilité générale (GA) ou Prévisualisation publique, et non les deux.</span><span class="sxs-lookup"><span data-stu-id="57f4e-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="57f4e-113">Ils n’ont pas l’intention de collaborer.</span><span class="sxs-lookup"><span data-stu-id="57f4e-113">They're not intended to work together.</span></span>


<span data-ttu-id="57f4e-114">Utilisez les **cmdlets PowerShellGet** pour installer le module Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57f4e-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="57f4e-115">L’installation du module pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="57f4e-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="57f4e-116">Démarrez la session PowerShell à l’aide **de l’outil** Exécuter en tant qu’administrateur dans Windows ou utilisez la `sudo` commande sur macOS ou Linux :</span><span class="sxs-lookup"><span data-stu-id="57f4e-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="57f4e-117">Par défaut, la Galerie PowerShell (PSGallery) n’est pas configurée comme référentiel fiable **pour PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="57f4e-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="57f4e-118">La première fois que vous utilisez PSGallery, vous verrez le message suivant :</span><span class="sxs-lookup"><span data-stu-id="57f4e-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="57f4e-119">Répondez **Oui** ou **Oui à Tous pour** poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="57f4e-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="57f4e-120">Installer la prévisualisation publique de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="57f4e-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="57f4e-121">Si vous utilisez la version d’aperçu public de Teams PowerShell, nous vous recommandons vivement de désinstaller Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="57f4e-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="57f4e-122">L’installation du module d’aperçu public Teams PowerShell pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="57f4e-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="57f4e-123">Démarrez la session PowerShell à l’aide **de l’outil** Exécuter en tant qu’administrateur dans Windows ou utilisez la `sudo` commande sur macOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="57f4e-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="57f4e-124">Si vous utilisez PowerShell 5.1, vous devez mettre à jour le module **PowerShellGet** au préalable.</span><span class="sxs-lookup"><span data-stu-id="57f4e-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="57f4e-125">Après avoir mis **à jour PowerShellGet,** fermez et rouvrez une session PowerShell avec élévation de charge pour vous assurer que la dernière **version de PowerShellGet** est chargée.</span><span class="sxs-lookup"><span data-stu-id="57f4e-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="57f4e-126">Pour installer la prévisualisation publique de Teams PowerShell, exécutez la commande PowerShell ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="57f4e-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="57f4e-127">Vous pouvez trouver la dernière version d’aperçu dans la [galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou dans PowerShell en exécutant « Find-Module MicrosoftTeams -AllowPrerelease »</span><span class="sxs-lookup"><span data-stu-id="57f4e-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="57f4e-128">Installation de Skype Entreprise Online Connector</span><span class="sxs-lookup"><span data-stu-id="57f4e-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="57f4e-129">Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="57f4e-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="57f4e-130">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="57f4e-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="57f4e-131">Connexion</span><span class="sxs-lookup"><span data-stu-id="57f4e-131">Sign in</span></span>

<span data-ttu-id="57f4e-132">Pour commencer à travailler avec Teams PowerShell, connectez-vous avec vos informations d’identification Azure.</span><span class="sxs-lookup"><span data-stu-id="57f4e-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="57f4e-133">Si vous utilisez la dernière version d’aperçu [public de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="57f4e-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="57f4e-134">Mettre à jour Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="57f4e-134">Update Teams PowerShell</span></span>

<span data-ttu-id="57f4e-135">Pour mettre à jour Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="57f4e-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="57f4e-136">Si Teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue.</span><span class="sxs-lookup"><span data-stu-id="57f4e-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="57f4e-137">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.</span><span class="sxs-lookup"><span data-stu-id="57f4e-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="57f4e-138">Désinstaller Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="57f4e-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="57f4e-139">Pour désinstaller Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="57f4e-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="57f4e-140">Si Teams PowerShell a déjà été importé dans votre session PowerShell, la désinstallation du module échoue.</span><span class="sxs-lookup"><span data-stu-id="57f4e-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="57f4e-141">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.</span><span class="sxs-lookup"><span data-stu-id="57f4e-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="57f4e-142">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="57f4e-142">Next Steps</span></span>

<span data-ttu-id="57f4e-143">Vous êtes maintenant prêt à gérer Teams à l’aide de Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57f4e-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="57f4e-144">Consultez [Gérer les équipes avec Teams PowerShell](teams-powershell-managing-teams.md) pour commencer.</span><span class="sxs-lookup"><span data-stu-id="57f4e-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57f4e-145">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="57f4e-145">Related topics</span></span>

[<span data-ttu-id="57f4e-146">Gestion des équipes avec Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="57f4e-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="57f4e-147">Notes de publication de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="57f4e-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="57f4e-148">Référence de l’cmdlet Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57f4e-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="57f4e-149">Référence de l’cmdlet Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="57f4e-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
