---
title: Installer Microsoft Teams à l’aide de MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Les administrateurs peuvent utiliser le MSI Teams pour déployer en bloc Microsoft Teams pour des utilisateurs ou sur des ordinateurs spécifiques.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7aaf355c1f1fc65855c7bffb7c5632929a084b88
ms.sourcegitcommit: 3a7d2131717327d9b2d16848758e31e10326a0bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2018
ms.locfileid: "24057602"
---
<a name="install-microsoft-teams-using-msi"></a>Installer Microsoft Teams à l’aide de MSI
=================================

Pour utiliser System Center Configuration Manager ou la stratégie de groupe ou les mécanismes de distribution de tiers pour le déploiement, Microsoft a fourni les fichiers MSI ( [32 bits](https://aka.ms/teams32bitmsi) et [64 bits](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en bloc des équipes pour sélectionner les utilisateurs ou ordinateurs. Administrateurs peuvent utiliser ces fichiers pour déployer des équipes à distance afin que les utilisateurs n’ont pas télécharger manuellement l’application d’équipes. Lors du déploiement, les équipes automatique de lancement pour tous les utilisateurs qui se connectent à sur cet ordinateur. (Vous pouvez désactiver lancement automatique après l’installation de l’application. [Voir ci-dessous](#disable-auto-lanuch-for-the-msi-installer).) Nous vous recommandons de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs de l’ordinateur bénéficient également ce déploiement. 
 
> [!Note] 
> Pour en savoir plus sur SCCM, voir [Introduction à System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandé)
1. Récupérer le dernier package.
2. Utilisez les valeurs par défaut préremplies par le fichier MSI.
3. Déployez sur les ordinateurs lorsque cela est possible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Comment fonctionne le package Microsoft équipes MSI

Le fichier MSI équipes place un programme d’installation dans les fichiers de programme. Chaque fois qu’un utilisateur se connecte à un nouveau profil d’utilisateur Windows, le programme d’installation est lancé et une copie de l’application des équipes sera installée dans le dossier appdata de l’utilisateur. Si l’utilisateur a déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignore le processus de cet utilisateur.

N’utilisez pas le fichier MSI pour déployer des mises à jour, car le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service. Pour redéployer le programme d’installation le plus récent utiliser le processus de redéploiement MSI décrite ci-dessous. Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur. Si une version ancienne très obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes. 

> [!Important] 
> Nous ne pas recommandé de modifier les emplacements d’installation par défaut, comme ceci risque de perturber le flux de mise à jour. Trop ancienne une version empêchera finira par les utilisateurs d’accéder au service. 


## <a name="target-computer-requirements"></a>Exigences pour l’ordinateur cible

- .NET framework 4.5 ou version ultérieure
- Windows 7 ou version ultérieure
- 3 Go d’espace disque requis pour chaque profil utilisateur (recommandé)

## <a name="clean-up-and-redeployment-procedure"></a>Nettoyage et procédure redéploiement
Si un utilisateur désinstalle des équipes de leur profil utilisateur, le programme d’installation MSI effectue le suivi que l’utilisateur a désinstallé l’application équipes et n’est plus installer équipes pour ce profil utilisateur. Pour redéployer les équipes pour cet utilisateur sur un ordinateur particulier où il a été désinstallé, procédez comme suit :

1. Désinstallation d’une application d’équipes installé pour chaque profil utilisateur. 
2. Après la désinstallation, supprimez le répertoire de manière récursive sous % localappdata%\Microsoft\Teams\. 
3. Redéployer le package MSI sur cet ordinateur.

> [!TIP] 
> Vous pouvez utiliser notre script de [déploiement des équipes Microsoft nettoyer](.\scripts\Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.  
                    
## <a name="disable-auto-lanuch-for-the-msi-installer"></a>Désactiver lanuch automatique pour le programme d’installation MSI

Si vous souhaitez désactiver le démarrage automatique, entrez l’invite de commandes suivante :

`msiexec /i Teams_windows.exe OPTIONS="noAutoStart=false"`

