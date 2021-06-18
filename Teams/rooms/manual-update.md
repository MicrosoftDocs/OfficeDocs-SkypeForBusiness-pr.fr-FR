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
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Mettre à jour manuellement un appareil Salles Microsoft Teams

L’application Salles Microsoft Teams est distribuée via le Microsoft Store. Les mises à jour de l’application sont installées automatiquement à partir du Microsoft Store pendant la maintenance nocturne. il s’agit de la méthode recommandée pour obtenir des mises à jour. Toutefois, dans certaines situations, un appareil Salles Teams ne peut pas recevoir de mises à jour du Microsoft Store. Par exemple, les stratégies de sécurité peuvent ne pas autoriser les appareils à se connecter à Internet ou autoriser le téléchargement d’applications à partir du Microsoft Store. Vous pouvez également mettre à jour un appareil avant d’effectuer l’installation, pendant lequel le Microsoft Store n’est pas disponible.

Si vous ne pouvez pas obtenir de mises à jour à partir du Microsoft Store, vous pouvez utiliser une application hors connexion, mettre à jour un script PowerShell pour mettre à jour manuellement vos appareils Salles d’équipe vers une version plus récente de l’application Salles d’équipe. Suivez les étapes de cet article pour mettre à jour manuellement vos appareils Salles d’équipe.

> [!NOTE]
> Ce processus peut uniquement mettre à jour un appareil Salles d’équipe avec l’application Salles d’équipe déjà installée. Il ne peut pas être utilisé pour effectuer une nouvelle installation. Elle ne permet pas non plus de rétrograder l’application vers une version antérieure. Pour effectuer une nouvelle installation de l’application Salles d’équipe, contactez le fabricant de votre appareil pour obtenir des supports spécifiques à celui-ci, ou consultez Préparer le support [d’installation.](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Étape 1 : télécharger le script de mise à jour de l’application hors connexion

Tout d’abord, téléchargez la dernière version du script de mise à jour des applications hors connexion. Pour télécharger le script, cliquez <https://go.microsoft.com/fwlink/?linkid=2151817> sur . Le script est téléchargé dans le dossier téléchargements par défaut sur votre appareil.

Les fichiers téléchargés peuvent être marqués comme bloqués par Windows. Si vous avez besoin d’exécuter le script sans interaction, vous devez débloquer le script. Pour débloquer le script, vous pouvez :

1. Cliquez avec le bouton droit sur le fichier dans l’Explorateur de fichiers
2. Cliquez sur **Propriétés**
3. Sélectionnez **Débloquer**
4. Cliquez **sur OK**

Pour débloquer le script à l’aide de PowerShell, voir [Débloquer le fichier.](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

Une fois le script de mise à jour de l’application hors connexion téléchargé, transférez le fichier vers l’appareil Salles Teams. Vous pouvez transférer un fichier sur l’appareil à l’aide d’un lecteur USB ou en accédant au fichier à partir d’un partage de fichiers réseau lorsque vous utilisez le mode d’administration sur l’appareil. N’oubliez pas d’enregistrer le fichier sur l’appareil.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Étape 2 : exécuter le script pour mettre à jour l’application Salles Teams

Le script de mise à jour de l’application hors connexion doit être exécuté à partir d’une invite de commandes avec élévation de élévation de niveau lorsque l’utilisateur de Skype (l’utilisateur sous lequel l’application s’exécute) est toujours connecté. Pour plus d’informations sur la connexion à un compte d’administrateur afin d’utiliser l’invite de commandes avec élévation de privilèges lorsque l’utilisateur de Skype est toujours connecté, consultez Passer en mode d’administration et revenir en arrière lorsque l’application Salles Microsoft Teams est en cours [d’exécution.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

Pour exécuter le script à partir d’une invite de commandes avec élévation de élévation de niveaux, exécutez l’une des commandes suivantes :

1. Basculer en mode d’administration
2. Cliquez sur l’icône Démarrer, tapez **Invite de commandes,** puis **sélectionnez Exécuter en tant qu’administrateur.**
3. Exécutez la commande suivante qui `<path to script>` inclut le chemin d’accès complet au script et le nom du fichier de script :

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Par exemple, si le fichier de script se trouve dans et que le nom du fichier de script est `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` le suivant, exécutez la commande suivante :

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Autorisez l’exécuter. Une fois terminé, le script redémarrera l’appareil Salles d’équipe.

Vous pouvez également exécuter le script à l’aide de Remote PowerShell. Pour plus d’informations sur l’utilisation de Remote PowerShell avec des appareils Teams Rooms, voir [Gestion à distance à l’aide de PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Étape 3 : vérifier que l’application a bien été mise à jour

Si le script s’exécute correctement, l’appareil redémarrera dans l’application Salles d’équipe.

Si le script rencontre un problème, il indique son problème sur la ligne de commande et enregistre sa sortie dans un fichier. Suivez les instructions du script. Si vous devez contacter le Support Microsoft, veillez à inclure le fichier journal avec la demande de support. Le script vous fournira le chemin d’accès au fichier journal.