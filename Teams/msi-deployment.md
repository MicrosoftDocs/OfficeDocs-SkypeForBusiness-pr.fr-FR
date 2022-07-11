---
title: Installer Teams en bloc à l’aide de Windows Installer (MSI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Utilisez des fichiers Windows Installer (MSI) pour distribuer le client Teams à plusieurs utilisateurs et ordinateurs.
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
ms.openlocfilehash: 7b8c8521aa5e19abe59aa9e4c60fcc41eff9b1c7
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713322"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>Installer Teams en bloc à l’aide de Windows Installer (MSI)

> [!Tip]
> Regardez la session suivante pour découvrir les avantages du client bureau Windows, comment le planifier et comment le déployer : [Teams : client de bureau Windows](https://aka.ms/teams-clients).

Microsoft fournit des fichiers MSI 32 bits, 64 bits et ARM64 que vous pouvez utiliser pour déployer Microsoft Teams en bloc pour sélectionner des utilisateurs et des ordinateurs. Les fichiers MSI peuvent être utilisés avec des Configuration Manager de point de terminaison [Microsoft](/configmgr/core/understand/introduction), [des stratégie de groupe](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) ou des logiciels de distribution tiers pour déployer Teams dans votre organisation. Les déploiements en bloc sont utiles, car les utilisateurs n’ont pas besoin de télécharger et d’installer manuellement le client Teams. Au lieu de cela, Teams est déployé sur des ordinateurs, puis lance automatiquement la première fois que les utilisateurs se connectent à un ordinateur.

Nous vous recommandons de déployer le package sur des ordinateurs plutôt qu’un utilisateur spécifique. En ciblant des ordinateurs, tous les nouveaux utilisateurs de ces ordinateurs bénéficieront de ce déploiement.

>[!NOTE]
> Teams peut également être distribué à votre organisation dans le cadre de Applications Microsoft 365 pour les grandes entreprises. Si vous souhaitez en savoir plus, consultez l’article [Déployer Microsoft Teams avec Microsoft 365 Apps for enterprise](/deployoffice/teams-install).

## <a name="msi-files"></a>Fichiers MSI

Le tableau ci-dessous fournit des liens vers des fichiers MSI 32 bits, 64 bits et ARM64 pour Teams. Téléchargez l’identité MSI que vous souhaitez installer sur les ordinateurs de votre organisation. L’architecture x86 (32 bits ou 64 bits) prise en charge par Teams est indépendante des autres applications Office installées sur un ordinateur.

Si vous disposez d’ordinateurs 64 bits, nous vous recommandons d’installer l’interface MSI Teams 64 bits, même si l’ordinateur exécute une version 32 bits d’Office. Arm64 MSI ne peut être installé que sur les ordinateurs qui utilisent l’architecture ARM, comme le Surface Pro X.

> [!IMPORTANT]
> Installez la version 64 bits de Teams uniquement sur les systèmes d’exploitation 64 bits. Si vous essayez d’installer la version 64 bits de Teams sur un système d’exploitation 32 bits, l’installation échoue et vous ne recevez pas de message d’erreur.

|Entité  |32 bits      |64 bits      | ARM64 |
|---------|---------|---------|-----------|
|Commerciale     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Gouvernement des États-Unis - GCC     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Gouvernement des États-Unis - GCC High    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Gouvernement des États-Unis - DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Fonctionnement du fichier MSI Microsoft Teams

### <a name="pc-installation"></a>Installation sur PC

Teams MSI place un programme d’installation sur `%SystemDrive%\Program Files\Teams Installer` Windows 32 bits et `%SystemDrive%\Program Files (x86)\Teams Installer` sur Windows 64 bits. Chaque fois qu’un utilisateur se connecte à un nouveau profil utilisateur Windows, le programme d’installation est lancé et une copie de l’application Teams est installée dans le dossier de `%LocalAppData%\Microsoft\Teams` cet utilisateur. Si l’application Teams est déjà installée sur un utilisateur dans le `%LocalAppData%\Microsoft\Teams` dossier, le programme d’installation MSI ignore le processus pour cet utilisateur.

Les fichiers MSI ne peuvent pas être utilisés pour déployer des mises à jour. Le client Teams se met à jour automatiquement lorsqu’il détecte qu’une nouvelle version est disponible à partir du service. Pour redéployer le dernier programme d’installation, utilisez le processus de redéploiement de MSI décrit ci-dessous. Si vous déployez une version antérieure du fichier MSI, le client se met à jour automatiquement (sauf dans les environnements VDI) lorsque cela est possible pour l’utilisateur. Si une version antérieure est déployée, le MSI déclenche une mise à jour de l’application avant que l’utilisateur ne puisse utiliser Teams.

> [!IMPORTANT]
> Nous vous déconseillons de modifier les emplacements d’installation par défaut, car cela peut interrompre le flux de mise à jour. La présence d’une version plus ancienne peut empêcher les utilisateurs d’accéder au service.

#### <a name="target-computer-requirements"></a>Configuration requise pour les ordinateurs cibles

Assurez-vous que les ordinateurs que vous installez Teams répondent aux exigences indiquées dans la configuration [matérielle requise pour Microsoft Teams](hardware-requirements-for-the-teams-app.md).

### <a name="vdi-installation"></a>Installation sur VDI

Pour obtenir des instructions complètes sur le déploiement de l’application de bureau teams sur VDI, consultez [Teams pour l’infrastructure de bureau virtualisée (Virtualized Desktop Infrastructure, VDI)](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procédure de nettoyage et de redéploiement

Si un utilisateur désinstalle Teams de son profil d’utilisateur, le programme d’installation MSI vérifiera que l’utilisateur a désinstallé l’application Teams et n’installe plus Teams pour ce profil d’utilisateur. Pour redéployer Teams pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :

> [!IMPORTANT]
> Les étapes suivantes contiennent des informations sur la façon de modifier le registre. Assurez-vous de sauvegarder le registre avant de le modifier et de savoir comment restaurer le registre en cas de problème. Si vous souhaitez en savoir plus sur la sauvegarde, la restauration et la modification du registre, consultez l’article [Informations sur le registre Windows pour les utilisateurs avancés](https://support.microsoft.com/help/256986).

1. Désinstallez l’application Teams installée pour chaque profil utilisateur. Si vous souhaitez en savoir plus, consultez l’article [Désinstaller Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Supprimez le répertoire de manière récursive sous `%LocalAppData%\Microsoft\Teams\` chaque profil utilisateur.
3. Supprimez la valeur de `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` Registre pour chaque profil utilisateur.
4. Redéployez le fichier MSI sur cet ordinateur particulier.

> [!TIP]
> Vous pouvez également utiliser le [script de nettoyage de déploiement Teams](scripts/powershell-script-deployment-cleanup.md) pour effectuer les étapes 1 et 2.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Empêcher Teams de démarrer automatiquement après l’installation

Le comportement par défaut du MSI est d’installer l’application Teams dès qu’un utilisateur se connecte, puis démarre automatiquement Teams. Si vous ne voulez pas que Teams démarrent automatiquement pour les utilisateurs une fois qu’elle est installée, vous pouvez utiliser une stratégie de groupe pour définir un paramètre de stratégie ou désactiver le lancement automatique pour le programme d’installation MSI.

### <a name="use-group-policy-recommended"></a>Utiliser la stratégie de groupe (recommandé)

Activez l’option **Empêcher le démarrage automatique de Microsoft Teams après l’installation** [stratégie de groupe](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) paramètre. Vous trouverez ce paramètre de stratégie dans les **modèles d’administration des**\\ stratégies de **configuration**\\\\ utilisateur **Microsoft Teams**. Il s’agit de la méthode recommandée, car vous pouvez activer ou désactiver le paramètre de stratégie en fonction des besoins de votre organisation.

Lorsque vous activez ce paramètre de stratégie avant l’installation de Teams, Teams ne démarre pas automatiquement lorsque les utilisateurs se connectent à Windows. Lorsqu’un utilisateur se connecte à Teams pour la première fois, les équipes démarrent automatiquement la prochaine fois que l’utilisateur se connecte.

Pour plus d’informations, consultez [Utiliser une stratégie de groupe pour empêcher Microsoft Teams de démarrer automatiquement après l’installation](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Si vous avez déjà déployé des équipes et que vous voulez définir cette stratégie pour désactiver les équipes de démarrage automatique, définissez tout d’abord le paramètre de stratégie de groupe sur la valeur souhaitée, puis exécutez le [script de réinitialisation de démarrage automatique Teams](scripts/powershell-script-teams-reset-autostart.md) au niveau de chaque utilisateur.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Désactiver le lancement automatique pour le programme d’installation MSI

Vous pouvez désactiver le lancement automatique pour le programme d’installation MSI en utilisant le `OPTIONS="noAutoStart=true"` paramètre comme suit.  

Pour la version 32 bits :

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Pour la version 64 bits :

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Lorsqu’un utilisateur se connecte à Windows, Teams est installé avec l’identité MSI. Teams ne démarre pas avant que l'utilisateur ne démarre manuellement Teams. Une fois que l’utilisateur a démarré manuellement Teams, Teams démarre automatiquement chaque fois que l’utilisateur ouvre une session.

Notez que ces exemples utilisent également le paramètre **ALLUSERS=1**. Lorsque vous définissez ce paramètre, Teams Machine-Wide Installer apparaît dans Programmes et fonctionnalités dans le Panneau de configuration et dans Applications et fonctionnalités dans les paramètres Windows pour tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent ensuite désinstaller Teams s’ils disposent d’informations d’identification d’administrateur sur l’ordinateur.

> [!Note]
> Si vous exécutez le MSI manuellement, veillez à l’exécuter avec des autorisations élevées. Même si vous l’exécutez en tant qu’administrateur, sans l’exécuter avec des autorisations élevées, le programme d’installation ne peut pas configurer l’option permettant de désactiver le démarrage automatique.
