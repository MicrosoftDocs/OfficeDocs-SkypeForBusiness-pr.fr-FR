---
title: Installation de Teams de Microsoft à l’aide de MSI
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Les administrateurs peuvent utiliser le fichier MSI d’équipes en bloc déployer Microsoft Teams pour sélectionner les utilisateurs ou ordinateurs.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8d1f8b77b4b362b95fb03d3f0202bfc6da619e8
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="b3ca2-103">Installation de Teams de Microsoft à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="b3ca2-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="b3ca2-104">Pour utiliser System Center Configuration Manager, ou stratégie de groupe ou les mécanismes de distribution 3ème partie pour le déploiement, Microsoft a fourni des fichiers MSI ( [32 bits](http://aka.ms/teams32bitmsi) et [64 bits](http://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en masse des équipes pour sélectionner les utilisateurs ou ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-104">To use System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or machines.</span></span> <span data-ttu-id="b3ca2-105">Administrateurs peuvent utiliser ces fichiers pour déployer à distance des équipes afin que les utilisateurs ne doivent pas télécharger manuellement l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="b3ca2-106">Lors du déploiement, les équipes seront automatiquement lancement pour tous les utilisateurs qui s’inscrivent sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="b3ca2-107">Nous vous recommandons de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs de la machine bénéficieront également de ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-107">We recommend that you deploy the package to the machine, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="b3ca2-108">Pour en savoir plus à propos de SCCM, consultez [Introduction à System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="b3ca2-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="b3ca2-109">Procédure de déploiement (recommandé)</span><span class="sxs-lookup"><span data-stu-id="b3ca2-109">Deployment Procedure (Recommended)</span></span>
1. <span data-ttu-id="b3ca2-110">Récupérer le dernier package</span><span class="sxs-lookup"><span data-stu-id="b3ca2-110">Retrieve the latest package</span></span>
2. <span data-ttu-id="b3ca2-111">Utiliser les paramètres par défaut pré-remplis par le fichier MSI</span><span class="sxs-lookup"><span data-stu-id="b3ca2-111">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="b3ca2-112">Déploiement sur les machines lorsque cela est possible</span><span class="sxs-lookup"><span data-stu-id="b3ca2-112">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="b3ca2-113">Fonctionne du package MSI d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="b3ca2-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="b3ca2-114">Le fichier MSI d’équipes place un programme d’installation dans les fichiers programme.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="b3ca2-115">Chaque fois qu’un utilisateur signe dans un nouveau profil d’utilisateur de Windows, le programme d’installation est lancé et une copie de l’application d’équipes sera installée dans le dossier appdata de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="b3ca2-116">Si un utilisateur possède déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignorera le processus pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="b3ca2-117">N’utilisez pas le fichier MSI pour déployer des mises à jour, le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-117">Do not use the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="b3ca2-118">Pour redéployer le programme d’installation les plus récent utilisent le processus de redéploiement de MSI décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="b3ca2-119">Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="b3ca2-120">Si une version très ancienne obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="b3ca2-121">Nous ne pas recommandé de modifier les emplacements d’installation par défaut, car ceci risque de perturber le flux de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="b3ca2-122">Trop ancienne une version sera finalement empêcher les utilisateurs d’accéder au service.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="b3ca2-123">Exigences en matière de la machine cible</span><span class="sxs-lookup"><span data-stu-id="b3ca2-123">Target machine requirements</span></span>

1. <span data-ttu-id="b3ca2-124">.NET framework 4.5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b3ca2-124">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="b3ca2-125">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b3ca2-125">Windows 7 or later</span></span>
2. <span data-ttu-id="b3ca2-126">3 Go d’espace disque pour chaque profil d’utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="b3ca2-126">3GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="b3ca2-127">Nettoyage à distance et la procédure de redéploiement</span><span class="sxs-lookup"><span data-stu-id="b3ca2-127">Clean up and redeployment Procedure</span></span>
<span data-ttu-id="b3ca2-128">Si un utilisateur désinstalle des équipes à partir de leur profil utilisateur, le programme d’installation MSI suivra que l’utilisateur a désinstallé l’application équipes et qu’il n’est plus installer des équipes pour le profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="b3ca2-129">Pour redéployer des équipes pour cet utilisateur sur un ordinateur particulier, où il a été désinstallé, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3ca2-129">To redeploy Teams for this user on a particular machine where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="b3ca2-130">Désinstallation d’une application d’équipes installé pour chaque profil d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b3ca2-130">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="b3ca2-131">Après la désinstallation, supprimez le répertoire de manière récursive sous %localappdata%\Microsoft\Teams\\</span><span class="sxs-lookup"><span data-stu-id="b3ca2-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="b3ca2-132">Redéployer le package MSI sur cet ordinateur particulier</span><span class="sxs-lookup"><span data-stu-id="b3ca2-132">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="b3ca2-133">Vous pouvez utiliser notre script de [nettoyage de déploiement des équipes de Microsoft](.\scripts\Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="b3ca2-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

