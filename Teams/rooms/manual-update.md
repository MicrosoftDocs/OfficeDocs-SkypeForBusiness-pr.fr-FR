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
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Mettre à jour manuellement un appareil Microsoft teams

L’application Microsoft teams salles est distribuée via le Microsoft Store. Les mises à jour apportées à l’application sont installées automatiquement à partir du Microsoft Store lors de la maintenance nocturne ; Il s’agit de la méthode recommandée pour obtenir les mises à jour. Toutefois, dans certains cas, un appareil de salle Teams ne peut pas recevoir de mises à jour du Microsoft Store. Par exemple, il est possible que les stratégies de sécurité n’autorisent pas les appareils à se connecter à Internet ou ne permettent pas de télécharger des applications à partir du Microsoft Store. Vous pouvez également mettre à jour un appareil avant de procéder à l’installation, au cours duquel le Microsoft Store n’est pas disponible.

Si vous ne parvenez pas à récupérer des mises à jour à partir de la boutique Microsoft, vous pouvez utiliser un script PowerShell de mise à jour de l’application en mode hors connexion pour mettre à jour manuellement vos périphériques d’équipe sur une nouvelle version de l’application salles d’équipe. Suivez les étapes décrites dans cet article pour mettre à jour manuellement vos appareils de salle d’équipe.

> [!NOTE]
> Ce processus ne peut mettre à jour qu’un appareil de salle d’équipe sur lequel l’application salles de teams est déjà installée. Il ne peut pas être utilisé pour effectuer une nouvelle installation. Il ne peut pas non plus être utilisé pour rétrograder l’application à une version plus ancienne. Pour effectuer une nouvelle installation de l’application salles d’équipe, contactez le fabricant de votre appareil pour obtenir du contenu multimédia qui lui est propre ou consultez [préparer le support d’installation](console.md#prepare-the-installation-media).

## <a name="step-1-download-the-offline-app-update-script"></a>Étape 1 : Télécharger le script de mise à jour des applications hors connexion

Tout d’abord, téléchargez la version la plus récente du script de mise à jour de l’application en mode hors connexion. Pour télécharger le script, cliquez sur <https://go.microsoft.com/fwlink/?linkid=2151817> . Le script est téléchargé dans le dossier téléchargements par défaut sur votre appareil.

Les fichiers téléchargés peuvent être marqués comme bloqués par Windows. Si vous avez besoin d’exécuter le script sans interaction, vous devez débloquer le script. Pour débloquer le script, procédez comme suit :

1. Cliquez avec le bouton droit sur le fichier dans l’Explorateur de fichiers
2. Cliquez sur **Propriétés** .
3. Sélectionnez **débloquer** .
4. Cliquez sur **OK** .

Pour débloquer le script à l’aide de PowerShell, voir [Unblock-file](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Après le téléchargement du script de mise à jour de l’application en mode hors connexion, transférez le fichier vers l’appareil de salle de l’équipe. Vous pouvez transférer un fichier vers l’appareil à l’aide d’un lecteur USB ou en accédant au fichier à partir d’un partage de fichiers réseau lorsque le mode administrateur est activé sur l’appareil. Veillez à noter l’emplacement où vous enregistrez le fichier sur l’appareil.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Étape 2 : exécuter le script pour mettre à jour l’application salles d’équipe

Le script de mise à jour de l’application en mode hors connexion doit être exécuté à partir d’une invite de commandes avec élévation de privilèges alors que l’utilisateur de Skype (utilisateur sous lequel l’application s’exécute) est connecté. Pour plus d’informations sur la connexion à un compte d’administrateur afin d’utiliser l’invite de commandes avec élévation de privilèges alors que l’utilisateur de Skype est toujours connecté, consultez [basculer vers le mode administrateur et retour lors de l’exécution de l’application Microsoft teams pièces](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).

Pour exécuter le script à partir d’une invite de commandes avec élévation de privilèges, procédez comme suit :

1. Basculer en mode administrateur
2. Cliquez sur l’icône Démarrer, tapez **invite de commandes**, puis sélectionnez **exécuter en tant qu’administrateur** .
3. Exécutez la commande suivante qui `<path to script>` inclut le chemin d’accès complet au script et le nom du fichier de script :

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Par exemple, si le fichier de script se trouve dans et que `C:\Users\Admin\Downloads` le nom du fichier de script est `MTR-Update-4.5.6.7.ps1` , exécutez la commande suivante :

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Autorisez l’exécution du script. Lorsque vous avez terminé, le script redémarre l’appareil de salle de l’équipe.

Vous pouvez également exécuter le script à l’aide de Remote PowerShell. Pour plus d’informations sur l’utilisation de Remote PowerShell avec les appareils de salle d’équipe, voir [gestion à distance à l’aide de PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Étape 3 : vérifier que l’application a été mise à jour avec succès

Si le script s’exécute correctement, l’appareil est redémarré dans l’application salles de équipe.

Si le script rencontre un problème, il indique quel est le problème sur la ligne de commande et enregistre sa sortie dans un fichier. Suivez les instructions fournies par le script. Si vous devez contacter le support technique de Microsoft, veillez à inclure le fichier journal avec la demande de support. Le script vous indique le chemin d’accès du fichier journal.
