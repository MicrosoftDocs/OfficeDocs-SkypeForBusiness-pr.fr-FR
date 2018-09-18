---
title: Installer Microsoft Teams à l’aide de MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Les administrateurs peuvent utiliser le MSI Teams pour déployer en bloc Microsoft Teams pour des utilisateurs ou sur des ordinateurs spécifiques.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882037"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="a3318-103">Installer Microsoft Teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="a3318-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="a3318-104">Pour utiliser System Center Configuration Manager, une stratégie de groupe ou d’autres mécanismes de distribution tiers pour un déploiement à grande échelle, Microsoft a fourni des fichiers MSI ([32 bits](https://aka.ms/teams32bitmsi) et [64 bits](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour déployer Teams en bloc pour des utilisateurs ou sur des ordinateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a3318-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="a3318-105">Les administrateurs peuvent utiliser ces fichiers pour déployer Teams à distance, afin que les utilisateurs n’aient pas à télécharger l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="a3318-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="a3318-106">Une fois déployée, l’application Teams se lancera automatiquement pour tous les utilisateurs qui se connectent sur cette machine.</span><span class="sxs-lookup"><span data-stu-id="a3318-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="a3318-107">Nous vous recommandons de déployer le package sur l’ordinateur pour que tous les nouveaux utilisateurs de celui-ci bénéficient également de ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="a3318-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="a3318-108">Pour en savoir plus sur SCCM, reportez-vous à la section [Présentation de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="a3318-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="a3318-109">Procédure de déploiement (recommandée)</span><span class="sxs-lookup"><span data-stu-id="a3318-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="a3318-110">Récupérez le package le plus récent.</span><span class="sxs-lookup"><span data-stu-id="a3318-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="a3318-111">Utilisez les paramètres par défaut préremplis par le MSI.</span><span class="sxs-lookup"><span data-stu-id="a3318-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="a3318-112">Effectuez le déploiement sur les ordinateurs lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="a3318-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="a3318-113">Fonctionnement du package MSI Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3318-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="a3318-114">Le MSI Teams placera un programme d'installation dans les fichiers programmes.</span><span class="sxs-lookup"><span data-stu-id="a3318-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="a3318-115">Lorsqu'un utilisateur se connectera avec un nouveau profil d’utilisateur Windows, le programme d'installation sera lancé et une copie de l’application Teams sera installée dans le dossier des données d’application de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3318-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="a3318-116">Si un utilisateur dispose déjà de l’application Teams installée dans le dossier des données d’application, le programme d'installation MSI ignorera le processus pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3318-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="a3318-117">N’utilisez pas le MSI pour déployer des mises à jour, car le client se mettra à jour automatiquement lorsqu'il détectera qu’une nouvelle version est disponible depuis le service.</span><span class="sxs-lookup"><span data-stu-id="a3318-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="a3318-118">Pour redéployer le programme d'installation le plus récent, utilisez le processus de redéploiement de MSI décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a3318-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="a3318-119">Si vous déployez une version plus ancienne du package MSI, le client se mettra à jour automatiquement lorsque cela sera possible pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3318-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="a3318-120">Si une version très ancienne est déployée, le MSI déclenchera une mise à jour de l’application avant que l’utilisateur puisse utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="a3318-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="a3318-121">Nous vous conseillons de ne pas modifier les emplacements d’installation par défaut, car cela risquerait d’interrompre le flux de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a3318-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="a3318-122">Une version trop ancienne empêchera les utilisateurs d’accéder au service.</span><span class="sxs-lookup"><span data-stu-id="a3318-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="a3318-123">Configuration requise pour les ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="a3318-123">Target computer requirements</span></span>

- <span data-ttu-id="a3318-124">.NET Framework 4.5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="a3318-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="a3318-125">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="a3318-125">Windows 7 or later</span></span>
- <span data-ttu-id="a3318-126">3 Go d’espace disque pour chaque profil d’utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="a3318-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="a3318-127">Procédure de nettoyage et de redéploiement</span><span class="sxs-lookup"><span data-stu-id="a3318-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="a3318-128">Si un utilisateur désinstalle Teams de son profil d’utilisateur, le programme d'installation MSI enregistrera que l’utilisateur a désinstallé l’application Teams et ne l’installera plus pour ce profil d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3318-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="a3318-129">Pour redéployer Teams pour cet utilisateur sur un ordinateur spécifique sur lequel il a été désinstallé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a3318-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="a3318-130">Désinstallez l’application Teams installée pour chaque profil d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3318-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="a3318-131">Ensuite, supprimez le répertoire de manière récursive sous %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="a3318-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="a3318-132">Redéployez le package MSI sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a3318-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="a3318-133">Vous pouvez utiliser notre script de [nettoyage du déploiement de Microsoft Teams](.\scripts\Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="a3318-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

