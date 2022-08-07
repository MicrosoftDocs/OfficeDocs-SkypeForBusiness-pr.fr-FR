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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Découvrez comment mettre à jour manuellement votre appareil Salles Microsoft Teams vers une version spécifique.
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267639"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Mettre à jour manuellement un appareil Salles Microsoft Teams

L’application Salles Microsoft Teams est distribuée via le Microsoft Store. Mises à jour à l’application sont installées automatiquement à partir du Microsoft Store pendant la maintenance nocturne ; il s’agit de la méthode recommandée pour obtenir des mises à jour. Toutefois, dans certains cas, un appareil salles Teams ne peut pas recevoir de mises à jour du Microsoft Store. Par exemple, les stratégies de sécurité peuvent ne pas autoriser les appareils à se connecter à Internet ou ne pas autoriser le téléchargement d’applications à partir du Microsoft Store. Vous pouvez également mettre à jour un appareil avant d’effectuer l’installation, au cours de laquelle le Microsoft Store n’est pas disponible.

Si vous ne pouvez pas obtenir les mises à jour du Microsoft Store, vous pouvez utiliser un script PowerShell de mise à jour d’application hors connexion pour mettre à jour manuellement vos appareils salles Teams vers une version plus récente de l’application salles Teams. Suivez les étapes décrites dans cet article pour mettre à jour manuellement vos appareils salles Teams.

> [!NOTE]
> Ce processus peut uniquement mettre à jour un appareil salles Teams avec l’application salles Teams déjà installée. Il ne peut pas être utilisé pour effectuer une nouvelle installation. Il ne peut pas non plus être utilisé pour rétrograder l’application vers une version antérieure. Pour effectuer une nouvelle installation de l’application salles Teams, contactez le fabricant de votre appareil pour connaître le média qui lui est propre.

## <a name="step-1-download-the-offline-app-update-script"></a>Étape 1 : Télécharger le script de mise à jour d’application hors connexion

Tout d’abord, téléchargez la dernière version du script de mise à jour de l’application hors connexion. Pour télécharger le script, cliquez sur <https://go.microsoft.com/fwlink/?linkid=2151817>. Le script est téléchargé dans le dossier de téléchargements par défaut sur votre appareil.

Les fichiers téléchargés peuvent être marqués comme bloqués par Windows. Si vous devez exécuter le script sans aucune interaction, vous devez débloquer le script. Pour débloquer le script, procédez comme suit :

1. Cliquez avec le bouton droit sur le fichier dans Explorateur de fichiers
2. Cliquez sur **Propriétés**
3. Sélectionner **Débloquer**
4. Cliquez sur **OK**

Pour débloquer le script à l’aide de PowerShell, consultez [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Une fois le script de mise à jour de l’application hors connexion téléchargé, transférez le fichier sur l’appareil salles Teams. Vous pouvez transférer un fichier vers l’appareil à l’aide d’un lecteur USB ou en accédant au fichier à partir d’un partage de fichiers réseau en mode Administration sur l’appareil. Veillez à noter où vous enregistrez le fichier sur l’appareil.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Étape 2 : Exécuter le script pour mettre à jour l’application salles Teams

Le script de mise à jour d’application hors connexion doit être exécuté à partir d’une invite de commandes avec élévation de privilèges pendant que l’utilisateur Skype (l’utilisateur sous lequel l’application s’exécute) est toujours connecté. Pour plus d’informations sur la façon de se connecter à un compte d’administrateur afin d’utiliser l’invite de commandes avec élévation de privilèges pendant que l’utilisateur Skype est toujours connecté, consultez [Basculer vers le mode Administration et revenir en cas de blocage de l’application Salles Microsoft Teams](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes).

Procédez comme suit pour exécuter le script à partir d’une invite de commandes avec élévation de privilèges :

1. Basculer en mode Administration
2. Cliquez sur l’icône Démarrer, tapez **Invite de commandes**, puis **sélectionnez Exécuter en tant qu’administrateur**
3. Exécutez la commande suivante, qui `<path to script>` inclut le chemin d’accès complet au script et le nom du fichier de script :

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Par exemple, si le fichier de script se trouve dans `C:\Users\Admin\Downloads`, et que le nom du fichier de script est `MTR-Update-4.5.6.7.ps1`, exécutez la commande suivante :

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Autorisez l’exécution du script. Une fois l’opération terminée, le script redémarre l’appareil salles Teams.

Vous pouvez également exécuter le script à l’aide de Remote PowerShell. Pour plus d’informations sur l’utilisation de Remote PowerShell avec des appareils salles Teams, consultez [Gestion à distance à l’aide de PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Étape 3 : Vérifier que l’application a été mise à jour avec succès

Si le script s’exécute correctement, l’appareil redémarre dans l’application salles Teams.

Si le script rencontre un problème, il indique le problème sur la ligne de commande et enregistre sa sortie dans un fichier. Suivez les instructions fournies par le script. Si vous devez contacter Support Microsoft, veillez à inclure le fichier journal avec la demande de support. Le script vous fournit le chemin d’accès au fichier journal.
