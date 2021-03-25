---
title: Mettre à jour manuellement un appareil Salles Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Découvrez comment mettre à jour manuellement votre appareil Salles Microsoft Teams vers une version spécifique.
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117512"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="6297e-103">Mettre à jour manuellement un appareil Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6297e-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="6297e-104">L’application Salles Microsoft Teams est distribuée via le Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="6297e-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="6297e-105">Les mises à jour de l’application sont installées automatiquement à partir du Microsoft Store pendant la maintenance nocturne. il s’agit de la méthode recommandée pour obtenir des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="6297e-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="6297e-106">Toutefois, dans certaines situations, un appareil Salles Teams ne peut pas recevoir de mises à jour du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="6297e-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="6297e-107">Par exemple, les stratégies de sécurité peuvent ne pas autoriser les appareils à se connecter à Internet ou autoriser le téléchargement d’applications à partir du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="6297e-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="6297e-108">Vous pouvez également mettre à jour un appareil avant d’effectuer l’installation, pendant lequel le Microsoft Store n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="6297e-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="6297e-109">Si vous ne pouvez pas obtenir de mises à jour à partir du Microsoft Store, vous pouvez utiliser une application hors connexion, mettre à jour un script PowerShell pour mettre à jour manuellement vos appareils Salles d’équipe vers une version plus récente de l’application Salles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6297e-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="6297e-110">Suivez les étapes de cet article pour mettre à jour manuellement vos appareils Salles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6297e-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="6297e-111">Ce processus peut uniquement mettre à jour un appareil Salles d’équipe avec l’application Salles d’équipe déjà installée.</span><span class="sxs-lookup"><span data-stu-id="6297e-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="6297e-112">Il ne peut pas être utilisé pour effectuer une nouvelle installation.</span><span class="sxs-lookup"><span data-stu-id="6297e-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="6297e-113">Elle ne permet pas non plus de rétrograder l’application vers une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="6297e-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="6297e-114">Pour effectuer une nouvelle installation de l’application Salles d’équipe, contactez le fabricant de votre appareil pour obtenir des supports spécifiques à celui-ci, ou consultez Préparer le support [d’installation.](console.md#prepare-the-installation-media)</span><span class="sxs-lookup"><span data-stu-id="6297e-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="6297e-115">Étape 1 : télécharger le script de mise à jour de l’application hors connexion</span><span class="sxs-lookup"><span data-stu-id="6297e-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="6297e-116">Tout d’abord, téléchargez la dernière version du script de mise à jour des applications hors connexion.</span><span class="sxs-lookup"><span data-stu-id="6297e-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="6297e-117">Pour télécharger le script, cliquez <https://go.microsoft.com/fwlink/?linkid=2151817> sur .</span><span class="sxs-lookup"><span data-stu-id="6297e-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="6297e-118">Le script est téléchargé dans le dossier téléchargements par défaut sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="6297e-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="6297e-119">Les fichiers téléchargés peuvent être marqués comme bloqués par Windows.</span><span class="sxs-lookup"><span data-stu-id="6297e-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="6297e-120">Si vous avez besoin d’exécuter le script sans interaction, vous devez débloquer le script.</span><span class="sxs-lookup"><span data-stu-id="6297e-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="6297e-121">Pour débloquer le script, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="6297e-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="6297e-122">Cliquez avec le bouton droit sur le fichier dans l’Explorateur de fichiers</span><span class="sxs-lookup"><span data-stu-id="6297e-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="6297e-123">Cliquez sur **Propriétés**</span><span class="sxs-lookup"><span data-stu-id="6297e-123">Click **Properties**</span></span>
3. <span data-ttu-id="6297e-124">Sélectionnez **Débloquer**</span><span class="sxs-lookup"><span data-stu-id="6297e-124">Select **Unblock**</span></span>
4. <span data-ttu-id="6297e-125">Cliquez **sur OK**</span><span class="sxs-lookup"><span data-stu-id="6297e-125">Click **OK**</span></span>

