---
title: Installer Microsoft Teams à l’aide de MSI via Microsoft Endpoint Configuration Manager
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
ms.openlocfilehash: 084f6d4587bc279c4387cf44b8ed29d38d51d4a6
ms.sourcegitcommit: 613665c866f6fd0febfa6e26ad718241cdfbb207
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42937598"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager

> [!Tip]
> Pour plus d’informations sur les avantages du client de bureau Windows, voir la session suivante et comment le déployer : [client de bureau Windows teams](https://aka.ms/teams-clients).

Pour utiliser Microsoft Endpoint Configuration Manager, une stratégie de groupe ou tout autre mécanisme de distribution tiers pour un déploiement étendu, Microsoft a fourni des fichiers MSI (32 bits et 64 bits) que les administrateurs peuvent utiliser pour le déploiement en bloc des équipes afin de sélectionner des utilisateurs ou ordinateurs. Les administrateurs peuvent être utilisés ces fichiers pour déployer Teams à distance, afin que les utilisateurs n’aient pas à télécharger l’application Teams. Une fois déployée, l’application Teams se lancera automatiquement pour tous les utilisateurs qui se connectent sur cette machine. (Vous pouvez désactiver le lancement automatique après l’installation de l’application. [Consultez](#disable-auto-launch-for-the-msi-installer)) Nous vous recommandons de déployer le package sur l’ordinateur pour que tous les nouveaux utilisateurs de celui-ci bénéficient également de ce déploiement.

Voici les liens vers les fichiers MSI :


|Entité  |32 bits      |64 bits      |
|---------|---------|---------|
|Commerciale     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Gouvernement fédéral : GCC     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Gouvernement fédéral : GCC Max.    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Gouvernement fédéral : DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

> [!NOTE]
> Installez la version 64 bits d’équipe sur les systèmes d’exploitation 64 bits. Si vous essayez d’installer la version 64 bits d’équipe sur un système d’exploitation 32 bits, l’installation échoue et vous ne recevez pas de message d’erreur.

Teams peut également être inclus avec un déploiement d'Office 365 ProPlus. Pour plus d’informations, reportez-vous à la rubrique [Déployer Microsoft Teams avec Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Pour en savoir plus sur le gestionnaire de configuration de points de terminaison Microsoft, voir [qu’est-ce que Configuration Manager ?](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandé)

1. Récupérer la dernière version du package.
2. Utilisez les valeurs par défaut préremplies par le MSI.
3. Déployez sur des ordinateurs lorsque c’est possible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Fonctionnement du package MSI Microsoft Teams

### <a name="pc-installation"></a>Installation sur PC

Le fichier MSI Teams placera un programme d’installation dans les fichiers programme. Chaque fois qu’un utilisateur se connecte à un nouveau profil utilisateur Windows, le programme d’installation démarre et une copie de l’application Teams est installée dans le dossier `AppData` de cet utilisateur. Si l’application Teams est déjà installée dans le dossier `AppData` d’un utilisateur, le programme d’installation MSI ignore le processus pour cet utilisateur.

N’utilisez pas le MSI pour déployer les mises à jour, car le client sera mis à jour automatiquement lorsqu’il détecte qu’une nouvelle version est disponible à partir du service. Pour redéployer le dernier programme d’installation, suivez le processus de redéploiement de MSI décrit ci-dessous. Si vous déployez une version antérieure du package MSI, le client effectue une mise à jour automatique (sauf dans les environnements VDI) lorsque l’utilisateur le permet. Si une version antérieure est déployée, le MSI déclenche une mise à jour de l’application avant que l’utilisateur ne puisse utiliser Teams.

> [!Important]
> Nous vous déconseillons de modifier les emplacements d’installation par défaut, car cela pourrait rompre le flux de mise à jour. La présence d’une version plus ancienne peut empêcher les utilisateurs d’accéder au service.

#### <a name="target-computer-requirements"></a>Configuration requise pour les ordinateurs cibles

- .NET framework 4.5 ou version ultérieure
- Windows 8.1 ou version ultérieure
- Windows Server 2012 R2 ou version ultérieure
- 3 Go d'espace disque pour chaque profil d'utilisateur (recommandé)

### <a name="vdi-installation"></a>Installation sur VDI

Pour obtenir des instructions complètes sur le déploiement de l’application de bureau teams sur VDI, consultez [Teams pour l’infrastructure de bureau virtualisée (Virtualized Desktop Infrastructure, VDI)](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procédure de nettoyage et de redéploiement

Si un utilisateur désinstalle teams de son profil utilisateur, le programme d’installation MSI effectue le suivi de la désinstallation de l’application teams par l’utilisateur et n’installe plus teams pour ce profil utilisateur. Pour redéployer Teams pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :

1. Désinstaller l’application teams installée pour chaque profil utilisateur.
2. Après la désinstallation, supprimez le répertoire de `%localappdata%\Microsoft\Teams\`manière récursive.
3. Redéployez le package MSI sur cet ordinateur particulier.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Empêcher Teams de démarrer automatiquement après l’installation

Le comportement par défaut du MSI est d’installer l’application Teams dès qu’un utilisateur se connecte, puis démarre automatiquement Teams. Si vous ne voulez pas que Teams démarrent automatiquement pour les utilisateurs une fois qu’elle est installée, vous pouvez utiliser une stratégie de groupe pour définir un paramètre de stratégie ou désactiver le lancement automatique pour le programme d’installation MSI.

### <a name="use-group-policy-recommended"></a>Utiliser la stratégie de groupe (recommandé)

Activez le paramètre de stratégie de groupe **Empêcher Microsoft Teams de démarrer automatiquement après l’installation**. Ce paramètre de stratégie est disponible sous Configuration utilisateur\Stratégies\Modèles d’administration\Microsoft Teams. Il s’agit de la méthode recommandée, car vous pouvez activer ou désactiver le paramètre de stratégie en fonction des besoins de votre organisation.

Lorsque vous activez ce paramètre de stratégie avant l’installation de Teams, Teams ne démarre pas automatiquement lorsque les utilisateurs se connectent à Windows. Lorsqu’un utilisateur se connecte à Teams pour la première fois, les équipes démarrent automatiquement la prochaine fois que l’utilisateur se connecte.

Pour plus d’informations, consultez [Utiliser une stratégie de groupe pour empêcher Microsoft Teams de démarrer automatiquement après l’installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Si vous avez déjà déployé des équipes et que vous voulez définir cette stratégie pour désactiver les équipes de démarrage automatique, définissez tout d’abord le paramètre de stratégie de groupe sur la valeur souhaitée, puis exécutez le [script de réinitialisation de démarrage automatique Teams](scripts/powershell-script-teams-reset-autostart.md) au niveau de chaque utilisateur.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Désactiver le lancement automatique pour le programme d’installation MSI

Vous pouvez désactiver le lancement automatique pour le programme d’installation MSI à l’aide du paramètre **OPTIONS = "noAutoStart = true"** comme suit.  

Pour la version 32 bits :

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Pour la version 64 bits :

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Lorsqu’un utilisateur se connecte à Windows, Teams est installé avec le MSI et un raccourci vers démarrer Teams est ajouté au bureau de l’utilisateur. Teams ne démarre pas avant que l'utilisateur ne démarre manuellement Teams. Une fois que l’utilisateur a démarré manuellement Teams, Teams démarre automatiquement chaque fois que l’utilisateur ouvre une session.

Notez que ces exemples utilisent également le paramètre **ALLUSERS = 1** . Lorsque vous définissez ce paramètre, le programme d’installation à l’échelle de l’entreprise teams apparaît dans programmes et fonctionnalités dans le panneau de configuration et dans applications & fonctionnalités dans les paramètres Windows de tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent alors désinstaller teams s’ils possèdent des informations d’identification d’administrateur sur l’ordinateur.

> [!Note]
> Si vous exécutez le MSI manuellement, veillez à l’exécuter avec des autorisations élevées. Même si vous l’exécutez en tant qu’administrateur, sans l’exécuter avec des autorisations élevées, le programme d’installation ne peut pas configurer l’option permettant de désactiver le démarrage automatique.
