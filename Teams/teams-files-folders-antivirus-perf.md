---
title: Fichiers et dossiers teams à exclure de l’analyse antivirus
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
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b4a4591bf25d7ef1a5b6efb9ab83c4508e26110
ms.sourcegitcommit: bcebe833d5ff4fcd3d6246fc5ed80980c6f31d0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37578806"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>Fichiers et dossiers teams à exclure de l’analyse antivirus
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