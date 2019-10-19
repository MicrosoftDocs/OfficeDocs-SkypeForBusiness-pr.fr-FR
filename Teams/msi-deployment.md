---
title: Installer Microsoft Teams à l’aide de MSI, via SCCM
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
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37567959"
---
<a name="install-microsoft-teams-using-msi"></a>Installer Microsoft Teams à l’aide de MSI
=================================

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du client de bureau Windows, sur son planning et son déploiement : client de [Bureau Windows teams](https://aka.ms/teams-clients)

Pour utiliser System Center Configuration Manager, ou une stratégie de groupe ou tout mécanisme de distribution tiers pour un déploiement large, Microsoft a fourni des fichiers MSI ( [32-bits](https://aka.ms/teams32bitmsi) et [64-bit](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en bloc d’équipes et sélectionner utilisateurs ou ordinateurs. Les administrateurs peuvent utiliser ces fichiers pour déployer à distance des équipes de sorte que les utilisateurs n’aient pas à télécharger manuellement l’application Teams. Lorsque le déploiement est déployé, teams démarre automatiquement pour tous les utilisateurs qui se connectent à cet ordinateur. (Vous pouvez désactiver le lancement automatique après l’installation de l’application. [Voir ci-dessous](#disable-auto-launch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, de sorte que tous les nouveaux utilisateurs de l’ordinateur bénéficient également de ce déploiement. 

Les équipes peuvent également être incluses dans un déploiement d’Office 365 ProPlus. Pour plus d’informations, reportez-vous à la rubrique [déploiement de Microsoft teams avec Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).
 
> [!Note] 
> Pour en savoir plus sur SCCM, voir [Présentation de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandée)
1. Récupérez le package le plus récent.
2. Utilisez les valeurs par défaut préremplies par le MSI.
3. Déployez sur les ordinateurs lorsque c’est possible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Fonctionnement du package MSI Microsoft teams

### <a name="pc-installation"></a>Installation sur PC

> [!Note] 
> Pour obtenir des instructions sur le déploiement d’équipes dans un environnement VDI (Virtual DesktopInfrastructure), voir [installation de VDI](#vdi-installation) .

Le MSI teams place un programme d’installation dans les fichiers programme. Dès qu’un utilisateur se connecte à un nouveau profil utilisateur Windows, le programme d’installation est lancé et une copie de l’application teams est installée dans le dossier AppData de l’utilisateur. Si un utilisateur possède déjà l’application teams installée dans le dossier AppData, le programme d’installation MSI ignore le processus pour cet utilisateur.

N’utilisez pas le MSI pour déployer les mises à jour, car le client effectue automatiquement une mise à jour dès qu’il détecte une nouvelle version. Pour redéployer le dernier programme d’installation, procédez comme suit lors du processus de redéploiement de MSI décrit ci-dessous.Si vous déployez une version plus ancienne du package MSI, le client se met à jour automatiquement (sauf dans les environnements VDI) lorsque l’utilisateur le peut. Si une ancienne version est déployée, le MSI déclenche une mise à jour de l’application avant que l’utilisateur ne puisse utiliser Teams. 

> [!Important] 
> Nous vous déconseillons de ne pas modifier les emplacements d’installation par défaut, car cela risque de perturber le déroulement de la mise à jour. La présence d’une trop ancienne version entraînera le blocage des utilisateurs de l’accès au service. 

#### <a name="target-computer-requirements"></a>Configuration requise pour l’ordinateur cible

- .NET Framework 4,5 ou version ultérieure
- Windows 7 ou version ultérieure
- 3 Go d’espace disque pour chaque profil utilisateur (recommandé)

### <a name="vdi-installation"></a>Installation de VDI

Voici le processus de déploiement de l’application de bureau Teams. Pour obtenir des instructions complètes, voir [teams pour l’infrastructure de bureau virtualisée](teams-for-vdi.md).

1. Téléchargez le package MSI teams à l’aide de l’un des liens suivants selon l’environnement. Nous vous recommandons d’utiliser la version 64 bits d’un VM VDI doté d’un système d’exploitation 64 bits.

    - [version 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [version 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Exécutez la commande suivante pour installer le MSI sur la machine virtuelle VDI (ou terminer la mise à jour).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Cette opération permet d’installer teams pour programmer des fichiers. À ce stade, la configuration de l’image Golden est terminée.

    La prochaine session interactive de connexion démarre teams et demande des informations d’identification. Notez qu’il n’est pas possible de désactiver le lancement automatique d’équipes lors de l’installation d’équipes sur VDI à l’aide de la propriété ALLUSER.

3. Exécutez la commande suivante pour désinstaller le MSI de l’ordinateur virtuel VDI (ou préparer la mise à jour).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Cela a pour cela la désinstallation de teams.

## <a name="clean-up-and-redeployment-procedure"></a>Procédure de nettoyage et de redéploiement

Si un utilisateur désinstalle teams de son profil utilisateur, le programme d’installation MSI effectue le suivi de la désinstallation de l’application teams par l’utilisateur et n’installe plus teams pour ce profil utilisateur. Pour redéployer teams pour cet utilisateur sur un ordinateur particulier sur lequel il a été désinstallé, procédez comme suit :

1. Désinstaller l’application teams installée pour chaque profil utilisateur. 
2. Après la désinstallation, supprimez le répertoire de manière récursive sous%localappdata%\Microsoft\Teams\.
3. Redéployez le package MSI sur cet ordinateur particulier.

> [!TIP] 
> Vous pouvez utiliser le script de [nettoyage du déploiement de Microsoft teams](scripts/Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Désactiver le lancement automatique pour le programme d’installation MSI

Le comportement par défaut de MSI consiste à installer le client teams dès qu’un utilisateur se connecte, puis à démarrer automatiquement Teams. Vous pouvez modifier ce comportement avec les paramètres ci-dessous comme suit :

- Quand un utilisateur se connecte à Windows, teams est installé avec le MSI
- Toutefois, le client Teams ne démarre pas tant que l’utilisateur n’a pas démarré les équipes manuellement
- Un raccourci pour démarrer teams sera ajouté au bureau de l’utilisateur.
- Lorsque l’utilisateur se connecte, il démarre automatiquement.

Pour la version 32 bits
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Pour la version 64 bits
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Si vous exécutez manuellement le MSI, veillez à l’exécuter avec des autorisations élevées. Même si vous l’exécutez en tant qu’administrateur, vous n’avez pas à le faire à l’aide de privilèges élevés, le programme d’installation ne peut pas configurer l’option permettant de désactiver le démarrage automatique.
