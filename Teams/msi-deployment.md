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
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37567959"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="6819a-103">Installer Microsoft Teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="6819a-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="6819a-104">Regardez la session suivante pour en savoir plus sur les avantages du client de bureau Windows, sur son planning et son déploiement : client de [Bureau Windows teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="6819a-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="6819a-105">Pour utiliser System Center Configuration Manager, ou une stratégie de groupe ou tout mécanisme de distribution tiers pour un déploiement large, Microsoft a fourni des fichiers MSI ( [32-bits](https://aka.ms/teams32bitmsi) et [64-bit](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en bloc d’équipes et sélectionner utilisateurs ou ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="6819a-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="6819a-106">Les administrateurs peuvent utiliser ces fichiers pour déployer à distance des équipes de sorte que les utilisateurs n’aient pas à télécharger manuellement l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="6819a-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="6819a-107">Lorsque le déploiement est déployé, teams démarre automatiquement pour tous les utilisateurs qui se connectent à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6819a-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="6819a-108">(Vous pouvez désactiver le lancement automatique après l’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="6819a-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="6819a-109">[Voir ci-dessous](#disable-auto-launch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, de sorte que tous les nouveaux utilisateurs de l’ordinateur bénéficient également de ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="6819a-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="6819a-110">Les équipes peuvent également être incluses dans un déploiement d’Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="6819a-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="6819a-111">Pour plus d’informations, reportez-vous à la rubrique [déploiement de Microsoft teams avec Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="6819a-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="6819a-112">Pour en savoir plus sur SCCM, voir [Présentation de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="6819a-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="6819a-113">Procédure de déploiement (recommandée)</span><span class="sxs-lookup"><span data-stu-id="6819a-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="6819a-114">Récupérez le package le plus récent.</span><span class="sxs-lookup"><span data-stu-id="6819a-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="6819a-115">Utilisez les valeurs par défaut préremplies par le MSI.</span><span class="sxs-lookup"><span data-stu-id="6819a-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="6819a-116">Déployez sur les ordinateurs lorsque c’est possible.</span><span class="sxs-lookup"><span data-stu-id="6819a-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="6819a-117">Fonctionnement du package MSI Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="6819a-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="6819a-118">Installation sur PC</span><span class="sxs-lookup"><span data-stu-id="6819a-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="6819a-119">Pour obtenir des instructions sur le déploiement d’équipes dans un environnement VDI (Virtual DesktopInfrastructure), voir [installation de VDI](#vdi-installation) .</span><span class="sxs-lookup"><span data-stu-id="6819a-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="6819a-120">Le MSI teams place un programme d’installation dans les fichiers programme.</span><span class="sxs-lookup"><span data-stu-id="6819a-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="6819a-121">Dès qu’un utilisateur se connecte à un nouveau profil utilisateur Windows, le programme d’installation est lancé et une copie de l’application teams est installée dans le dossier AppData de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6819a-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="6819a-122">Si un utilisateur possède déjà l’application teams installée dans le dossier AppData, le programme d’installation MSI ignore le processus pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6819a-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="6819a-123">N’utilisez pas le MSI pour déployer les mises à jour, car le client effectue automatiquement une mise à jour dès qu’il détecte une nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="6819a-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="6819a-124">Pour redéployer le dernier programme d’installation, procédez comme suit lors du processus de redéploiement de MSI décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6819a-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="6819a-125">Si vous déployez une version plus ancienne du package MSI, le client se met à jour automatiquement (sauf dans les environnements VDI) lorsque l’utilisateur le peut.</span><span class="sxs-lookup"><span data-stu-id="6819a-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="6819a-126">Si une ancienne version est déployée, le MSI déclenche une mise à jour de l’application avant que l’utilisateur ne puisse utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="6819a-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="6819a-127">Nous vous déconseillons de ne pas modifier les emplacements d’installation par défaut, car cela risque de perturber le déroulement de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="6819a-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="6819a-128">La présence d’une trop ancienne version entraînera le blocage des utilisateurs de l’accès au service.</span><span class="sxs-lookup"><span data-stu-id="6819a-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="6819a-129">Configuration requise pour l’ordinateur cible</span><span class="sxs-lookup"><span data-stu-id="6819a-129">Target computer requirements</span></span>

- <span data-ttu-id="6819a-130">.NET Framework 4,5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="6819a-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="6819a-131">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="6819a-131">Windows 7 or later</span></span>
- <span data-ttu-id="6819a-132">3 Go d’espace disque pour chaque profil utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="6819a-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="6819a-133">Installation de VDI</span><span class="sxs-lookup"><span data-stu-id="6819a-133">VDI installation</span></span>

<span data-ttu-id="6819a-134">Voici le processus de déploiement de l’application de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="6819a-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="6819a-135">Pour obtenir des instructions complètes, voir [teams pour l’infrastructure de bureau virtualisée](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="6819a-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="6819a-136">Téléchargez le package MSI teams à l’aide de l’un des liens suivants selon l’environnement.</span><span class="sxs-lookup"><span data-stu-id="6819a-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="6819a-137">Nous vous recommandons d’utiliser la version 64 bits d’un VM VDI doté d’un système d’exploitation 64 bits.</span><span class="sxs-lookup"><span data-stu-id="6819a-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="6819a-138">version 32 bits</span><span class="sxs-lookup"><span data-stu-id="6819a-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="6819a-139">version 64 bits</span><span class="sxs-lookup"><span data-stu-id="6819a-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="6819a-140">Exécutez la commande suivante pour installer le MSI sur la machine virtuelle VDI (ou terminer la mise à jour).</span><span class="sxs-lookup"><span data-stu-id="6819a-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="6819a-141">Cette opération permet d’installer teams pour programmer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="6819a-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="6819a-142">À ce stade, la configuration de l’image Golden est terminée.</span><span class="sxs-lookup"><span data-stu-id="6819a-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="6819a-143">La prochaine session interactive de connexion démarre teams et demande des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="6819a-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="6819a-144">Notez qu’il n’est pas possible de désactiver le lancement automatique d’équipes lors de l’installation d’équipes sur VDI à l’aide de la propriété ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="6819a-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="6819a-145">Exécutez la commande suivante pour désinstaller le MSI de l’ordinateur virtuel VDI (ou préparer la mise à jour).</span><span class="sxs-lookup"><span data-stu-id="6819a-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="6819a-146">Cela a pour cela la désinstallation de teams.</span><span class="sxs-lookup"><span data-stu-id="6819a-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="6819a-147">Procédure de nettoyage et de redéploiement</span><span class="sxs-lookup"><span data-stu-id="6819a-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="6819a-148">Si un utilisateur désinstalle teams de son profil utilisateur, le programme d’installation MSI effectue le suivi de la désinstallation de l’application teams par l’utilisateur et n’installe plus teams pour ce profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6819a-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="6819a-149">Pour redéployer teams pour cet utilisateur sur un ordinateur particulier sur lequel il a été désinstallé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6819a-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="6819a-150">Désinstaller l’application teams installée pour chaque profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6819a-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="6819a-151">Après la désinstallation, supprimez le répertoire de manière récursive sous%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="6819a-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="6819a-152">Redéployez le package MSI sur cet ordinateur particulier.</span><span class="sxs-lookup"><span data-stu-id="6819a-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="6819a-153">Vous pouvez utiliser le script de [nettoyage du déploiement de Microsoft teams](scripts/Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="6819a-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="6819a-154">Désactiver le lancement automatique pour le programme d’installation MSI</span><span class="sxs-lookup"><span data-stu-id="6819a-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="6819a-155">Le comportement par défaut de MSI consiste à installer le client teams dès qu’un utilisateur se connecte, puis à démarrer automatiquement Teams.</span><span class="sxs-lookup"><span data-stu-id="6819a-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="6819a-156">Vous pouvez modifier ce comportement avec les paramètres ci-dessous comme suit :</span><span class="sxs-lookup"><span data-stu-id="6819a-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="6819a-157">Quand un utilisateur se connecte à Windows, teams est installé avec le MSI</span><span class="sxs-lookup"><span data-stu-id="6819a-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="6819a-158">Toutefois, le client Teams ne démarre pas tant que l’utilisateur n’a pas démarré les équipes manuellement</span><span class="sxs-lookup"><span data-stu-id="6819a-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="6819a-159">Un raccourci pour démarrer teams sera ajouté au bureau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6819a-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="6819a-160">Lorsque l’utilisateur se connecte, il démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6819a-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="6819a-161">Pour la version 32 bits</span><span class="sxs-lookup"><span data-stu-id="6819a-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="6819a-162">Pour la version 64 bits</span><span class="sxs-lookup"><span data-stu-id="6819a-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="6819a-163">Si vous exécutez manuellement le MSI, veillez à l’exécuter avec des autorisations élevées.</span><span class="sxs-lookup"><span data-stu-id="6819a-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="6819a-164">Même si vous l’exécutez en tant qu’administrateur, vous n’avez pas à le faire à l’aide de privilèges élevés, le programme d’installation ne peut pas configurer l’option permettant de désactiver le démarrage automatique.</span><span class="sxs-lookup"><span data-stu-id="6819a-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
