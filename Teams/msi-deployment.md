---
title: Installer Microsoft Teams à l’aide de MSI, via SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Les administrateurs peuvent utiliser le MSI Teams pour déployer en bloc Microsoft Teams pour des utilisateurs ou sur des ordinateurs spécifiques.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea2f6b85dc4802f2caac4df5b69754d27e8fb9a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33899016"
---
<a name="install-microsoft-teams-using-msi"></a>Installer Microsoft Teams à l’aide de MSI
=================================

> [!Tip]
> Regarder la session pour en savoir plus sur le Client de bureau Windows, comment planifier et déployer les avantages suivante : [Client de bureau Windows équipes](https://aka.ms/teams-clients)

Pour utiliser System Center Configuration Manager ou la stratégie de groupe ou les mécanismes de distribution de tiers pour le déploiement, Microsoft a fourni les fichiers MSI ( [32 bits](https://aka.ms/teams32bitmsi) et [64 bits](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en bloc des équipes pour sélectionner les utilisateurs ou ordinateurs. Administrateurs peuvent utiliser ces fichiers pour déployer des équipes à distance afin que les utilisateurs n’ont pas télécharger manuellement l’application d’équipes. Lors du déploiement, les équipes automatique de lancement pour tous les utilisateurs qui se connectent à sur cet ordinateur. (Vous pouvez désactiver lancement automatique après l’installation de l’application. [Voir ci-dessous](#disable-auto-launch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs de l’ordinateur bénéficient également ce déploiement. 
 
> [!Note] 
> Pour en savoir plus sur SCCM, voir [Introduction à System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandé)
1. Récupérer le dernier package.
2. Utilisez les valeurs par défaut préremplies par le fichier MSI.
3. Déployez sur les ordinateurs lorsque cela est possible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Comment fonctionne le package Microsoft équipes MSI

### <a name="pc-installation"></a>Installation de l’ordinateur

> [!Note] 
> Pour obtenir des instructions sur la façon de déployer d’équipes dans un environnement de DesktopInfrastructure VDI (Virtual), consultez la rubrique [installation VDI](#vdi-installation) .

Le fichier MSI équipes place un programme d’installation dans les fichiers de programme. Chaque fois qu’un utilisateur se connecte à un nouveau profil d’utilisateur Windows, le programme d’installation est lancé et une copie de l’application des équipes sera installée dans le dossier appdata de l’utilisateur. Si l’utilisateur a déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignore le processus de cet utilisateur.

N’utilisez pas le fichier MSI pour déployer des mises à jour, car le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service. Pour redéployer le programme d’installation le plus récent utiliser le processus de redéploiement MSI décrite ci-dessous.Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur. Si une version ancienne très obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes. 

> [!Important] 
> Nous ne pas recommandé de modifier les emplacements d’installation par défaut, comme ceci risque de perturber le flux de mise à jour. Trop ancienne une version empêchera finira par les utilisateurs d’accéder au service. 

#### <a name="target-computer-requirements"></a>Exigences pour l’ordinateur cible

- .NET framework 4.5 ou version ultérieure
- Windows 7 ou version ultérieure
- 3 Go d’espace disque requis pour chaque profil utilisateur (recommandé)

### <a name="vdi-installation"></a>Installation de VDI

Voici le processus de déploiement de l’application de bureau équipes. Pour obtenir des instructions complètes, voir [équipes pour l’Infrastructure de bureau virtualisés](teams-for-vdi.md).

1. Téléchargez le package MSI équipes à l’aide d’un des liens suivants en fonction de l’environnement. Nous vous recommandons la version 64 bits pour une VM VDI avec un système d’exploitation 64 bits.

    - [version 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [version 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Exécutez la commande suivante pour installer le fichier MSI de VM VDI (ou effectuer la mise à jour).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Cela installe des équipes pour les fichiers de programme. À ce stade, le programme d’installation or image est terminée.

    La prochaine ouverture de session interactive démarre les équipes et demande des informations d’identification. Notez qu’il n’est pas possible de désactiver le démarrage automatique des équipes lors de l’installation des équipes sur VDI à l’aide de la propriété ALLUSER.

3. Exécutez la commande suivante pour désinstaller le fichier MSI de la VM VDI (ou préparer la mise à jour).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Les équipes est désinstallé à partir des fichiers de programme.

## <a name="clean-up-and-redeployment-procedure"></a>Nettoyage et procédure redéploiement

Si un utilisateur désinstalle des équipes de leur profil utilisateur, le programme d’installation MSI effectue le suivi que l’utilisateur a désinstallé l’application équipes et n’est plus installer équipes pour ce profil utilisateur. Pour redéployer les équipes pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :

1. Désinstallation d’une application d’équipes installé pour chaque profil utilisateur. 
2. Après la désinstallation, supprimez le répertoire de manière récursive sous % localappdata%\Microsoft\Teams\.
3. Redéployer le package MSI sur cet ordinateur.

> [!TIP] 
> Vous pouvez utiliser notre script de [déploiement des équipes Microsoft nettoyer](scripts/Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Désactiver le démarrage automatique pour le programme d’installation MSI

Comportement par défaut de MSI consiste à installer le client équipes dès qu’un utilisateur se connecte et puis démarrer automatiquement les équipes. Vous pouvez modifier ce comportement avec les paramètres ci-dessous comme suit :

- Lorsqu’un utilisateur se connecte à Windows, équipes seront installés avec le fichier MSI
- Toutefois, le client équipes ne démarrera pas jusqu'à ce que l’utilisateur a démarré manuellement les équipes
- Un raccourci pour démarrer des équipes sera ajouté sur le bureau de l’utilisateur
- Une fois que le démarrage manuel, équipes seront démarrage automatique chaque fois que l’utilisateur se connecte en

Pour la version 32 bits
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Pour la version 64 bits
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Si vous exécutez manuellement le fichier MSI, veillez à exécuter avec des autorisations élevées. Même si vous l’exécutez en tant qu’administrateur, sans l’exécuter avec des autorisations élevées, le programme d’installation ne sera pas en mesure de configurer l’option pour désactiver le démarrage automatique.
