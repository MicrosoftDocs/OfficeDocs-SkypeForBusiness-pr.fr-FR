---
title: Installer Microsoft Teams à l’aide de MSI, via SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Les administrateurs peuvent utiliser le MSI Teams pour déployer en bloc Microsoft Teams pour des utilisateurs ou sur des ordinateurs spécifiques.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e32eb60b238d606ac30fe74c7551e01efe88242a
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002228"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="8a0e0-103">Installer Microsoft Teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="8a0e0-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="8a0e0-104">Regardez la session suivante pour en savoir plus sur les avantages du client de bureau Windows, sur son planning et son déploiement : client de [Bureau Windows teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="8a0e0-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="8a0e0-105">Pour utiliser System Center Configuration Manager, ou une stratégie de groupe, ou tout mécanisme de distribution tiers pour un déploiement large, Microsoft a fourni des fichiers MSI (32-bits et 64-bit) que les administrateurs peuvent utiliser pour le déploiement en bloc d’équipes pour sélectionner des utilisateurs ou des ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="8a0e0-106">Les administrateurs peuvent utiliser ces fichiers pour déployer à distance des équipes de sorte que les utilisateurs n’aient pas à télécharger manuellement l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="8a0e0-107">Lorsque le déploiement est déployé, teams démarre automatiquement pour tous les utilisateurs qui se connectent à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="8a0e0-108">(Vous pouvez désactiver le lancement automatique après l’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="8a0e0-109">[Voir ci-dessous](#disable-auto-launch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, de sorte que tous les nouveaux utilisateurs de l’ordinateur bénéficient également de ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="8a0e0-110">Voici les liens vers les fichiers MSI :</span><span class="sxs-lookup"><span data-stu-id="8a0e0-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="8a0e0-111">Organisme</span><span class="sxs-lookup"><span data-stu-id="8a0e0-111">Entity</span></span>  |<span data-ttu-id="8a0e0-112">32 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-112">32 bit</span></span>      |<span data-ttu-id="8a0e0-113">64 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="8a0e0-114">Marché</span><span class="sxs-lookup"><span data-stu-id="8a0e0-114">Commercial</span></span>     | [<span data-ttu-id="8a0e0-115">32 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="8a0e0-116">64 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="8a0e0-117">Gouvernement fédéral-GCC</span><span class="sxs-lookup"><span data-stu-id="8a0e0-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="8a0e0-118">32 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="8a0e0-119">64 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="8a0e0-120">Public fédéral-GCC High</span><span class="sxs-lookup"><span data-stu-id="8a0e0-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="8a0e0-121">32 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="8a0e0-122">64 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="8a0e0-123">Gouvernement fédéral-DoD</span><span class="sxs-lookup"><span data-stu-id="8a0e0-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="8a0e0-124">32 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="8a0e0-125">64 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="8a0e0-126">Les équipes peuvent également être incluses dans un déploiement d’Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="8a0e0-127">Pour plus d’informations, reportez-vous à la rubrique [déploiement de Microsoft teams avec Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="8a0e0-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="8a0e0-128">Pour en savoir plus sur SCCM, voir [Présentation de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="8a0e0-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="8a0e0-129">Procédure de déploiement (recommandée)</span><span class="sxs-lookup"><span data-stu-id="8a0e0-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="8a0e0-130">Récupérez le package le plus récent.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="8a0e0-131">Utilisez les valeurs par défaut préremplies par le MSI.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="8a0e0-132">Déployez sur les ordinateurs lorsque c’est possible.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="8a0e0-133">Fonctionnement du package MSI Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="8a0e0-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="8a0e0-134">Installation sur PC</span><span class="sxs-lookup"><span data-stu-id="8a0e0-134">PC installation</span></span>

<span data-ttu-id="8a0e0-135">Le MSI teams place un programme d’installation dans les fichiers programme.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="8a0e0-136">Dès qu’un utilisateur se connecte à un nouveau profil utilisateur Windows, le programme d’installation est lancé et une copie de l’application teams est installée dans le dossier AppData de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="8a0e0-137">Si un utilisateur possède déjà l’application teams installée dans le dossier AppData, le programme d’installation MSI ignore le processus pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="8a0e0-138">N’utilisez pas le MSI pour déployer les mises à jour, car le client effectue automatiquement une mise à jour dès qu’il détecte une nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="8a0e0-139">Pour redéployer le dernier programme d’installation, procédez comme suit lors du processus de redéploiement de MSI décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="8a0e0-140">Si vous déployez une version plus ancienne du package MSI, le client se met à jour automatiquement (sauf dans les environnements VDI) lorsque l’utilisateur le peut.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="8a0e0-141">Si une ancienne version est déployée, le MSI déclenche une mise à jour de l’application avant que l’utilisateur ne puisse utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="8a0e0-142">Nous vous déconseillons de ne pas modifier les emplacements d’installation par défaut, car cela risque de perturber le déroulement de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="8a0e0-143">La présence d’une trop ancienne version entraînera le blocage des utilisateurs de l’accès au service.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="8a0e0-144">Configuration requise pour l’ordinateur cible</span><span class="sxs-lookup"><span data-stu-id="8a0e0-144">Target computer requirements</span></span>

- <span data-ttu-id="8a0e0-145">.NET Framework 4,5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="8a0e0-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="8a0e0-146">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="8a0e0-146">Windows 7 or later</span></span>
- <span data-ttu-id="8a0e0-147">3 Go d’espace disque pour chaque profil utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="8a0e0-147">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="8a0e0-148">Installation de VDI</span><span class="sxs-lookup"><span data-stu-id="8a0e0-148">VDI installation</span></span>

<span data-ttu-id="8a0e0-149">Pour obtenir des instructions complètes sur le déploiement de l’application de bureau teams sur VDI, voir [teams pour l’infrastructure de bureau virtuelle](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="8a0e0-149">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="8a0e0-150">Procédure de nettoyage et de redéploiement</span><span class="sxs-lookup"><span data-stu-id="8a0e0-150">Clean up and redeployment procedure</span></span>

<span data-ttu-id="8a0e0-151">Si un utilisateur désinstalle teams de son profil utilisateur, le programme d’installation MSI effectue le suivi de la désinstallation de l’application teams par l’utilisateur et n’installe plus teams pour ce profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-151">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="8a0e0-152">Pour redéployer teams pour cet utilisateur sur un ordinateur particulier sur lequel il a été désinstallé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a0e0-152">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="8a0e0-153">Désinstaller l’application teams installée pour chaque profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-153">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="8a0e0-154">Après la désinstallation, supprimez le répertoire de manière récursive sous%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-154">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="8a0e0-155">Redéployez le package MSI sur cet ordinateur particulier.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-155">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="8a0e0-156">Vous pouvez utiliser le script de [nettoyage du déploiement de Microsoft teams](scripts/Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-156">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="8a0e0-157">Désactiver le lancement automatique pour le programme d’installation MSI</span><span class="sxs-lookup"><span data-stu-id="8a0e0-157">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="8a0e0-158">Le comportement par défaut de MSI consiste à installer le client teams dès qu’un utilisateur se connecte, puis à démarrer automatiquement Teams.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-158">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="8a0e0-159">Vous pouvez modifier ce comportement avec les paramètres ci-dessous comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a0e0-159">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="8a0e0-160">Quand un utilisateur se connecte à Windows, teams est installé avec le MSI</span><span class="sxs-lookup"><span data-stu-id="8a0e0-160">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="8a0e0-161">Toutefois, le client Teams ne démarre pas tant que l’utilisateur n’a pas démarré les équipes manuellement</span><span class="sxs-lookup"><span data-stu-id="8a0e0-161">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="8a0e0-162">Un raccourci pour démarrer teams sera ajouté au bureau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-162">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="8a0e0-163">Lorsque l’utilisateur se connecte, il démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-163">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="8a0e0-164">Pour la version 32 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-164">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="8a0e0-165">Pour la version 64 bits</span><span class="sxs-lookup"><span data-stu-id="8a0e0-165">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> <span data-ttu-id="8a0e0-166">Si vous exécutez manuellement le MSI, veillez à l’exécuter avec des autorisations élevées.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-166">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="8a0e0-167">Même si vous l’exécutez en tant qu’administrateur, vous n’avez pas à le faire à l’aide de privilèges élevés, le programme d’installation ne peut pas configurer l’option permettant de désactiver le démarrage automatique.</span><span class="sxs-lookup"><span data-stu-id="8a0e0-167">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