<span data-ttu-id="6297e-126">Pour débloquer le script à l’aide de PowerShell, voir [Débloquer le fichier.](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)</span><span class="sxs-lookup"><span data-stu-id="6297e-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="6297e-127">Une fois le script de mise à jour de l’application hors connexion téléchargé, transférez le fichier vers l’appareil Salles Teams.</span><span class="sxs-lookup"><span data-stu-id="6297e-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="6297e-128">Vous pouvez transférer un fichier sur l’appareil à l’aide d’un lecteur USB ou en accédant au fichier à partir d’un partage de fichiers réseau lorsque vous utilisez le mode d’administration sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6297e-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="6297e-129">N’oubliez pas d’enregistrer le fichier sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6297e-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="6297e-130">Étape 2 : exécuter le script pour mettre à jour l’application Salles Teams</span><span class="sxs-lookup"><span data-stu-id="6297e-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="6297e-131">Le script de mise à jour de l’application hors connexion doit être exécuté à partir d’une invite de commandes avec élévation de élévation de niveau lorsque l’utilisateur de Skype (l’utilisateur sous lequel l’application s’exécute) est toujours connecté.</span><span class="sxs-lookup"><span data-stu-id="6297e-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="6297e-132">Pour plus d’informations sur la connexion à un compte d’administrateur afin d’utiliser l’invite de commandes avec élévation de privilèges lorsque l’utilisateur de Skype est toujours connecté, consultez Passer en mode d’administration et revenir en arrière lorsque l’application Salles Microsoft Teams est en cours [d’exécution.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)</span><span class="sxs-lookup"><span data-stu-id="6297e-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="6297e-133">Pour exécuter le script à partir d’une invite de commandes avec élévation de élévation de niveaux, exécutez l’une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6297e-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="6297e-134">Basculer en mode d’administration</span><span class="sxs-lookup"><span data-stu-id="6297e-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="6297e-135">Cliquez sur l’icône Démarrer, tapez **Invite de commandes,** puis **sélectionnez Exécuter en tant qu’administrateur.**</span><span class="sxs-lookup"><span data-stu-id="6297e-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="6297e-136">Exécutez la commande suivante qui `<path to script>` inclut le chemin d’accès complet au script et le nom du fichier de script :</span><span class="sxs-lookup"><span data-stu-id="6297e-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="6297e-137">Par exemple, si le fichier de script se trouve dans et que le nom du fichier de script est `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` le suivant, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6297e-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="6297e-138">Autorisez l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="6297e-138">Allow the script to run.</span></span> <span data-ttu-id="6297e-139">Une fois terminé, le script redémarrera l’appareil Salles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6297e-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="6297e-140">Vous pouvez également exécuter le script à l’aide de Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6297e-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="6297e-141">Pour plus d’informations sur l’utilisation de Remote PowerShell avec des appareils Teams Rooms, voir [Gestion à distance à l’aide de PowerShell.](rooms-operations.md#remote-management-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="6297e-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="6297e-142">Étape 3 : vérifier que l’application a bien été mise à jour</span><span class="sxs-lookup"><span data-stu-id="6297e-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="6297e-143">Si le script s’exécute correctement, l’appareil redémarrera dans l’application Salles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6297e-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="6297e-144">Si le script rencontre un problème, il indique son problème sur la ligne de commande et enregistre sa sortie dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="6297e-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="6297e-145">Suivez les instructions du script.</span><span class="sxs-lookup"><span data-stu-id="6297e-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="6297e-146">Si vous devez contacter le Support Microsoft, veillez à inclure le fichier journal avec la demande de support.</span><span class="sxs-lookup"><span data-stu-id="6297e-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="6297e-147">Le script vous fournira le chemin d’accès au fichier journal.</span><span class="sxs-lookup"><span data-stu-id="6297e-147">The script will provide you with the path to the log file.</span></span>