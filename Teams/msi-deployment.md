---
title: Installation de Teams de Microsoft à l’aide de MSI
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Les administrateurs peuvent utiliser le fichier MSI d’équipes en bloc déployer Microsoft Teams pour sélectionner les utilisateurs ou ordinateurs.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a2031a567b96db6987c6c9c035631f17fd3d03f
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
<a name="install-microsoft-teams-using-msi"></a>Installation de Teams de Microsoft à l’aide de MSI
===========================================

Pour utiliser System Center Configuration Manager, ou stratégie de groupe ou les mécanismes de distribution 3ème partie pour le déploiement, Microsoft a fourni des fichiers MSI ( [32 bits](http://aka.ms/teams32bitmsi) et [64 bits](http://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour le déploiement en masse des équipes pour sélectionner les utilisateurs ou ordinateurs. Administrateurs peuvent utiliser ces fichiers pour déployer à distance des équipes afin que les utilisateurs ne doivent pas télécharger manuellement l’application d’équipes. Lors du déploiement, les équipes seront automatiquement lancement pour tous les utilisateurs qui s’inscrivent sur cet ordinateur. Nous vous recommandons de déployer le package sur l’ordinateur, afin que tous les nouveaux utilisateurs de la machine bénéficieront également de ce déploiement. 
 
> [!Note] 
> Pour en savoir plus à propos de SCCM, consultez [Introduction à System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandé)
1. Récupérer le dernier package
2. Utiliser les paramètres par défaut pré-remplis par le fichier MSI
3. Déploiement sur les machines lorsque cela est possible

## <a name="how-the-microsoft-teams-msi-package-works"></a>Fonctionne du package MSI d’équipes Microsoft

Le fichier MSI d’équipes place un programme d’installation dans les fichiers programme. Chaque fois qu’un utilisateur signe dans un nouveau profil d’utilisateur de Windows, le programme d’installation est lancé et une copie de l’application d’équipes sera installée dans le dossier appdata de l’utilisateur. Si un utilisateur possède déjà l’application équipes installée dans le dossier appdata, le programme d’installation MSI ignorera le processus pour cet utilisateur.

N’utilisez pas le fichier MSI pour déployer des mises à jour, le client sera automatiquement mise à jour lorsqu’il détecte qu'une nouvelle version est disponible à partir du service. Pour redéployer le programme d’installation les plus récent utilisent le processus de redéploiement de MSI décrite ci-dessous. Si vous déployez une version antérieure du package MSI, le client mettra automatiquement à jour lorsque cela est possible pour l’utilisateur. Si une version très ancienne obtient déployée, le fichier MSI déclenche une mise à jour de l’application avant que l’utilisateur est en mesure d’utiliser des équipes. 

> [!Important] 
> Nous ne pas recommandé de modifier les emplacements d’installation par défaut, car ceci risque de perturber le flux de la mise à jour. Qui puis finalement empêchera les utilisateurs d’accéder au service. 


## <a name="target-machine-requirements"></a>Exigences en matière de la machine cible

1. .NET framework 4.5 ou version ultérieure
2. Windows 7 ou version ultérieure
2. 3 Go d’espace disque pour chaque profil d’utilisateur (recommandé)

## <a name="clean-up-and-redeployment-procedure"></a>Nettoyage à distance et la procédure de redéploiement
Si un utilisateur désinstalle des équipes à partir de leur profil utilisateur, le programme d’installation MSI suivra que l’utilisateur a désinstallé l’application équipes et qu’il n’est plus installer des équipes pour le profil utilisateur. Pour redéployer des équipes pour cet utilisateur sur un ordinateur particulier, où il a été désinstallé, effectuez les opérations suivantes :

1. Désinstallation d’une application d’équipes installé pour chaque profil d’utilisateur 
2. Après la désinstallation, supprimez le répertoire de manière récursive sous %localappdata%\Microsoft\Teams\ 
3. Redéployer le package MSI sur cet ordinateur particulier

> [!TIP] 
> Vous pouvez utiliser notre script de [nettoyage de déploiement des équipes de Microsoft](.\scripts\Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.                              

