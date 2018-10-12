---
title: Installer Microsoft Teams à l’aide de MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Les administrateurs peuvent utiliser le MSI Teams pour déployer en bloc Microsoft Teams pour des utilisateurs ou sur des ordinateurs spécifiques.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d197d431bb08027da27dd7ae61e421c9519aad1
ms.sourcegitcommit: 8a4ed16adc60497510a528784e139075fbae9e55
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "25502197"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="d9cc9-103">Installer Microsoft Teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="d9cc9-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="d9cc9-104">Regarder la session pour en savoir plus sur le Client de bureau Windows, comment planifier et déployer les avantages suivante : [Client de bureau Windows équipes](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="d9cc9-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="d9cc9-105">Pour utiliser System Center Configuration Manager ou la stratégie de groupe ou les mécanismes de distribution de tiers pour le déploiement, Microsoft a fourni les fichiers MSI ( [32 bits](https://aka.ms/teams32bitmsi) et [64 bits](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en bloc des équipes pour sélectionner les utilisateurs ou ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="d9cc9-106">Administrateurs peuvent utiliser ces fichiers pour déployer des équipes à distance afin que les utilisateurs n’ont pas télécharger manuellement l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="d9cc9-107">Lors du déploiement, les équipes automatique de lancement pour tous les utilisateurs qui se connectent à sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="d9cc9-108">(Vous pouvez désactiver lancement automatique après l’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="d9cc9-109">[Voir ci-dessous](#disable-auto-lanuch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs de l’ordinateur bénéficient également ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-109">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="d9cc9-110">Pour en savoir plus sur SCCM, voir [Introduction à System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="d9cc9-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="d9cc9-111">Procédure de déploiement (recommandé)</span><span class="sxs-lookup"><span data-stu-id="d9cc9-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="d9cc9-112">Récupérer le dernier package.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="d9cc9-113">Utilisez les valeurs par défaut préremplies par le fichier MSI.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="d9cc9-114">Déployez sur les ordinateurs lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="d9cc9-115">Comment fonctionne le package Microsoft équipes MSI</span><span class="sxs-lookup"><span data-stu-id="d9cc9-115">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="d9cc9-116">Le fichier MSI équipes place un programme d’installation dans les fichiers de programme.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-116">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="d9cc9-117">Chaque fois qu’un utilisateur se connecte à un nouveau profil d’utilisateur Windows, le programme d’installation est lancé et une copie de l’application des équipes sera installée dans le dossier appdata de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-117">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="d9cc9-118">Si l’utilisateur a déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignore le processus de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-118">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="d9cc9-119">N’utilisez pas le fichier MSI pour déployer des mises à jour, car le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-119">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="d9cc9-120">Pour redéployer le programme d’installation le plus récent utiliser le processus de redéploiement MSI décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-120">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="d9cc9-121">Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-121">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="d9cc9-122">Si une version ancienne très obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-122">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="d9cc9-123">Nous ne pas recommandé de modifier les emplacements d’installation par défaut, comme ceci risque de perturber le flux de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-123">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="d9cc9-124">Trop ancienne une version empêchera finira par les utilisateurs d’accéder au service.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-124">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="d9cc9-125">Exigences pour l’ordinateur cible</span><span class="sxs-lookup"><span data-stu-id="d9cc9-125">Target computer requirements</span></span>

- <span data-ttu-id="d9cc9-126">.NET framework 4.5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="d9cc9-126">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="d9cc9-127">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="d9cc9-127">Windows 7 or later</span></span>
- <span data-ttu-id="d9cc9-128">3 Go d’espace disque requis pour chaque profil utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="d9cc9-128">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="d9cc9-129">Nettoyage et procédure redéploiement</span><span class="sxs-lookup"><span data-stu-id="d9cc9-129">Clean up and redeployment procedure</span></span>
<span data-ttu-id="d9cc9-130">Si un utilisateur désinstalle des équipes de leur profil utilisateur, le programme d’installation MSI effectue le suivi que l’utilisateur a désinstallé l’application équipes et n’est plus installer équipes pour ce profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-130">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="d9cc9-131">Pour redéployer les équipes pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d9cc9-131">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="d9cc9-132">Désinstallation d’une application d’équipes installé pour chaque profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-132">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="d9cc9-133">Après la désinstallation, supprimez le répertoire de manière récursive sous % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-133">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="d9cc9-134">Redéployer le package MSI sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-134">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="d9cc9-135">Vous pouvez utiliser notre script de [déploiement des équipes Microsoft nettoyer](scripts/Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-135">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="d9cc9-136">Désactiver le démarrage automatique pour le programme d’installation MSI</span><span class="sxs-lookup"><span data-stu-id="d9cc9-136">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="d9cc9-137">Si vous souhaitez désactiver le démarrage automatique, entrez l’invite de commandes suivante :</span><span class="sxs-lookup"><span data-stu-id="d9cc9-137">If you want to disable auto launch, enter the following command prompt:</span></span>

```
msiexec /i Teams_windows.exe OPTIONS="noAutoStart=true"
```

