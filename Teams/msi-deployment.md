---
title: Installer Microsoft Teams à l’aide de MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Les administrateurs peuvent utiliser le fichier MSI d’équipes en bloc déployer Microsoft Teams pour sélectionner des utilisateurs ou des ordinateurs.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882037"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="378ee-103">Installer Microsoft Teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="378ee-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="378ee-104">Pour utiliser System Center Configuration Manager ou la stratégie de groupe ou les mécanismes de distribution de tiers pour le déploiement, Microsoft a fourni les fichiers MSI ( [32 bits](https://aka.ms/teams32bitmsi) et [64 bits](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en bloc des équipes pour sélectionner les utilisateurs ou ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="378ee-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="378ee-105">Administrateurs peuvent utiliser ces fichiers pour déployer des équipes à distance afin que les utilisateurs n’ont pas télécharger manuellement l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="378ee-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="378ee-106">Lors du déploiement, les équipes automatique de lancement pour tous les utilisateurs qui se connectent à sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="378ee-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="378ee-107">Nous vous recommandons de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs de l’ordinateur bénéficient également ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="378ee-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="378ee-108">Pour en savoir plus sur SCCM, voir [Introduction à System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="378ee-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="378ee-109">Procédure de déploiement (recommandé)</span><span class="sxs-lookup"><span data-stu-id="378ee-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="378ee-110">Récupérer le dernier package.</span><span class="sxs-lookup"><span data-stu-id="378ee-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="378ee-111">Utilisez les valeurs par défaut préremplies par le fichier MSI.</span><span class="sxs-lookup"><span data-stu-id="378ee-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="378ee-112">Déployez sur les ordinateurs lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="378ee-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="378ee-113">Comment fonctionne le package Microsoft équipes MSI</span><span class="sxs-lookup"><span data-stu-id="378ee-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="378ee-114">Le fichier MSI équipes place un programme d’installation dans les fichiers de programme.</span><span class="sxs-lookup"><span data-stu-id="378ee-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="378ee-115">Chaque fois qu’un utilisateur se connecte à un nouveau profil d’utilisateur Windows, le programme d’installation est lancé et une copie de l’application des équipes sera installée dans le dossier appdata de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="378ee-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="378ee-116">Si l’utilisateur a déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignore le processus de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="378ee-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="378ee-117">N’utilisez pas le fichier MSI pour déployer des mises à jour, car le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service.</span><span class="sxs-lookup"><span data-stu-id="378ee-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="378ee-118">Pour redéployer le programme d’installation le plus récent utiliser le processus de redéploiement MSI décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="378ee-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="378ee-119">Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="378ee-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="378ee-120">Si une version ancienne très obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes.</span><span class="sxs-lookup"><span data-stu-id="378ee-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="378ee-121">Nous ne pas recommandé de modifier les emplacements d’installation par défaut, comme ceci risque de perturber le flux de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="378ee-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="378ee-122">Trop ancienne une version empêchera finira par les utilisateurs d’accéder au service.</span><span class="sxs-lookup"><span data-stu-id="378ee-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="378ee-123">Exigences pour l’ordinateur cible</span><span class="sxs-lookup"><span data-stu-id="378ee-123">Target computer requirements</span></span>

- <span data-ttu-id="378ee-124">.NET framework 4.5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="378ee-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="378ee-125">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="378ee-125">Windows 7 or later</span></span>
- <span data-ttu-id="378ee-126">3 Go d’espace disque requis pour chaque profil utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="378ee-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="378ee-127">Nettoyage et procédure redéploiement</span><span class="sxs-lookup"><span data-stu-id="378ee-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="378ee-128">Si un utilisateur désinstalle des équipes de leur profil utilisateur, le programme d’installation MSI effectue le suivi que l’utilisateur a désinstallé l’application équipes et n’est plus installer équipes pour ce profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="378ee-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="378ee-129">Pour redéployer les équipes pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="378ee-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="378ee-130">Désinstallation d’une application d’équipes installé pour chaque profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="378ee-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="378ee-131">Après la désinstallation, supprimez le répertoire de manière récursive sous % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="378ee-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="378ee-132">Redéployer le package MSI sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="378ee-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="378ee-133">Vous pouvez utiliser notre script de [déploiement des équipes Microsoft nettoyer](.\scripts\Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="378ee-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

