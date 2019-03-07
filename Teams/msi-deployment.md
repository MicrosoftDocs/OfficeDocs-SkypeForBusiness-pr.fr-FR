---
title: Installer Microsoft Teams à l’aide de MSI, via SCCM
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Les administrateurs peuvent utiliser le MSI Teams pour déployer en bloc Microsoft Teams pour des utilisateurs ou sur des ordinateurs spécifiques.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5ffceef19e91f5d3e694db7655d23efb67498ae
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464347"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="fd040-103">Installer Microsoft Teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="fd040-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="fd040-104">Regarder la session pour en savoir plus sur le Client de bureau Windows, comment planifier et déployer les avantages suivante : [Client de bureau Windows équipes](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="fd040-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="fd040-105">Pour utiliser System Center Configuration Manager ou la stratégie de groupe ou les mécanismes de distribution de tiers pour le déploiement, Microsoft a fourni les fichiers MSI ( [32 bits](https://aka.ms/teams32bitmsi) et [64 bits](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en bloc des équipes pour sélectionner les utilisateurs ou ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="fd040-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="fd040-106">Administrateurs peuvent utiliser ces fichiers pour déployer des équipes à distance afin que les utilisateurs n’ont pas télécharger manuellement l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="fd040-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="fd040-107">Lors du déploiement, les équipes automatique de lancement pour tous les utilisateurs qui se connectent à sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fd040-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="fd040-108">(Vous pouvez désactiver lancement automatique après l’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="fd040-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="fd040-109">[Voir ci-dessous](#disable-auto-lanuch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs de l’ordinateur bénéficient également ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="fd040-109">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="fd040-110">Pour en savoir plus sur SCCM, voir [Introduction à System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="fd040-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="fd040-111">Procédure de déploiement (recommandé)</span><span class="sxs-lookup"><span data-stu-id="fd040-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="fd040-112">Récupérer le dernier package.</span><span class="sxs-lookup"><span data-stu-id="fd040-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="fd040-113">Utilisez les valeurs par défaut préremplies par le fichier MSI.</span><span class="sxs-lookup"><span data-stu-id="fd040-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="fd040-114">Déployez sur les ordinateurs lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="fd040-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="fd040-115">Comment fonctionne le package Microsoft équipes MSI</span><span class="sxs-lookup"><span data-stu-id="fd040-115">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="fd040-116">Le fichier MSI équipes place un programme d’installation dans les fichiers de programme.</span><span class="sxs-lookup"><span data-stu-id="fd040-116">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="fd040-117">Chaque fois qu’un utilisateur se connecte à un nouveau profil d’utilisateur Windows, le programme d’installation est lancé et une copie de l’application des équipes sera installée dans le dossier appdata de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd040-117">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="fd040-118">Si l’utilisateur a déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignore le processus de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd040-118">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="fd040-119">N’utilisez pas le fichier MSI pour déployer des mises à jour, car le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service.</span><span class="sxs-lookup"><span data-stu-id="fd040-119">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="fd040-120">Pour redéployer le programme d’installation le plus récent utiliser le processus de redéploiement MSI décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="fd040-120">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="fd040-121">Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd040-121"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="fd040-122">Si une version ancienne très obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes.</span><span class="sxs-lookup"><span data-stu-id="fd040-122">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="fd040-123">Nous ne pas recommandé de modifier les emplacements d’installation par défaut, comme ceci risque de perturber le flux de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="fd040-123">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="fd040-124">Trop ancienne une version empêchera finira par les utilisateurs d’accéder au service.</span><span class="sxs-lookup"><span data-stu-id="fd040-124">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="fd040-125">Exigences pour l’ordinateur cible</span><span class="sxs-lookup"><span data-stu-id="fd040-125">Target computer requirements</span></span>

- <span data-ttu-id="fd040-126">.NET framework 4.5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="fd040-126">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="fd040-127">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="fd040-127">Windows 7 or later</span></span>
- <span data-ttu-id="fd040-128">3 Go d’espace disque requis pour chaque profil utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="fd040-128">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="fd040-129">Nettoyage et procédure redéploiement</span><span class="sxs-lookup"><span data-stu-id="fd040-129">Clean up and redeployment procedure</span></span>
<span data-ttu-id="fd040-130">Si un utilisateur désinstalle des équipes de leur profil utilisateur, le programme d’installation MSI effectue le suivi que l’utilisateur a désinstallé l’application équipes et n’est plus installer équipes pour ce profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd040-130">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="fd040-131">Pour redéployer les équipes pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fd040-131">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="fd040-132">Désinstallation d’une application d’équipes installé pour chaque profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd040-132">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="fd040-133">Après la désinstallation, supprimez le répertoire de manière récursive sous % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="fd040-133">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="fd040-134">Redéployer le package MSI sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fd040-134">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="fd040-135">Vous pouvez utiliser notre script de [déploiement des équipes Microsoft nettoyer](scripts/Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="fd040-135">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="fd040-136">Désactiver le démarrage automatique pour le programme d’installation MSI</span><span class="sxs-lookup"><span data-stu-id="fd040-136">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="fd040-137">Comportement par défaut de MSI consiste à installer le client équipes dès qu’un utilisateur se connecte et puis démarrer automatiquement les équipes.</span><span class="sxs-lookup"><span data-stu-id="fd040-137">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="fd040-138">Vous pouvez modifier ce comportement avec les paramètres ci-dessous comme suit :</span><span class="sxs-lookup"><span data-stu-id="fd040-138">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="fd040-139">Lorsqu’un utilisateur se connecte à Windows, équipes seront installés avec le fichier MSI</span><span class="sxs-lookup"><span data-stu-id="fd040-139">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="fd040-140">Toutefois, le client équipes ne démarrera pas jusqu'à ce que l’utilisateur a démarré manuellement les équipes</span><span class="sxs-lookup"><span data-stu-id="fd040-140">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="fd040-141">Un raccourci pour démarrer des équipes sera ajouté sur le bureau de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="fd040-141">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="fd040-142">Une fois que le démarrage manuel, équipes seront démarrage automatique chaque fois que l’utilisateur se connecte en</span><span class="sxs-lookup"><span data-stu-id="fd040-142">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="fd040-143">Pour la version 32 bits</span><span class="sxs-lookup"><span data-stu-id="fd040-143">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="fd040-144">Pour la version 64 bits</span><span class="sxs-lookup"><span data-stu-id="fd040-144">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```
> [!Note] 
>  <span data-ttu-id="fd040-145">Si vous exécutez manuellement le fichier MSI, veillez à exécuter avec des autorisations élevées.</span><span class="sxs-lookup"><span data-stu-id="fd040-145">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="fd040-146">Même si vous l’exécutez en tant qu’administrateur, sans l’exécuter avec des autorisations élevées, le programme d’installation ne sera pas en mesure de configurer l’option pour désactiver le démarrage automatique.</span><span class="sxs-lookup"><span data-stu-id="fd040-146">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
