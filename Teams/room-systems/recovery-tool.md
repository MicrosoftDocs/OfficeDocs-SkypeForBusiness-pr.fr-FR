---
title: Utiliser l’outil de récupération de Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge.
ms.openlocfilehash: 79cdd7b2e3530570033083bdac7089e862f169ce
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909460"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="d0c3e-103">Utiliser l’outil de récupération de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="d0c3e-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="d0c3e-104">Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="d0c3e-105">Cet outil doit être appliqué lorsque le message d’erreur « configuration système obsolète » est affiché sur la console de Microsoft Teams, ou avant de procéder à la réinitialisation de la [restauration en usine](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore).</span><span class="sxs-lookup"><span data-stu-id="d0c3e-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0c3e-106">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="d0c3e-106">Prerequisites</span></span>

<span data-ttu-id="d0c3e-107">Téléchargez le dernier [package d’installation de Microsoft teams](https://go.microsoft.com/fwlink/?linkid=851168) , puis récupérez-le sur une clé USB ou un partage réseau accessible à partir de l’appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="d0c3e-108">L’extraction des fichiers à partir du MSI peut être effectuée de diverses manières.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="d0c3e-109">Tout mécanisme qui extrait tous les fichiers et conserve leur structure d’annuaire est acceptable.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="d0c3e-110">Par exemple, vous pouvez utiliser la commande `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` où `PathToMsi` correspond au chemin d’accès complet au package d’installation de Microsoft Teams, puis `PathToTarget` correspond au chemin d’accès complet au dossier dans lequel vous voulez extraire les fichiers.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-110">One such way is to use the command `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="d0c3e-111">Exécution de l’outil</span><span class="sxs-lookup"><span data-stu-id="d0c3e-111">Running the tool</span></span>

1) <span data-ttu-id="d0c3e-112">Connectez-vous au compte d’administrateur sur votre appareil Microsoft Teams, puis lancez une invite de commandes avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="d0c3e-113">Vérifiez à partir de l’appareil Microsoft teams qui vous permet d’accéder `RecoveryTool.ps1 file`à la version incluse dans les fichiers extraits du programme d’installation de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="d0c3e-114">Le kit est disponible sur le partage réseau ou sur le lecteur USB utilisé pour préparer les éléments requis.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="d0c3e-115">Exécuter `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="d0c3e-116">Si vous effectuez une restauration en usine :</span><span class="sxs-lookup"><span data-stu-id="d0c3e-116">If you are performing a factory restore:</span></span>
   - <span data-ttu-id="d0c3e-117">Lorsque vous y êtes invité par le script, sélectionnez l’option 2 : **Reset**.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-117">When prompted by the script select option 2: **Reset**.</span></span>
   - <span data-ttu-id="d0c3e-118">Si BitLocker est activé, suivez les instructions fournies à la fin de la sortie du script pour le désactiver.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   - <span data-ttu-id="d0c3e-119">Effectuez la restauration en usine.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-119">Perform the factory restore.</span></span>
      - <span data-ttu-id="d0c3e-120">Ouvrez l’application **paramètres** , puis sélectionnez **mettre à jour les & sécurité**</span><span class="sxs-lookup"><span data-stu-id="d0c3e-120">Open the **Settings** app, and select **Update & Security**</span></span>
      - <span data-ttu-id="d0c3e-121">Accédez à l’onglet **récupération** .</span><span class="sxs-lookup"><span data-stu-id="d0c3e-121">Navigate to the **Recovery** tab.</span></span>
      - <span data-ttu-id="d0c3e-122">Sous **réinitialiser ce PC**, sélectionnez **commencer** .</span><span class="sxs-lookup"><span data-stu-id="d0c3e-122">Beneath **Reset this PC**, select **Get started**</span></span>
      - <span data-ttu-id="d0c3e-123">Sélectionnez **Supprimer tout**, puis **suivant** et **Réinitialiser**</span><span class="sxs-lookup"><span data-stu-id="d0c3e-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
      - <span data-ttu-id="d0c3e-124">Le système redémarre à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-124">The system will reboot multiple times.</span></span> <span data-ttu-id="d0c3e-125">Lorsque le rétablissement est terminé, le système se trouve sur l’écran OOBE Windows.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-125">When the reset is complete, the system will be at the Windows OOBE screen.</span></span>
5) <span data-ttu-id="d0c3e-126">Si vous réparez un système à jour :</span><span class="sxs-lookup"><span data-stu-id="d0c3e-126">If you are repairing an "out of date" system:</span></span>
    - <span data-ttu-id="d0c3e-127">Lorsque vous y êtes invité par le script, sélectionnez option 1 : **réparer**.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-127">When prompted by the script select option 1: **Repair**.</span></span>
    - <span data-ttu-id="d0c3e-128">Lorsque vous avez terminé, redémarrez l’appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-128">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d0c3e-129">Elle redémarrera automatiquement et sera entièrement récupérée la deuxième fois.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-129">It will reboot again automatically and come up fully recovered the second time.</span></span>

> [!NOTE]
> <span data-ttu-id="d0c3e-130">Il existe un problème connu pour lequel les salles de Microsoft teams peuvent être désactivées si l’option **conserver mes fichiers-supprime des applications et des paramètres, mais** que vous avez sélectionné l’option conservation de vos fichiers personnels lors du processus de réinitialisation de Windows.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-130">There is a known issue where the Microsoft Teams Rooms can become unusable if the  **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="d0c3e-131">N’utilisez *pas* cette option.</span><span class="sxs-lookup"><span data-stu-id="d0c3e-131">Do *not* use this option.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0c3e-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d0c3e-132">See also</span></span>

[<span data-ttu-id="d0c3e-133">Aide Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="d0c3e-133">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="d0c3e-134">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="d0c3e-134">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
