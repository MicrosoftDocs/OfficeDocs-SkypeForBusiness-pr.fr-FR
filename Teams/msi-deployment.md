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
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882037"
---
<a name="install-microsoft-teams-using-msi"></a>Installer Microsoft Teams à l’aide de MSI
=================================

Pour utiliser System Center Configuration Manager, une stratégie de groupe ou d’autres mécanismes de distribution tiers pour un déploiement à grande échelle, Microsoft a fourni des fichiers MSI ([32 bits](https://aka.ms/teams32bitmsi) et [64 bits](https://aka.ms/teams64bitmsi)) que les administrateurs peuvent utiliser pour déployer Teams en bloc pour des utilisateurs ou sur des ordinateurs spécifiques. Les administrateurs peuvent utiliser ces fichiers pour déployer Teams à distance, afin que les utilisateurs n’aient pas à télécharger l’application Teams. Une fois déployée, l’application Teams se lancera automatiquement pour tous les utilisateurs qui se connectent sur cette machine. Nous vous recommandons de déployer le package sur l’ordinateur pour que tous les nouveaux utilisateurs de celui-ci bénéficient également de ce déploiement. 
 
> [!Note] 
> Pour en savoir plus sur SCCM, reportez-vous à la section [Présentation de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procédure de déploiement (recommandée)
1. Récupérez le package le plus récent.
2. Utilisez les paramètres par défaut préremplis par le MSI.
3. Effectuez le déploiement sur les ordinateurs lorsque cela est possible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Fonctionnement du package MSI Microsoft Teams

Le MSI Teams placera un programme d'installation dans les fichiers programmes. Lorsqu'un utilisateur se connectera avec un nouveau profil d’utilisateur Windows, le programme d'installation sera lancé et une copie de l’application Teams sera installée dans le dossier des données d’application de cet utilisateur. Si un utilisateur dispose déjà de l’application Teams installée dans le dossier des données d’application, le programme d'installation MSI ignorera le processus pour cet utilisateur.

N’utilisez pas le MSI pour déployer des mises à jour, car le client se mettra à jour automatiquement lorsqu'il détectera qu’une nouvelle version est disponible depuis le service. Pour redéployer le programme d'installation le plus récent, utilisez le processus de redéploiement de MSI décrit ci-dessous. Si vous déployez une version plus ancienne du package MSI, le client se mettra à jour automatiquement lorsque cela sera possible pour l’utilisateur. Si une version très ancienne est déployée, le MSI déclenchera une mise à jour de l’application avant que l’utilisateur puisse utiliser Teams. 

> [!Important] 
> Nous vous conseillons de ne pas modifier les emplacements d’installation par défaut, car cela risquerait d’interrompre le flux de mise à jour. Une version trop ancienne empêchera les utilisateurs d’accéder au service. 


## <a name="target-computer-requirements"></a>Configuration requise pour les ordinateurs cibles

- .NET Framework 4.5 ou version ultérieure
- Windows 7 ou version ultérieure
- 3 Go d’espace disque pour chaque profil d’utilisateur (recommandé)

## <a name="clean-up-and-redeployment-procedure"></a>Procédure de nettoyage et de redéploiement
Si un utilisateur désinstalle Teams de son profil d’utilisateur, le programme d'installation MSI enregistrera que l’utilisateur a désinstallé l’application Teams et ne l’installera plus pour ce profil d’utilisateur. Pour redéployer Teams pour cet utilisateur sur un ordinateur spécifique sur lequel il a été désinstallé, procédez comme suit :

1. Désinstallez l’application Teams installée pour chaque profil d’utilisateur. 
2. Ensuite, supprimez le répertoire de manière récursive sous %localappdata%\Microsoft\Teams\. 
3. Redéployez le package MSI sur cet ordinateur.

> [!TIP] 
> Vous pouvez utiliser notre script de [nettoyage du déploiement de Microsoft Teams](.\scripts\Powershell-script-teams-deployment-clean-up.md) pour effectuer les étapes 1 et 2 via SCCM.                              

