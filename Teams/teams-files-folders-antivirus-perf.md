---
title: Fichiers et dossiers Teams à exclure de l’analyse antivirus
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Améliorez les performances des équipes en excluant certains fichiers et dossiers de l’analyse antivirus classique.
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579590"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>Fichiers et dossiers Teams à exclure de l’analyse antivirus
=================================

Vous pouvez améliorer les performances globales du déploiement d’équipes en empêchant vos logiciels antivirus d’analyser certains fichiers et dossiers Teams. Cela évite d’avoir recours aux ressources système pour analyser les fichiers et dossiers qui n’ont pas besoin d’être analysés.

> [!NOTE]
> Lors du téléchargement de fichiers ou du partage de fichiers par vos utilisateurs, ces fichiers ne passent pas par les emplacements indiqués dans la section suivante. Les emplacements où vos utilisateurs peuvent télécharger, télécharger ou partager des fichiers continuent d’être analysés régulièrement par votre logiciel antivirus.

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>Fichiers et dossiers à ajouter à votre liste de protection antivirus

Utilisez les procédures prises en charge par votre logiciel antivirus pour ajouter les fichiers et dossiers suivants à vos listes approuvées. Pour économiser les ressources système, il est préférable d’éviter les analyses antivirus de ces emplacements.

### <a name="programs"></a>Logiciels

Ajoutez les programmes d’équipe suivants à votre liste de protection antivirus.

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

