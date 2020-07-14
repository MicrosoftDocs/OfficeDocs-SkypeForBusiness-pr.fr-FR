---
title: Utiliser la recherche de contenu dans Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Apprenez-en davantage sur l’utilisation de la recherche de contenu dans Microsoft teams pour interroger les informations de Microsoft teams à partir d’Exchange, SharePoint Online, OneDrive entreprise et OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d05d815a74fc395c06763920014b7de453847bec
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121524"
---
<a name="use-content-search-in-microsoft-teams"></a>Utiliser la recherche de contenu dans Microsoft Teams
=====================================

> [!NOTE]
> La recherche de contenu dans les messages et les fichiers de [canaux privés](private-channels.md) ne fonctionne pas de la même manière que dans les canaux standard. Pour en savoir plus, voir [recherche de contenu de canaux privés](#content-search-of-private-channels).

La recherche de contenu fournit un moyen de rechercher des informations sur Microsoft teams dans Exchange, SharePoint Online et OneDrive entreprise.

Pour en savoir plus, voir [recherche de contenu dans Microsoft 365 ou Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

Par exemple, l’utilisation de la **recherche de contenu** par rapport aux spécifications de fabrication dans le site SharePoint, vous pouvez effectuer des recherches sur des conversations par canal standard d’Exchange, des téléchargements de fichiers et des modifications de SharePoint Online, et des modifications de OneNote.

Vous pouvez également ajouter des critères de requête à la **recherche de contenu** pour affiner les résultats renvoyés. Dans l’exemple ci-dessus, vous pouvez chercher le contenu dans lequel les mots clés «**New Factory specs »** étaient utilisés.

> [!TIP]
> Après avoir ajouté des conditions de recherche, vous pouvez exporter un rapport ou les données vers votre ordinateur pour analyse.

## <a name="content-search-of-private-channels"></a>Recherche de contenu de canaux privés

Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.

Étant donné que chaque canal privé dispose de sa propre collection de sites SharePoint séparée du site d’équipe parent, les fichiers d’un canal privé sont gérés indépendamment de l’équipe parente.

Microsoft Teams ne prend pas en charge la recherche de contenu d’un seul canal ; de sorte que l’ensemble de l’équipe doit être recherché. Pour effectuer une recherche de contenu d’un canal privé, effectuez une recherche dans l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure des messages).

Procédez comme suit pour identifier les fichiers et les messages dans un canal privé à inclure dans la recherche de contenu.

### <a name="include-private-channel-files-in-a-content-search"></a>Inclure des fichiers de canal privé dans une recherche de contenu

Avant d’effectuer cette procédure, installez [SharePoint Online Management Shell et connectez-vous à SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)online.

1. Exécutez la commande suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés au sein de l’équipe.

    ```PowerShell
    Get-SPOSite
    ```
2. Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et de l’ID du groupe d’équipe parent.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canaux privés pertinents.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Inclure des messages de canal privé dans une recherche de contenu

Avant d’effectuer cette procédure, vérifiez que vous avez installé la [dernière version du module teams PowerShell](teams-powershell-overview.md) .

1. Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Exécutez la commande suivante pour obtenir la liste des membres du canal privé.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans le cadre de votre requête de recherche de contenu.

## <a name="related-topics"></a>Voir aussi

- [cas de découverte électronique dans le centre de conformité Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 