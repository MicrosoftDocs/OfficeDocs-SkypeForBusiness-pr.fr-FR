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
description: Découvrez comment utiliser la recherche de contenu dans le Centre de conformité Microsoft 365 pour rechercher du contenu Microsoft Teams stocké dans Exchange Online, SharePoint Online, OneDrive Entreprise et OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980438"
---
<a name="use-content-search-in-microsoft-teams"></a>Utiliser la recherche de contenu dans Microsoft Teams
=====================================

> [!NOTE]
> La recherche de contenu dans les messages et les fichiers dans les [canaux](private-channels.md) privés fonctionne différemment que dans les canaux standard. Pour en savoir plus, consultez [la recherche de contenu dans les canaux privés.](#content-search-of-private-channels)

La recherche de contenu permet d’interroger les informations de Microsoft Teams couvrant Exchange, SharePoint Online et OneDrive Entreprise.

Pour en savoir plus, consultez [la recherche de contenu dans Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search)

Par exemple,  en utilisant la recherche de contenu par rapport à votre boîte aux lettres Spécifications de fabrication et à votre site SharePoint Caractéristiques de fabrication, vous pouvez effectuer une recherche sur les conversations de canal standard de Teams à partir d’Exchange, les téléchargements et modifications des fichiers à partir de SharePoint Online et les modifications apportées à OneNote.

Vous pouvez également ajouter des critères de requête à **la** recherche de contenu pour affiner les résultats renvoyés. Dans l’exemple ci-dessus, vous pouvez rechercher le contenu dans lequel les mots clés «**Nouvelles spécifications d’usine »** ont été utilisés.

> [!TIP]
> Après avoir ajouté des conditions de recherche, vous pouvez exporter un rapport ou le contenu réel vers votre ordinateur pour analyse.

## <a name="content-search-of-private-channels"></a>Recherche de contenu dans les canaux privés

Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.

Chaque canal privé possède sa propre collection de sites SharePoint distincte du site d’équipe parent, les fichiers dans un canal privé sont gérés indépendamment de l’équipe parente.

Teams ne prend pas en charge la recherche de contenu sur un seul canal. Il faut donc effectuer une recherche dans toute l’équipe. Pour effectuer une recherche de contenu dans un canal privé, recherchez dans l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure les messages).

Pour identifier les fichiers et messages d’un canal privé à inclure dans votre recherche de contenu, utilisez les étapes suivantes.

### <a name="include-private-channel-files-in-a-content-search"></a>Inclure les fichiers de canal privé dans une recherche de contenu

Avant d’effectuer ces étapes, installez [SharePoint Online Management Shell et connectez-vous à SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Exécutez la suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés de l’équipe.

    ```PowerShell
    Get-SPOSite
    ```
2. Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et à l’ID du groupe d’équipe parent.

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

### <a name="include-private-channel-messages-in-a-content-search"></a>Inclure les messages de canal privé dans une recherche de contenu

Avant d’effectuer ces étapes, assurez-vous que vous avez installé la dernière version du [module Teams PowerShell.](teams-powershell-overview.md)

1. Exécutez la suivante pour obtenir une liste des canaux privés de l’équipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Exécutez l’information suivante pour obtenir la liste des membres d’un canal privé.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans votre requête de recherche de contenu.

## <a name="related-topics"></a>Voir aussi

- [Cas de découverte électronique dans le Centre de conformité Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 