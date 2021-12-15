---
title: Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Utilisez Microsoft Endpoint Configuration Manager pour déployer en bloc Microsoft Teams pour sélectionner des utilisateurs ou des ordinateurs.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a26970bdef120ae6b6ba80fac80838320a06fd7
ms.sourcegitcommit: 8d728ca42dc917a28b94e2de84ce4f5b2515d485
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2021
ms.locfileid: "61513505"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager

> [!Tip]
> Regardez la session suivante pour découvrir les avantages du client bureau Windows, comment le planifier et comment le déployer : [Teams : client de bureau Windows](https://aka.ms/teams-clients).

Pour utiliser Microsoft Endpoint Configuration Manager, une stratégie de groupe ou tout autre mécanisme de distribution tiers pour un déploiement étendu, Microsoft a fourni des fichiers MSI (32 bits et 64 bits) que les administrateurs peuvent utiliser pour le déploiement en bloc des équipes afin de sélectionner des utilisateurs ou ordinateurs. Les administrateurs peuvent être utilisés ces fichiers pour déployer Teams à distance, afin que les utilisateurs n’aient pas à télécharger l’application Teams. Une fois déployée, l’application Teams se lancera automatiquement pour tous les utilisateurs qui se connectent sur cette machine. (Vous pouvez désactiver le lancement automatique après l’installation de l’application. [Consultez](#disable-auto-launch-for-the-msi-installer)) Nous vous recommandons de déployer le package sur l’ordinateur pour que tous les nouveaux utilisateurs de celui-ci bénéficient également de ce déploiement.

Voici les liens vers les fichiers MSI :

|Entité  |32 bits      |64 bits      | ARM64 |
|---------|---------|---------|-----------|
|Commerciale     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Gouvernement des États-Unis - Cloud de la communauté du secteur public     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Gouvernement des États-Unis - Cloud de la communauté du secteur public Haute    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Administration publique des États-Unis - DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

**Pour garantir un déploiement réussi, prenez en compte les éléments suivants :**

- Installez la version 64 bits de Teams sur les systèmes d’exploitation 64 bits. Si vous essayez d’installer la version 64 bits de Teams sur un système d’exploitation 32 bits, l’installation échouera et vous ne recevrez pas de message d’erreur.

- Teams peut également être inclus avec un déploiement de Microsoft 365 Apps for enterprise. Si vous souhaitez en savoir plus, consultez l’article [Déployer Microsoft Teams avec Microsoft 365 Apps for enterprise](/deployoffice/teams-install).

- Si vous souhaitez en savoir plus sur Microsoft Endpoint Configuration Manager, consultez l’article [Présentation de Configuration Manager](/configmgr/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandé)

1. Récupérer la dernière version du package.
2. Utilisez les valeurs par défaut préremplies par le MSI.
3. Déployez sur des ordinateurs lorsque c’est possible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Fonctionnement du package MSI Microsoft Teams

### <a name="pc-installation"></a>Installation sur PC

Le fichier MSI Teams placera un programme d’installation dans les fichiers programme. Chaque fois qu’un utilisateur se connecte à un nouveau profil utilisateur Windows, le programme d’installation démarre et une copie de l’application Teams est installée dans le dossier `AppData` de cet utilisateur. Si l’application Teams est déjà installée dans le dossier `AppData` d’un utilisateur, le programme d’installation MSI ignore le processus pour cet utilisateur.

N’utilisez pas le MSI pour déployer les mises à jour, car le client sera mis à jour automatiquement lorsqu’il détecte qu’une nouvelle version est disponible à partir du service. Pour redéployer le dernier programme d’installation, suivez le processus de redéploiement de MSI décrit ci-dessous. Si vous déployez une version antérieure du package MSI, le client effectue une mise à jour automatique (sauf dans les environnements VDI) lorsque l’utilisateur le permet. Si une version antérieure est déployée, le MSI déclenche une mise à jour de l’application avant que l’utilisateur ne puisse utiliser Teams.

> [!IMPORTANT]
> L’emplacement par défaut est C:\Program Files\Teams Installer sur les systèmes d’exploitation 32 bits et C:\Program Files (x86)\Teams Installer sur les systèmes d’exploitation 64 bits.
> Nous vous déconseillons de modifier les emplacements d’installation par défaut, car cela pourrait rompre le flux de mise à jour. La présence d’une version plus ancienne peut empêcher les utilisateurs d’accéder au service.

#### <a name="target-computer-requirements"></a>Configuration requise pour les ordinateurs cibles

- .NET framework 4.5 ou version ultérieure
- Windows 8.1 ou version ultérieure
- Windows Server 2012 R2 ou version ultérieure
- 3 Go d'espace disque pour chaque profil d'utilisateur (recommandé)

### <a name="vdi-installation"></a>Installation sur VDI

Pour obtenir des instructions complètes sur le déploiement de l’application de bureau teams sur VDI, consultez [Teams pour l’infrastructure de bureau virtualisée (Virtualized Desktop Infrastructure, VDI)](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procédure de nettoyage et de redéploiement

Si un utilisateur désinstalle Teams de son profil d’utilisateur, le programme d’installation MSI vérifiera que l’utilisateur a désinstallé l’application Teams et n’installe plus Teams pour ce profil d’utilisateur. Pour redéployer Teams pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :

> [!IMPORTANT]
> Les étapes suivantes contiennent des informations sur la façon de modifier le registre. Assurez-vous de sauvegarder le registre avant de le modifier et de savoir comment restaurer le registre en cas de problème. Si vous souhaitez en savoir plus sur la sauvegarde, la restauration et la modification du registre, consultez l’article [Informations sur le registre Windows pour les utilisateurs avancés](https://support.microsoft.com/help/256986).

1. Désinstallez l’application Teams installée pour chaque profil utilisateur. Si vous souhaitez en savoir plus, consultez l’article [Désinstaller Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Supprimez le répertoire de façon récurrente sous `%localappdata%\Microsoft\Teams\`.
3. Supprimez la valeur de registre `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi`.
4. Redéployez le package MSI sur cet ordinateur particulier.

> [!TIP]
> Vous pouvez également utiliser le [script de nettoyage de déploiement Teams](scripts/powershell-script-deployment-cleanup.md) pour effectuer les étapes 1 et 2.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Empêcher Teams de démarrer automatiquement après l’installation

Le comportement par défaut du MSI est d’installer l’application Teams dès qu’un utilisateur se connecte, puis démarre automatiquement Teams. Si vous ne voulez pas que Teams démarrent automatiquement pour les utilisateurs une fois qu’elle est installée, vous pouvez utiliser une stratégie de groupe pour définir un paramètre de stratégie ou désactiver le lancement automatique pour le programme d’installation MSI.

### <a name="use-group-policy-recommended"></a>Utiliser la stratégie de groupe (recommandé)

Activez le paramètre de stratégie de groupe **Empêcher Microsoft Teams de démarrer automatiquement après l’installation**. Ce paramètre de stratégie est disponible sous Configuration utilisateur\Stratégies\Modèles d’administration\Microsoft Teams. Il s’agit de la méthode recommandée, car vous pouvez activer ou désactiver le paramètre de stratégie en fonction des besoins de votre organisation.

Lorsque vous activez ce paramètre de stratégie avant l’installation de Teams, Teams ne démarre pas automatiquement lorsque les utilisateurs se connectent à Windows. Lorsqu’un utilisateur se connecte à Teams pour la première fois, les équipes démarrent automatiquement la prochaine fois que l’utilisateur se connecte.

Pour plus d’informations, consultez [Utiliser une stratégie de groupe pour empêcher Microsoft Teams de démarrer automatiquement après l’installation](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Si vous avez déjà déployé des équipes et que vous voulez définir cette stratégie pour désactiver les équipes de démarrage automatique, définissez tout d’abord le paramètre de stratégie de groupe sur la valeur souhaitée, puis exécutez le [script de réinitialisation de démarrage automatique Teams](scripts/powershell-script-teams-reset-autostart.md) au niveau de chaque utilisateur.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Désactiver le lancement automatique pour le programme d’installation MSI

Vous pouvez désactiver le lancement automatique pour le programme d’installation MSI à l’aide du paramètre **OPTIONS = "noAutoStart = true"** comme suit.  

Pour la version 32 bits :

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Pour la version 64 bits :

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Lorsqu’un utilisateur se connecte à Windows, Teams est installé avec le MSI et un raccourci vers démarrer Teams est ajouté au bureau de l’utilisateur. Teams ne démarre pas avant que l'utilisateur ne démarre manuellement Teams. Une fois que l’utilisateur a démarré manuellement Teams, Teams démarre automatiquement chaque fois que l’utilisateur ouvre une session.

Notez que ces exemples utilisent également le paramètre **ALLUSERS=1**. Lorsque vous définissez ce paramètre, Teams Machine-Wide Installer apparaît dans Programmes et fonctionnalités dans le Panneau de configuration et dans Applications et fonctionnalités dans les paramètres Windows pour tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent ensuite désinstaller Teams s’ils disposent d’informations d’identification d’administrateur sur l’ordinateur.

> [!Note]
> Si vous exécutez le MSI manuellement, veillez à l’exécuter avec des autorisations élevées. Même si vous l’exécutez en tant qu’administrateur, sans l’exécuter avec des autorisations élevées, le programme d’installation ne peut pas configurer l’option permettant de désactiver le démarrage automatique.
