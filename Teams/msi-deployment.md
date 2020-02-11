---
title: Installation de Microsoft teams à l’aide de MSI via Microsoft Endpoint Configuration Manager
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Les administrateurs peuvent utiliser le MSI Teams pour déployer en bloc Microsoft Teams pour des utilisateurs ou sur des ordinateurs spécifiques.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f57eeb44fd728d1b656ce13f56cf2c5997805b9
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888363"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Installation de Microsoft teams à l’aide de Microsoft Endpoint Configuration Manager

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du client de bureau Windows, sur son planning et son déploiement : client de [Bureau Windows teams](https://aka.ms/teams-clients)

Pour utiliser le gestionnaire de configuration de points de terminaison de Microsoft, ou une stratégie de groupe ou tout mécanisme de distribution tiers pour un déploiement global, Microsoft a fourni des fichiers MSI (32-bits et 64 bits) que les administrateurs peuvent utiliser pour le déploiement en bloc d’équipes pour sélectionner des utilisateurs ou ordinateurs. Les administrateurs peuvent utiliser ces fichiers pour déployer à distance des équipes de sorte que les utilisateurs n’aient pas à télécharger manuellement l’application Teams. Lorsque le déploiement est déployé, teams démarre automatiquement pour tous les utilisateurs qui se connectent à cet ordinateur. (Vous pouvez désactiver le lancement automatique après l’installation de l’application. [Voir ci-dessous](#disable-auto-launch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, de sorte que tous les nouveaux utilisateurs de l’ordinateur bénéficient également de ce déploiement.

Voici les liens vers les fichiers MSI :


|Organisme  |32 bits      |64 bits      |
|---------|---------|---------|
|Marché     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Gouvernement fédéral-GCC     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Public fédéral-GCC High    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Gouvernement fédéral-DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Les équipes peuvent également être incluses dans un déploiement d’Office 365 ProPlus. Pour plus d’informations, reportez-vous à la rubrique [déploiement de Microsoft teams avec Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Pour en savoir plus sur le gestionnaire de configuration de points de terminaison Microsoft, voir [qu’est-ce que Configuration Manager ?](https://docs.microsoft.com/configmgr/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandée)

1. Récupérez le package le plus récent.
2. Utilisez les valeurs par défaut préremplies par le MSI.
3. Déployez sur les ordinateurs lorsque c’est possible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Fonctionnement du package MSI Microsoft teams

### <a name="pc-installation"></a>Installation sur PC

Le MSI teams place un programme d’installation dans les fichiers programme. Dès qu’un utilisateur se connecte à un nouveau profil utilisateur Windows, le programme d’installation est lancé et une copie de l’application teams est installée dans le dossier AppData de l’utilisateur. Si un utilisateur possède déjà l’application teams installée dans le dossier AppData, le programme d’installation MSI ignore le processus pour cet utilisateur.

N’utilisez pas le MSI pour déployer les mises à jour, car le client effectue automatiquement une mise à jour dès qu’il détecte une nouvelle version. Pour redéployer le dernier programme d’installation, procédez comme suit lors du processus de redéploiement de MSI décrit ci-dessous.Si vous déployez une version plus ancienne du package MSI, le client se met à jour automatiquement (sauf dans les environnements VDI) lorsque l’utilisateur le peut. Si une ancienne version est déployée, le MSI déclenche une mise à jour de l’application avant que l’utilisateur ne puisse utiliser Teams.

> [!Important]
> Nous vous déconseillons de ne pas modifier les emplacements d’installation par défaut, car cela risque de perturber le déroulement de la mise à jour. La présence d’une trop ancienne version entraînera le blocage des utilisateurs de l’accès au service.

#### <a name="target-computer-requirements"></a>Configuration requise pour l’ordinateur cible

- .NET Framework 4,5 ou version ultérieure
- Windows 7 ou version ultérieure
- Windows Server 2012 R2 ou version ultérieure
- 3 Go d’espace disque pour chaque profil utilisateur (recommandé)

### <a name="vdi-installation"></a>Installation de VDI

Pour obtenir des instructions complètes sur le déploiement de l’application de bureau teams sur VDI, voir [teams pour l’infrastructure de bureau virtuelle](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procédure de nettoyage et de redéploiement

Si un utilisateur désinstalle teams de son profil utilisateur, le programme d’installation MSI effectue le suivi de la désinstallation de l’application teams par l’utilisateur et n’installe plus teams pour ce profil utilisateur. Pour redéployer teams pour cet utilisateur sur un ordinateur particulier sur lequel il a été désinstallé, procédez comme suit :

1. Désinstaller l’application teams installée pour chaque profil utilisateur.
2. Après la désinstallation, supprimez le répertoire de manière récursive sous%localappdata%\Microsoft\Teams\.
3. Redéployez le package MSI sur cet ordinateur particulier.

> [!TIP]
> Vous pouvez utiliser le script de [nettoyage du déploiement de Microsoft teams](scripts/Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via Configuration Manager.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Empêcher les équipes de démarrer automatiquement après l’installation

Le comportement par défaut de l’application MSI consiste à installer l’application teams dès qu’un utilisateur se connecte, puis à démarrer automatiquement Teams. Si vous ne souhaitez pas que Microsoft teams démarre automatiquement une fois qu’il est installé, vous pouvez utiliser une stratégie de groupe pour définir un paramètre de stratégie ou désactiver le lancement automatique pour le programme d’installation MSI.

#### <a name="use-group-policy-recommended"></a>Utiliser une stratégie de groupe (recommandée)

Activez le paramètre **empêcher le démarrage automatique de Microsoft teams après l’installation** . Vous pouvez trouver ce paramètre de stratégie dans User Configuration administration\onedrive Templates\Microsoft Teams. Il s’agit de la méthode recommandée, car vous pouvez activer ou désactiver le paramètre de stratégie conformément aux besoins de votre organisation.

Lorsque vous activez ce paramètre de stratégie avant l’installation d’Teams, Teams ne démarre pas automatiquement lorsque les utilisateurs se connectent à Windows. Dès qu’un utilisateur se connecte à teams pour la première fois, teams s’ouvre automatiquement lors de la prochaine connexion de l’utilisateur.

Pour en savoir plus, voir [utiliser une stratégie de groupe pour empêcher les équipes de démarrer automatiquement après l’installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Si vous avez déjà déployé des équipes et souhaitez définir cette stratégie pour désactiver le démarrage automatique d’équipes, définissez d’abord le paramètre de stratégie de groupe sur la valeur de votre choix, puis exécutez le [script de réinitialisation automatique d’équipes](scripts/powershell-script-teams-reset-autostart.md) par utilisateur.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Désactiver le lancement automatique pour le programme d’installation MSI

Vous pouvez désactiver le lancement automatique du programme d’installation MSI en utilisant le paramètre **options = « noAutoStart = true »** comme suit.  

Pour la version 32 bits

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

Pour la version 64 bits

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

Lorsqu’un utilisateur se connecte à Windows, teams est installé avec le MSI et un raccourci pour démarrer teams est ajouté au bureau de l’utilisateur. Les équipes ne commencent pas tant que l’utilisateur n’a pas démarré teams manuellement. Après le démarrage manuel des équipes par l’utilisateur, teams démarre automatiquement chaque fois que l’utilisateur se connecte.

> [!Note]
> Si vous exécutez manuellement le MSI, veillez à l’exécuter avec des autorisations élevées. Même si vous l’exécutez en tant qu’administrateur, vous n’avez pas à le faire à l’aide de privilèges élevés, le programme d’installation ne peut pas configurer l’option permettant de désactiver le démarrage automatique.
