---
title: Mettre à jour manuellement un appareil Microsoft teams
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
description: Découvrez comment mettre à jour manuellement votre appareil de salle Microsoft teams avec une version spécifique.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731392"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="ca018-103">Mettre à jour manuellement un appareil Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ca018-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="ca018-104">L’application Microsoft teams salles est distribuée via le Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ca018-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="ca018-105">Les mises à jour apportées à l’application sont installées automatiquement à partir du Microsoft Store lors de la maintenance nocturne ; Il s’agit de la méthode recommandée pour obtenir les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="ca018-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="ca018-106">Toutefois, dans certains cas, un appareil de salle Teams ne peut pas recevoir de mises à jour du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ca018-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="ca018-107">Par exemple, il est possible que les stratégies de sécurité n’autorisent pas les appareils à se connecter à Internet ou ne permettent pas de télécharger des applications à partir du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ca018-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="ca018-108">Vous pouvez également mettre à jour un appareil avant de procéder à l’installation, au cours duquel le Microsoft Store n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="ca018-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="ca018-109">Si vous ne parvenez pas à récupérer des mises à jour à partir de la boutique Microsoft, vous pouvez utiliser un script PowerShell de mise à jour de l’application en mode hors connexion pour mettre à jour manuellement vos périphériques d’équipe sur une nouvelle version de l’application salles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="ca018-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="ca018-110">Suivez les étapes décrites dans cet article pour mettre à jour manuellement vos appareils de salle d’équipe.</span><span class="sxs-lookup"><span data-stu-id="ca018-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="ca018-111">Ce processus ne peut mettre à jour qu’un appareil de salle d’équipe sur lequel l’application salles de teams est déjà installée.</span><span class="sxs-lookup"><span data-stu-id="ca018-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="ca018-112">Il ne peut pas être utilisé pour effectuer une nouvelle installation.</span><span class="sxs-lookup"><span data-stu-id="ca018-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="ca018-113">Il ne peut pas non plus être utilisé pour rétrograder l’application à une version plus ancienne.</span><span class="sxs-lookup"><span data-stu-id="ca018-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="ca018-114">Pour effectuer une nouvelle installation de l’application salles d’équipe, contactez le fabricant de votre appareil pour obtenir du contenu multimédia qui lui est propre ou consultez [préparer le support d’installation](console.md#prepare-the-installation-media).</span><span class="sxs-lookup"><span data-stu-id="ca018-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="ca018-115">Étape 1 : Télécharger le script de mise à jour des applications hors connexion</span><span class="sxs-lookup"><span data-stu-id="ca018-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="ca018-116">Tout d’abord, téléchargez la version la plus récente du script de mise à jour de l’application en mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="ca018-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="ca018-117">Pour télécharger le script, cliquez sur <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="ca018-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="ca018-118">Le script est téléchargé dans le dossier téléchargements par défaut sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="ca018-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="ca018-119">Les fichiers téléchargés peuvent être marqués comme bloqués par Windows.</span><span class="sxs-lookup"><span data-stu-id="ca018-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="ca018-120">Si vous avez besoin d’exécuter le script sans interaction, vous devez débloquer le script.</span><span class="sxs-lookup"><span data-stu-id="ca018-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="ca018-121">Pour débloquer le script, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ca018-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="ca018-122">Cliquez avec le bouton droit sur le fichier dans l’Explorateur de fichiers</span><span class="sxs-lookup"><span data-stu-id="ca018-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="ca018-123">Cliquez sur **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="ca018-123">Click **Properties**</span></span>
3. <span data-ttu-id="ca018-124">Sélectionnez **débloquer** .</span><span class="sxs-lookup"><span data-stu-id="ca018-124">Select **Unblock**</span></span>
4. <span data-ttu-id="ca018-125">Cliquez sur **OK** .</span><span class="sxs-lookup"><span data-stu-id="ca018-125">Click **OK**</span></span>

<span data-ttu-id="ca018-126">Pour débloquer le script à l’aide de PowerShell, voir [Unblock-file](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span><span class="sxs-lookup"><span data-stu-id="ca018-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="ca018-127">Après le téléchargement du script de mise à jour de l’application en mode hors connexion, transférez le fichier vers l’appareil de salle de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="ca018-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="ca018-128">Vous pouvez transférer un fichier vers l’appareil à l’aide d’un lecteur USB ou en accédant au fichier à partir d’un partage de fichiers réseau lorsque le mode administrateur est activé sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ca018-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="ca018-129">Veillez à noter l’emplacement où vous enregistrez le fichier sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ca018-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="ca018-130">Étape 2 : exécuter le script pour mettre à jour l’application salles d’équipe</span><span class="sxs-lookup"><span data-stu-id="ca018-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="ca018-131">Le script de mise à jour de l’application en mode hors connexion doit être exécuté à partir d’une invite de commandes avec élévation de privilèges alors que l’utilisateur de Skype (utilisateur sous lequel l’application s’exécute) est connecté.</span><span class="sxs-lookup"><span data-stu-id="ca018-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="ca018-132">Pour plus d’informations sur la connexion à un compte d’administrateur afin d’utiliser l’invite de commandes avec élévation de privilèges alors que l’utilisateur de Skype est toujours connecté, consultez [basculer vers le mode administrateur et retour lors de l’exécution de l’application Microsoft teams pièces](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span><span class="sxs-lookup"><span data-stu-id="ca018-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="ca018-133">Pour exécuter le script à partir d’une invite de commandes avec élévation de privilèges, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ca018-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="ca018-134">Basculer en mode administrateur</span><span class="sxs-lookup"><span data-stu-id="ca018-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="ca018-135">Cliquez sur l’icône Démarrer, tapez **invite de commandes**, puis sélectionnez **exécuter en tant qu’administrateur** .</span><span class="sxs-lookup"><span data-stu-id="ca018-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="ca018-136">Exécutez la commande suivante qui `<path to script>` inclut le chemin d’accès complet au script et le nom du fichier de script :</span><span class="sxs-lookup"><span data-stu-id="ca018-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="ca018-137">Par exemple, si le fichier de script se trouve dans et que `C:\Users\Admin\Downloads` le nom du fichier de script est `MTR-Update-4.5.6.7.ps1` , exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ca018-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="ca018-138">Autorisez l’exécution du script.</span><span class="sxs-lookup"><span data-stu-id="ca018-138">Allow the script to run.</span></span> <span data-ttu-id="ca018-139">Lorsque vous avez terminé, le script redémarre l’appareil de salle de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="ca018-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="ca018-140">Vous pouvez également exécuter le script à l’aide de Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca018-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="ca018-141">Pour plus d’informations sur l’utilisation de Remote PowerShell avec les appareils de salle d’équipe, voir [gestion à distance à l’aide de PowerShell](rooms-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="ca018-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="ca018-142">Étape 3 : vérifier que l’application a été mise à jour avec succès</span><span class="sxs-lookup"><span data-stu-id="ca018-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="ca018-143">Si le script s’exécute correctement, l’appareil est redémarré dans l’application salles de équipe.</span><span class="sxs-lookup"><span data-stu-id="ca018-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="ca018-144">Si le script rencontre un problème, il indique quel est le problème sur la ligne de commande et enregistre sa sortie dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="ca018-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="ca018-145">Suivez les instructions fournies par le script.</span><span class="sxs-lookup"><span data-stu-id="ca018-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="ca018-146">Si vous devez contacter le support technique de Microsoft, veillez à inclure le fichier journal avec la demande de support.</span><span class="sxs-lookup"><span data-stu-id="ca018-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="ca018-147">Le script vous indique le chemin d’accès du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="ca018-147">The script will provide you with the path to the log file.</span></span>
