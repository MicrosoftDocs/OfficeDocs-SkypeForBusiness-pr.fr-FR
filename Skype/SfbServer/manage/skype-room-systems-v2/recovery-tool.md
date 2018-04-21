---
title: Utiliser l’outil de récupération de systèmes de salle Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: Cet article explique comment utiliser l’outil de récupération pour systèmes de salle Skype v2, ce qui permet de mettre un système obsolète dans un état pris en charge.
ms.openlocfilehash: 7c7a6188ec1cbd1153c09b768e81789fcffd266e
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="e3c27-103">Utiliser l’outil de récupération de systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="e3c27-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="e3c27-104">Cet article explique comment utiliser l’outil de récupération pour systèmes de salle Skype v2, ce qui permet de mettre un système obsolète dans un état pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e3c27-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="e3c27-105">Vous utilisez cet outil lorsque la console de v2 Skype salle systèmes affiche une erreur « la configuration système obsolète ».</span><span class="sxs-lookup"><span data-stu-id="e3c27-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="e3c27-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="e3c27-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="e3c27-107">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e3c27-107">Prerequisites</span></span>

<span data-ttu-id="e3c27-108">Téléchargez le dernier [package d’installation de systèmes de salle Skype v2](https://go.microsoft.com/fwlink/?linkid=851168) et extrayez-le sur un USB mémoire stick ou un partage réseau accessible au périphérique v2 systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="e3c27-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="e3c27-109">Vous devez également installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="e3c27-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="e3c27-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="e3c27-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="e3c27-111">Vérifier la Version de Windows</span><span class="sxs-lookup"><span data-stu-id="e3c27-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="e3c27-112">Connexion à un compte d’administrateur à partir de **Paramètres > Paramètres Windows > Admin signe dans** à partir du périphérique de v2 de systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="e3c27-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="e3c27-113">Cette option affiche l’écran de connexion.</span><span class="sxs-lookup"><span data-stu-id="e3c27-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="e3c27-114">Connexion à un compte d’administrateur, l’administrateur par défaut compte étant `admin` avec le mot de passe `sfb`.</span><span class="sxs-lookup"><span data-stu-id="e3c27-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="e3c27-115">Cliquez sur le menu Démarrer et le type `winver.exe` dans la zone de recherche et cliquez sur \**Commande Exécuter* dans le résultat.</span><span class="sxs-lookup"><span data-stu-id="e3c27-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="e3c27-116">Notez le numéro après 'Version' sur la deuxième ligne du volet d’informations.</span><span class="sxs-lookup"><span data-stu-id="e3c27-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="e3c27-117">Si la Version indiquée est 1607 ou version antérieure, suivez les étapes de la procédure de <a href="#Windows-up">Mise à jour de Windows avant la restauration</a> avant de poursuivre les étapes à <a href="#Perform">effectuer une restauration</a> .</span><span class="sxs-lookup"><span data-stu-id="e3c27-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="e3c27-118">Si la Version indiquée est supérieure à 1607, suivez uniquement les étapes de <a href="#Perform">effectuer une restauration</a>.</span><span class="sxs-lookup"><span data-stu-id="e3c27-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="e3c27-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="e3c27-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="e3c27-120">Mise à jour de Windows avant la restauration (si nécessaire)</span><span class="sxs-lookup"><span data-stu-id="e3c27-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="e3c27-121">Bien que toujours connecté tant qu’utilisateur admin, lancez une invite de commandes avec élévation de privilèges Powershell.</span><span class="sxs-lookup"><span data-stu-id="e3c27-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="e3c27-122">Exécutez la commande `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="e3c27-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="e3c27-123">Exécutez Windows Update et installer la mise à jour pour Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="e3c27-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="e3c27-124">Une fois la mise à jour 1709 signe complète dans admin compte et installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="e3c27-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="e3c27-125">La mise à jour peut être effectuée à partir du lien ou à l’aide de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e3c27-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="e3c27-126">Une étape facultative, installer les mises à jour supplémentaires disponibles à partir de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e3c27-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="e3c27-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="e3c27-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="e3c27-128">Effectuer une restauration</span><span class="sxs-lookup"><span data-stu-id="e3c27-128">Perform a recovery</span></span>

1. <span data-ttu-id="e3c27-129">Connectez-vous au compte administrateur sur votre appareil v2 de systèmes de salle Skype et lancer une invite de commandes avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="e3c27-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="e3c27-130">Vérifiez à partir du périphérique de v2 Skype salle systèmes que vous ne pouvez accéder à la `RecoveryTool.ps1` fichier, ce qui est inclus dans les fichiers extraits à partir du package d’installation de systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="e3c27-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="e3c27-131">Vous trouverez le kit sur le partage réseau ou un lecteur USB utilisé lors de la préparation des conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="e3c27-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="e3c27-132">Exécutez la commande Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="e3c27-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="e3c27-133">Lorsque vous y êtes invité par l’option de sélection de script `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="e3c27-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="e3c27-134">À la fin, redémarrez le périphérique v2 de systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="e3c27-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="e3c27-135">Il redémarre à nouveau automatiquement et élaborer totalement récupéré la deuxième fois.</span><span class="sxs-lookup"><span data-stu-id="e3c27-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="e3c27-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="e3c27-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="e3c27-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e3c27-137">See also</span></span>


#### 

[<span data-ttu-id="e3c27-138">Gérer l’espace de Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="e3c27-138">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
#### 
