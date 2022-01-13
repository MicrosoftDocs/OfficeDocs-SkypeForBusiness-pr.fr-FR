---
title: Mettre à jour manuellement un Salles Microsoft Teams appareil
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Découvrez comment mettre à jour manuellement Salles Microsoft Teams appareil vers une version spécifique.
ms.openlocfilehash: 0b8ec08880d3f8c7ecce28293c92fb6ada901277
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "62014994"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Mettre à jour manuellement un Salles Microsoft Teams appareil

L Salles Microsoft Teams appeil est distribué via le Microsoft Store. Les mises à jour de l’application sont installées à partir du Microsoft Store automatiquement pendant la maintenance nocturne ; il s’agit de la méthode recommandée pour obtenir les mises à jour. Toutefois, dans certaines situations, un appareil salles Teams ne peut pas recevoir de mises à jour du Microsoft Store. Par exemple, les stratégies de sécurité peuvent ne pas autoriser les appareils à se connecter à Internet ou autoriser le téléchargement d’applications à partir du Microsoft Store. Vous pouvez également mettre à jour un appareil avant de le configurer, au cours duquel le Microsoft Store n’est pas disponible.

Si vous ne pouvez pas obtenir de mises à jour du Microsoft Store, vous pouvez utiliser un script de mise à jour de l’application hors connexion PowerShell pour mettre à jour manuellement vos appareils salles Teams vers une version plus récente de l’application salles Teams. Suivez les étapes de cet article pour mettre à jour manuellement vos salles Teams appareils mobiles.

> [!NOTE]
> Ce processus peut uniquement mettre à jour salles Teams appareil avec l’salles Teams l’application déjà installée. Il ne peut pas être utilisé pour effectuer une nouvelle installation. Elle ne permet pas non plus de rétrograder l’application vers une version antérieure. Pour effectuer une nouvelle installation de l’salles Teams, contactez le fabricant de votre appareil pour obtenir des médias qui lui sont spécifiques.

## <a name="step-1-download-the-offline-app-update-script"></a>Étape 1 : télécharger le script de mise à jour de l’application hors connexion

Tout d’abord, téléchargez la dernière version du script de mise à jour des applications hors connexion. Pour télécharger le script, cliquez <https://go.microsoft.com/fwlink/?linkid=2151817> sur . Le script est téléchargé dans le dossier téléchargements par défaut sur votre appareil.

Les fichiers téléchargés peuvent être marqués comme bloqués par Windows. Si vous avez besoin d’exécuter le script sans interaction, vous devez débloquer le script. Pour débloquer le script, vous pouvez :

1. Cliquez avec le bouton droit sur le fichier dans l’Explorateur de fichiers
2. Cliquez sur **Propriétés**
3. Sélectionnez **Débloquer**
4. Cliquez **sur OK**

Pour débloquer le script à l’aide de PowerShell, voir [Débloquer le fichier.](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

Une fois le script de mise à jour de l’application hors connexion téléchargé, transférez le fichier vers l salles Teams appareil mobile. Vous pouvez transférer un fichier sur l’appareil à l’aide d’un lecteur USB ou en accédant au fichier à partir d’un partage de fichiers réseau lorsque vous utilisez le mode d’administration sur l’appareil. N’oubliez pas d’enregistrer le fichier sur l’appareil.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Étape 2 : exécuter le script pour mettre à jour l salles Teams appappe

Le script de mise à jour de l’application hors connexion doit être exécuté à partir d’une invite de commandes avec élévation de élévation de Skype (l’utilisateur sous lequel l’application s’exécute) est toujours connecté. Pour plus d’informations sur la connexion à un compte d’administrateur afin d’utiliser l’invite de commandes avec élévation de privilèges lorsque l’utilisateur de Skype est toujours connecté, voir Passer en mode d’administration et revenir en arrière en cas de panne de l’application [Salles Microsoft Teams.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes)

Pour exécuter le script à partir d’une invite de commandes avec élévation de élévation de niveaux, exécutez l’une des commandes suivantes :

1. Basculer en mode d’administration
2. Cliquez sur l’icône Démarrer, tapez **Invite de** commandes, puis **sélectionnez Exécuter en tant qu’administrateur.**
3. Exécutez la commande suivante qui `<path to script>` inclut le chemin d’accès complet au script et le nom du fichier de script :

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Par exemple, si le fichier de script se trouve dans et que le nom du fichier de script est `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` le suivant, exécutez la commande suivante :

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Autorisez l’exécuter. Une fois terminé, le script redémarrera le salles Teams appareil.

Vous pouvez également exécuter le script à l’aide de Remote PowerShell. Pour plus d’informations sur l’utilisation de Remote PowerShell avec des salles Teams, voir Gestion à distance [à l’aide de PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Étape 3 : vérifier que l’application a bien été mise à jour

Si le script s’exécute correctement, l’appareil redémarrera dans l’salles Teams’application.

Si le script rencontre un problème, il indique son problème sur la ligne de commande et enregistre sa sortie dans un fichier. Suivez les instructions du script. Si vous devez contacter le Support Microsoft, veillez à inclure le fichier journal avec la demande de support. Le script vous fournira le chemin d’accès au fichier journal.
