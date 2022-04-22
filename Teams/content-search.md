---
title: Utiliser la recherche de contenu dans Microsoft Teams
author: v-tophillips
ms.author: v-tophillips
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
description: Découvrez comment utiliser la recherche de contenu dans le portail de conformité Microsoft Purview pour rechercher Microsoft Teams contenu stocké dans Exchange Online, SharePoint Online, OneDrive Entreprise et OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88f44bffaa3bf2dc125dad5f2d7595d08f49bffd
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031859"
---
# <a name="use-content-search-in-microsoft-teams"></a>Utiliser la recherche de contenu dans Microsoft Teams

> [!NOTE]
> La recherche de contenu de messages et de fichiers dans [des canaux privés](private-channels.md) fonctionne différemment de celle des canaux standard. Pour en savoir plus, consultez [La recherche de contenu de canaux privés](#content-search-of-private-channels).

La recherche de contenu permet d’interroger Microsoft Teams informations couvrant Exchange, SharePoint Online et OneDrive Entreprise.

Pour en savoir plus, consultez [Recherche de contenu dans Microsoft 365](/microsoft-365/compliance/content-search).

Par exemple, à l’aide de **la recherche de contenu** sur votre boîte aux lettres Specs de fabrication et vos spécifications de fabrication SharePoint site, vous pouvez rechercher Teams conversations de canal standard à partir de Exchange, les chargements de fichiers et les modifications à partir de SharePoint Online et OneNote modifications.

Vous pouvez également ajouter des critères de requête à la **recherche de contenu** pour affiner les résultats retournés. Dans l’exemple ci-dessus, vous pouvez rechercher du contenu dans lequel les mots clés « **New Factory Specs » ont été utilisés** .

> [!TIP]
> Après avoir ajouté des conditions de recherche, vous pouvez exporter un rapport ou le contenu réel vers votre ordinateur à des fins d’analyse.

## <a name="content-search-of-private-channels"></a>Recherche de contenu de canaux privés

Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.

Étant donné que chaque canal privé possède sa propre collection de sites SharePoint qui est distincte du site d’équipe parent, les fichiers d’un canal privé sont gérés indépendamment de l’équipe parente.

Teams ne prenant pas en charge la recherche de contenu d’un canal unique, toute l’équipe doit donc être recherchée. Pour effectuer une recherche de contenu d’un canal privé, effectuez une recherche dans l’équipe, la collection de sites associée au canal privé (pour inclure des fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure des messages).

Utilisez les étapes suivantes pour identifier les fichiers et les messages dans un canal privé à inclure dans votre recherche de contenu.

### <a name="include-private-channel-files-in-a-content-search"></a>Inclure des fichiers de canal privé dans une recherche de contenu

Avant d’effectuer ces étapes, installez le [SharePoint Online Management Shell et connectez-vous à SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Exécutez ce qui suit pour obtenir la liste de toutes les collections de sites SharePoint associées aux canaux privés de l’équipe.

    ```PowerShell
    Get-SPOSite
    ```
2. Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et à l’ID de groupe d’équipe parent.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canal privé pertinents.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Inclure des messages de canal privé dans une recherche de contenu

Avant d’effectuer ces étapes, vérifiez que la [dernière version du module PowerShell Teams](teams-powershell-overview.md) est installée.

1. Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Exécutez la commande suivante pour obtenir la liste des membres du canal privé.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans le cadre de votre requête de recherche de contenu.

## <a name="related-topics"></a>Sujets associés

- [Cas eDiscovery dans le portail de conformité Microsoft Purview](/Office365/SecurityCompliance/ediscovery-cases)