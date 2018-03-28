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
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="ee72c-103">Installation de Teams de Microsoft à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="ee72c-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="ee72c-104">Pour tirer parti de System Center Configuration Manager, ou stratégie de groupe ou les mécanismes de distribution 3ème partie pour le déploiement, Microsoft a fourni des fichiers MSI ( [32 bits](http://aka.ms/teams32bitmsi) et [64 bits](http://aka.ms/teams64bitmsi)) pour les administrateurs d’exploiter lors du déploiement en masse de Teams de Microsoft pour sélectionner les utilisateurs ou les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="ee72c-104">To leverage System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) for admins to leverage during bulk deployment of Microsoft Teams to select users or machines.</span></span> <span data-ttu-id="ee72c-105">Administrateurs peuvent utiliser ces fichiers pour déployer à distance des équipes afin que les utilisateurs ne doivent pas télécharger manuellement l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="ee72c-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="ee72c-106">Lors du déploiement, les équipes seront automatiquement lancement pour tous les utilisateurs qui signe dans sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ee72c-106">When deployed, Teams will auto launch for all users who sign-in on that machine.</span></span> <span data-ttu-id="ee72c-107">Il est recommandé de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs sur les ordinateurs bénéficieront également de ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="ee72c-107">It is recommended that you deploy the package to the machine, so all new users to the machines will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="ee72c-108">Pour en savoir plus à propos de SCCM, reportez-vous à la section.</span><span class="sxs-lookup"><span data-stu-id="ee72c-108">To learn more about SCCM, see.</span></span> [<span data-ttu-id="ee72c-109">Introduction à System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ee72c-109">Introduction to System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a><span data-ttu-id="ee72c-110">Procédure de déploiement (recommandations)</span><span class="sxs-lookup"><span data-stu-id="ee72c-110">Deployment Procedure (Recommendations)</span></span>
1. <span data-ttu-id="ee72c-111">Récupérer le dernier package</span><span class="sxs-lookup"><span data-stu-id="ee72c-111">Retrieve the latest package</span></span>
2. <span data-ttu-id="ee72c-112">Utiliser les paramètres par défaut pré-remplis par le fichier MSI</span><span class="sxs-lookup"><span data-stu-id="ee72c-112">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="ee72c-113">Déploiement sur les machines lorsque cela est possible</span><span class="sxs-lookup"><span data-stu-id="ee72c-113">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="ee72c-114">Fonctionne du package MSI d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee72c-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="ee72c-115">Le fichier MSI d’équipes place un programme d’installation dans les fichiers programme.</span><span class="sxs-lookup"><span data-stu-id="ee72c-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="ee72c-116">Chaque fois qu’un utilisateur signe dans un nouveau profil d’utilisateur de Windows, le programme d’installation est lancé et une copie de l’application des équipes sera installée dans le dossier appdata de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee72c-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="ee72c-117">Si un utilisateur possède déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignorera le processus pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee72c-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="ee72c-118">N’exploitent pas le fichier MSI pour déployer des mises à jour, le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service.</span><span class="sxs-lookup"><span data-stu-id="ee72c-118">Do not leverage the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="ee72c-119">Pour redéployer le programme d’installation les plus récent utilisent le processus de redéploiement de MSI décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ee72c-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="ee72c-120">Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee72c-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="ee72c-121">Si une version très ancienne obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes.</span><span class="sxs-lookup"><span data-stu-id="ee72c-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="ee72c-122">Il est déconseillé de que vous modifiez les emplacements d’installation comme ceci risque de perturber le flux de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="ee72c-122">It's not recommended you change any install locations as this could break the update flow.</span></span> <span data-ttu-id="ee72c-123">Qui puis finalement empêchera les utilisateurs d’accéder au service.</span><span class="sxs-lookup"><span data-stu-id="ee72c-123">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="ee72c-124">Exigences en matière de la machine cible :</span><span class="sxs-lookup"><span data-stu-id="ee72c-124">Target machine requirements:</span></span>

1. <span data-ttu-id="ee72c-125">.NET framework 4.5 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="ee72c-125">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="ee72c-126">Windows 7 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="ee72c-126">Windows 7 or later</span></span>
2. <span data-ttu-id="ee72c-127">32 Go d’espace disque pour chaque profil d’utilisateur (recommandé)</span><span class="sxs-lookup"><span data-stu-id="ee72c-127">32GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-upredeployment-procedure"></a><span data-ttu-id="ee72c-128">Up\redeployment procédure de nettoyage</span><span class="sxs-lookup"><span data-stu-id="ee72c-128">Clean up\redeployment Procedure</span></span>
<span data-ttu-id="ee72c-129">Si un utilisateur désinstalle des équipes à partir de leur profil utilisateur, le programme d’installation MSI suivra que l’utilisateur a désinstallé l’application équipes et qu’il n’est plus installer des équipes pour le profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee72c-129">If a user uninstalls Teams from for their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="ee72c-130">Pour redéployer des équipes pour cet utilisateur sur un ordinateur particulier, où il a été désinstallé vous devrez :</span><span class="sxs-lookup"><span data-stu-id="ee72c-130">To redeploy Teams for this user on a particular machine where it was uninstalled you will need to:</span></span>

1. <span data-ttu-id="ee72c-131">Désinstallation d’une application d’équipes installé pour chaque profil d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ee72c-131">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="ee72c-132">Après la désinstallation, supprimez le répertoire de manière récursive sous %localappdata%\Microsoft\Teams\\</span><span class="sxs-lookup"><span data-stu-id="ee72c-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="ee72c-133">Redéployer le package MSI sur cet ordinateur particulier</span><span class="sxs-lookup"><span data-stu-id="ee72c-133">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="ee72c-134">Vous pouvez tirer parti de notre script de [nettoyage de déploiement d’équipes Microsoft](.\scripts\Powershell-script-teams-deployment-clean-up.md) pour réaliser ces étapes 1 et 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="ee72c-134">You can leverage our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish this steps 1 and 2 via SCCM.</span></span>                                

