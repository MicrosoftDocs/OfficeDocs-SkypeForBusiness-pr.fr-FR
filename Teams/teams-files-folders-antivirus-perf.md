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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dbb4b31fc3cddd8c434eb5c94e4f8801ff0633b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837674"
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

### <a name="folders"></a>Folder

Ajoutez les dossiers d’équipes suivants à votre liste de protection antivirus.

|Catégorie  |Lieu  |
|---------|---------|
|Program Files  |%localappdata%\Microsoft\Teams|
|Fichiers de données     |%appdata%\Microsoft\Teams\|