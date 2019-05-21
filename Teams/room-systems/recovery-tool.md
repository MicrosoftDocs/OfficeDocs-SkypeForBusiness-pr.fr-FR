---
title: Utiliser l’outil de récupération de Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge.
ms.openlocfilehash: cbfb3ef1ec033389894b3b7479e454160dc77b1b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305483"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="fd37f-103">Utiliser l’outil de récupération de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fd37f-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="fd37f-104">Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge.</span><span class="sxs-lookup"><span data-stu-id="fd37f-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="fd37f-105">Vous pouvez utiliser cet outil lorsque le message d’erreur «configuration système obsolète» s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fd37f-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="fd37f-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="fd37f-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="fd37f-107">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="fd37f-107">Prerequisites</span></span>

<span data-ttu-id="fd37f-108">Téléchargez le dernier [package d’installation de Microsoft teams](https://go.microsoft.com/fwlink/?linkid=851168) , puis récupérez-le sur une clé USB ou un partage réseau accessible à partir de l’appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd37f-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="fd37f-109">Vous devrez également installer [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="fd37f-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="fd37f-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="fd37f-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="fd37f-111">Vérifier la version de Windows</span><span class="sxs-lookup"><span data-stu-id="fd37f-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="fd37f-112">Connectez-vous à un compte d’administrateur en accédant à **Settings> Windows Setting> admin Connectez-vous** à partir de l’appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd37f-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="fd37f-113">Cette option vous permet d’accéder à l’écran de connexion.</span><span class="sxs-lookup"><span data-stu-id="fd37f-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="fd37f-114">Connectez-vous à un compte d’administrateur, `admin` à l’aide du compte `sfb`d’administrateur par défaut et du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="fd37f-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="fd37f-115">Cliquez sur le menu Démarrer, puis `winver.exe` tapez dans la zone de recherche et cliquez sur la*commande + exécuter* du résultat.</span><span class="sxs-lookup"><span data-stu-id="fd37f-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="fd37f-116">Notez le numéro après «version» dans la deuxième ligne du volet d’informations.</span><span class="sxs-lookup"><span data-stu-id="fd37f-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="fd37f-117">Si la version présentée est 1607 ou une version antérieure, suivez les étapes de la procédure de <a href="#Windows-up">mise à jour de Windows avant la récupération</a> avant de procéder à la <a href="#Perform">récupération</a> .</span><span class="sxs-lookup"><span data-stu-id="fd37f-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="fd37f-118">Si la version présentée est supérieure à 1607, procédez comme suit pour <a href="#Perform">effectuer une récupération</a>.</span><span class="sxs-lookup"><span data-stu-id="fd37f-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="fd37f-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="fd37f-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="fd37f-120">Mise à jour de Windows avant la récupération (si nécessaire)</span><span class="sxs-lookup"><span data-stu-id="fd37f-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="fd37f-121">Quand vous êtes connecté en tant qu’administrateur, lancez une invite PowerShell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="fd37f-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="fd37f-122">Exécutez la commande `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="fd37f-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="fd37f-123">Exécutez Windows Update et installez la mise à jour pour Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="fd37f-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="fd37f-124">À l’issue de la mise à jour vers 1709, reconnectez-vous au compte d’administrateur, puis installez [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="fd37f-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="fd37f-125">La mise à jour est possible à partir du lien ou à l’aide de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="fd37f-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="fd37f-126">Installez éventuellement des mises à jour supplémentaires disponibles à partir de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="fd37f-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="fd37f-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="fd37f-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="fd37f-128">Effectuer une récupération</span><span class="sxs-lookup"><span data-stu-id="fd37f-128">Perform a recovery</span></span>

1. <span data-ttu-id="fd37f-129">Connectez-vous au compte d’administrateur sur votre appareil Microsoft Teams, puis lancez une invite de commandes avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="fd37f-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="fd37f-130">Vérifiez à partir de l’appareil de Microsoft teams que vous êtes en `RecoveryTool.ps1` mesure d’accéder au fichier, qui est inclus dans les fichiers extraits du package d’installation de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd37f-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="fd37f-131">Le kit est disponible sur le partage réseau ou sur le lecteur USB utilisé pour préparer les éléments requis.</span><span class="sxs-lookup"><span data-stu-id="fd37f-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="fd37f-132">Exécutez la commande `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="fd37f-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="fd37f-133">Lorsque vous y êtes invité par l’option `1:"Repair System"`de sélection de script.</span><span class="sxs-lookup"><span data-stu-id="fd37f-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="fd37f-134">Lorsque vous avez terminé, redémarrez l’appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd37f-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="fd37f-135">Elle redémarrera automatiquement et sera entièrement récupérée la deuxième fois.</span><span class="sxs-lookup"><span data-stu-id="fd37f-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="fd37f-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="fd37f-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="fd37f-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fd37f-137">See also</span></span>
 
[<span data-ttu-id="fd37f-138">Aide Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fd37f-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="fd37f-139">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fd37f-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
