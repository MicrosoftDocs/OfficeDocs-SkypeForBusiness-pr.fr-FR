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
description: Cet article explique comment utiliser l’outil de récupération pour les systèmes de salle Skype v2, que vous utilisez pour intégrer un système obsolète à un état pris en charge.
ms.openlocfilehash: 63deb332a520a0752242140f85f200a160eefe0d
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="c4ed4-103">Utiliser l’outil de récupération de systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="c4ed4-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="c4ed4-104">Cet article explique comment utiliser l’outil de récupération pour les systèmes de salle Skype v2, que vous utilisez pour intégrer un système obsolète à un état pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="c4ed4-105">Vous utiliserez cet outil lorsque la console de v2 Skype salle systèmes indique une erreur « configuration de système obsolète ».</span><span class="sxs-lookup"><span data-stu-id="c4ed4-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="c4ed4-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="c4ed4-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="c4ed4-107">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="c4ed4-107">Prerequisites</span></span>

<span data-ttu-id="c4ed4-108">Télécharger le dernier [package d’installation de systèmes de salle Skype v2](https://go.microsoft.com/fwlink/?linkid=851168) et extrayez-le sur un USB mémoire module ou un partage réseau accessible à l’appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="c4ed4-109">Vous devez également installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="c4ed4-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="c4ed4-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="c4ed4-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="c4ed4-111">Vérifier la Version de Windows</span><span class="sxs-lookup"><span data-stu-id="c4ed4-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="c4ed4-112">Connexion à un compte d’administrateur en accédant à **Paramètres > Paramètres Windows > Admin Sign In** à partir de l’appareil v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="c4ed4-113">Cette option affiche l’écran de connexion.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="c4ed4-114">Compte de la connexion à un compte d’administration, l’administrateur par défaut est `admin` avec le mot de passe `sfb`.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="c4ed4-115">Cliquez sur le menu Démarrer et le type `winver.exe` dans la zone de recherche et cliquez sur \* le résultat de la*Commande Exécuter* .</span><span class="sxs-lookup"><span data-stu-id="c4ed4-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="c4ed4-116">Notez le numéro après « Version » sur la deuxième ligne du volet d’informations.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="c4ed4-117">Si la Version indiquée est 1607 ou une version antérieure, suivez les étapes dans les étapes de <a href="#Windows-up">Mise à jour Windows avant de récupération</a> avant de commencer les étapes à <a href="#Perform">effectuer une récupération</a> .</span><span class="sxs-lookup"><span data-stu-id="c4ed4-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="c4ed4-118">Si la Version indiquée est supérieure à 1607, suivez uniquement les étapes dans <a href="#Perform">effectuer une récupération</a>.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="c4ed4-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="c4ed4-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="c4ed4-120">Mettre à jour Windows avant récupération (si nécessaire)</span><span class="sxs-lookup"><span data-stu-id="c4ed4-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="c4ed4-121">Alors que toujours connecté en tant qu’utilisateur admin, lancez une invite de commandes Powershell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="c4ed4-122">Exécutez la commande `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="c4ed4-123">Exécutez Windows Update et installez la mise à jour pour Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="c4ed4-124">Une fois la mise à jour 1709 connexion complète dans le compte d’administrateur et installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="c4ed4-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="c4ed4-125">La mise à jour peut être effectuée à partir du lien ou à l’aide de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="c4ed4-126">Comme une étape facultative, installez les mises à jour supplémentaires disponibles à partir de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="c4ed4-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="c4ed4-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="c4ed4-128">Effectuer une récupération</span><span class="sxs-lookup"><span data-stu-id="c4ed4-128">Perform a recovery</span></span>

1. <span data-ttu-id="c4ed4-129">Se connecter au compte d’administrateur sur votre appareil v2 de systèmes de salle Skype et lancez une invite de commandes avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="c4ed4-130">Vérifiez de l’appareil v2 de systèmes de salle Skype que vous êtes en mesure d’accéder à la `RecoveryTool.ps1` fichier, qui est inclus dans les fichiers extraits à partir du package d’installation v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="c4ed4-131">Le kit se trouvent sur le partage réseau ou d’une clé USB utilisé lors de la préparation des conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="c4ed4-132">Exécutez la commande Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="c4ed4-133">Lorsque vous êtes invité à l’option select script `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="c4ed4-134">Une fois terminée, redémarrez l’équipement de v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="c4ed4-135">Il redémarre automatiquement et élaborer entièrement récupérée la deuxième fois.</span><span class="sxs-lookup"><span data-stu-id="c4ed4-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="c4ed4-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="c4ed4-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="c4ed4-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4ed4-137">See also</span></span>


#### 
[<span data-ttu-id="c4ed4-138">Systèmes de salle Skype version 2</span><span class="sxs-lookup"><span data-stu-id="c4ed4-138">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="c4ed4-139">Gérer les salles Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="c4ed4-139">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
