---
title: Installer Microsoft teams PowerShell
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
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="0902c-103">Installer Microsoft teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0902c-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="0902c-104">Cet article explique comment installer le module Microsoft teams PowerShell à l’aide de [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="0902c-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="0902c-105">Ces instructions fonctionnent sur les plateformes [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, MacOS et Windows.</span><span class="sxs-lookup"><span data-stu-id="0902c-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="0902c-106">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="0902c-106">Requirements</span></span>

<span data-ttu-id="0902c-107">Teams PowerShell nécessite PowerShell 5,1 ou une version ultérieure sur toutes les plateformes.</span><span class="sxs-lookup"><span data-stu-id="0902c-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="0902c-108">Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="0902c-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="0902c-109">Il existe des problèmes connus dans PowerShell 7 et teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0902c-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="0902c-110">Pour une utilisation optimale, nous vous recommandons d’utiliser PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="0902c-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="0902c-111">Installer le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="0902c-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="0902c-112">Pour une utilisation optimale, utilisez les modules de disponibilité générale (GA) ou d’aperçu public.</span><span class="sxs-lookup"><span data-stu-id="0902c-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="0902c-113">Ils ne sont pas destinés à être utilisés ensemble.</span><span class="sxs-lookup"><span data-stu-id="0902c-113">They're not intended to work together.</span></span>


<span data-ttu-id="0902c-114">Utilisez les applets de cmdlet **PowerShellGet** pour installer le module teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0902c-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="0902c-115">L’installation du module pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="0902c-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="0902c-116">Démarrez la session PowerShell à l’aide de l’option **exécuter en tant qu’administrateur** dans Windows ou utilisez la `sudo` commande sur MacOS ou Linux :</span><span class="sxs-lookup"><span data-stu-id="0902c-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="0902c-117">Par défaut, la Galerie PowerShell (PSGallery) n’est pas configurée en tant que référentiel approuvé pour **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="0902c-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="0902c-118">Lorsque vous utilisez PSGallery pour la première fois, le message suivant s’affiche :</span><span class="sxs-lookup"><span data-stu-id="0902c-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="0902c-119">Répondez **Yes** ou **Yes à All** pour continuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="0902c-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="0902c-120">Installer teams public preview</span><span class="sxs-lookup"><span data-stu-id="0902c-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="0902c-121">Si vous utilisez la version bêta publique de teams PowerShell, nous vous conseillons vivement de désinstaller le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0902c-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="0902c-122">L’installation du module PowerShell public Preview d’teams pour tous les utilisateurs sur un système nécessite des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="0902c-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="0902c-123">Démarrez la session PowerShell à l’aide de l’option **exécuter en tant qu’administrateur** dans Windows ou utilisez la `sudo` commande sur MacOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="0902c-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="0902c-124">Si vous utilisez PowerShell 5,1, vous devez mettre à jour le module **PowerShellGet** auparavant.</span><span class="sxs-lookup"><span data-stu-id="0902c-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="0902c-125">Après avoir effectué la mise à jour de **PowerShellGet**, fermez et rouvrez une session PowerShell avec élévation de privilèges pour vous assurer que la dernière version de **PowerShellGet** est chargée.</span><span class="sxs-lookup"><span data-stu-id="0902c-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="0902c-126">Pour installer Team PowerShell public Preview, exécutez la commande PowerShell ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0902c-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="0902c-127">Pour savoir comment accéder à la version d’évaluation la plus récente dans la [Galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou dans PowerShell, exécutez « Find-module MicrosoftTeams-AllowPrerelease ».</span><span class="sxs-lookup"><span data-stu-id="0902c-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="0902c-128">Installation de Skype entreprise Online Connector</span><span class="sxs-lookup"><span data-stu-id="0902c-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="0902c-129">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="0902c-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="0902c-130">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0902c-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="0902c-131">Connexion</span><span class="sxs-lookup"><span data-stu-id="0902c-131">Sign in</span></span>

<span data-ttu-id="0902c-132">Pour commencer à utiliser teams PowerShell, connectez-vous à l’aide de vos informations d’identification Azure.</span><span class="sxs-lookup"><span data-stu-id="0902c-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="0902c-133">Si vous utilisez la version la plus récente de la [version préliminaire public teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0902c-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="0902c-134">Mettre à jour PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="0902c-134">Update Teams PowerShell</span></span>

<span data-ttu-id="0902c-135">Pour mettre à jour PowerShell Teams, ouvrez une nouvelle invite de commandes PowerShell avec élévation de privilèges et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0902c-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="0902c-136">Si teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue.</span><span class="sxs-lookup"><span data-stu-id="0902c-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="0902c-137">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="0902c-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="0902c-138">Désinstaller teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0902c-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="0902c-139">Pour désinstaller teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de privilèges et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0902c-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="0902c-140">Si teams PowerShell a déjà été importé dans votre session PowerShell, la désinstallation du module échoue.</span><span class="sxs-lookup"><span data-stu-id="0902c-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="0902c-141">Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="0902c-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0902c-142">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="0902c-142">Next Steps</span></span>

<span data-ttu-id="0902c-143">Vous êtes maintenant prêt à gérer teams à l’aide de teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0902c-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="0902c-144">Pour commencer, voir [gestion d’équipes avec teams PowerShell](teams-powershell-managing-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="0902c-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0902c-145">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="0902c-145">Related topics</span></span>

[<span data-ttu-id="0902c-146">Gestion des équipes avec PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="0902c-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="0902c-147">Notes de publication teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0902c-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="0902c-148">Référence sur les applets de passe Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="0902c-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="0902c-149">Référence sur les applets de fonction Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="0902c-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
