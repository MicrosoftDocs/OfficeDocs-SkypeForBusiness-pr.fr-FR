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
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="ceedf-103">Fichiers et dossiers teams à exclure de l’analyse antivirus</span><span class="sxs-lookup"><span data-stu-id="ceedf-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="ceedf-104">Vous pouvez améliorer les performances globales du déploiement d’équipes en empêchant vos logiciels antivirus d’analyser certains fichiers et dossiers Teams.</span><span class="sxs-lookup"><span data-stu-id="ceedf-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="ceedf-105">Cela évite d’avoir recours aux ressources système pour analyser les fichiers et dossiers qui n’ont pas besoin d’être analysés.</span><span class="sxs-lookup"><span data-stu-id="ceedf-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="ceedf-106">Lors du téléchargement de fichiers ou du partage de fichiers par vos utilisateurs, ces fichiers ne passent pas par les emplacements indiqués dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="ceedf-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="ceedf-107">Les emplacements où vos utilisateurs peuvent télécharger, télécharger ou partager des fichiers continuent d’être analysés régulièrement par votre logiciel antivirus.</span><span class="sxs-lookup"><span data-stu-id="ceedf-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="ceedf-108">Fichiers et dossiers à ajouter à votre liste de protection antivirus</span><span class="sxs-lookup"><span data-stu-id="ceedf-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="ceedf-109">Utilisez les procédures prises en charge par votre logiciel antivirus pour ajouter les fichiers et dossiers suivants à vos listes approuvées.</span><span class="sxs-lookup"><span data-stu-id="ceedf-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="ceedf-110">Pour économiser les ressources système, il est préférable d’éviter les analyses antivirus de ces emplacements.</span><span class="sxs-lookup"><span data-stu-id="ceedf-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="ceedf-111">Logiciels</span><span class="sxs-lookup"><span data-stu-id="ceedf-111">Programs</span></span>

<span data-ttu-id="ceedf-112">Ajoutez les programmes d’équipe suivants à votre liste de protection antivirus.</span><span class="sxs-lookup"><span data-stu-id="ceedf-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="ceedf-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="ceedf-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="ceedf-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="ceedf-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="ceedf-115">Folder</span><span class="sxs-lookup"><span data-stu-id="ceedf-115">Folders</span></span>

<span data-ttu-id="ceedf-116">Ajoutez les dossiers d’équipes suivants à votre liste de protection antivirus.</span><span class="sxs-lookup"><span data-stu-id="ceedf-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="ceedf-117">Catégorie</span><span class="sxs-lookup"><span data-stu-id="ceedf-117">Category</span></span>  |<span data-ttu-id="ceedf-118">Lieu</span><span class="sxs-lookup"><span data-stu-id="ceedf-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="ceedf-119">Program Files</span><span class="sxs-lookup"><span data-stu-id="ceedf-119">Program files</span></span>  |<span data-ttu-id="ceedf-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="ceedf-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="ceedf-121">Fichiers de données</span><span class="sxs-lookup"><span data-stu-id="ceedf-121">Data files</span></span>     |<span data-ttu-id="ceedf-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="ceedf-122">%appdata%\Microsoft\Teams</span></span>\|