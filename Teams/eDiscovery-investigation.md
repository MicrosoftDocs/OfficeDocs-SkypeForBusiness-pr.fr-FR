---
title: Mener une recherche eDiscovery de contenu dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Découvrez les actions à entreprendre et le moment opportun pour mener une recherche eDiscovery, par exemple lorsque vous devez soumettre toutes les informations stockées électroniquement dans le cadre d'une procédure juridique.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27dac8bd72eaac581022431c3786b0f7487d137c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968045"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Mener une recherche eDiscovery de contenu dans Microsoft Teams
============================

Les grandes entreprises sont souvent exposées à des actions juridiques à forte pénalité qui demandent la soumission de toutes les informations stockées électroniquement (ESI).

Toutes les équipes 1:1 ou les discussions de groupe sont journalisées dans les boîtes aux lettres des utilisateurs correspondants, et tous les messages des canaux standard sont journalisés dans la boîte aux lettres du groupe représentant l’équipe. Les fichiers téléchargés dans les canaux standard sont décrits sous la fonctionnalité eDiscovery pour SharePoint Online et OneDrive entreprise.

> [!NOTE]
> la découverte électronique des messages et fichiers dans des [canaux privés](private-channels.md) ne fonctionne pas de la même manière que dans les canaux standard. Pour en savoir plus, voir [découverte électronique des canaux privés](#ediscovery-of-private-channels).

1.  Pour effectuer une analyse eDiscovery avec le contenu Microsoft Teams, reportez-vous à l’étape 1 de [ce](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) lien.

2.  Les données de Microsoft teams s’affichent sous forme de messages instantanés ou de conversations dans la sortie d’exportation eDiscovery d’Excel et vous pouvez les monter. PST dans Outlook pour afficher ces messages après l’exportation.

    Lors du montage du. PST pour l’équipe, Notez que toutes les conversations sont conservées dans le dossier de discussion d’équipe sous historique des conversations. Le titre du message s’aligne sur l’équipe et le canal. À partir de la consultation de l’image ci-dessous, vous pouvez voir ce message de Bob qui a affiché le canal Project 7 standard de l’équipe des spécifications de fabrication.

    ![Capture d’écran d’un dossier de discussion d’équipe dans la boîte aux lettres d’un utilisateur dans Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Pour afficher des discussions privées dans la boîte aux lettres d’un utilisateur, celles-ci se trouvent également dans le dossier de conversation d’équipe sous historique des conversations.

## <a name="ediscovery-of-guest-to-guest-chats"></a>Découverte électronique des discussions entre invités

Sans boîte aux lettres, les discussions invitées invitées (1xNs dans lesquelles il n’y a pas d’utilisateurs privés) ne sont pas indexées et ne sont pas incluses dans eDiscovery. Pour faciliter l’eDiscovery pour les discussions invitées, une boîte aux lettres Cloud (ou une boîte aux lettres fantôme) est créée pour le stockage des données 1xN. Une fois que les données de chat de l’équipe sont stockées dans la boîte aux lettres dans le Cloud, celles-ci sont indexées pour la découverte électronique et la recherche de contenu de conformité.

L’illustration suivante décrit le fonctionnement de eDiscovery pour les discussions invitées dans lesquelles il n’y a pas de boîte aux lettres.

![invité-à-invité-discussions-avec non-boîte aux lettres](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a>Découverte électronique des canaux privés

Les enregistrements de messages envoyés dans un canal privé sont remis à la boîte aux lettres de tous les membres du canal privé plutôt qu’à une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme pour indiquer le canal privé depuis lequel ils ont été envoyés.

Étant donné que chaque canal privé dispose de sa propre collection de sites SharePoint séparée du site d’équipe parent, les fichiers d’un canal privé sont gérés indépendamment de l’équipe parente.

Microsoft Teams ne prend pas en charge la découverte électronique d’un seul canal, de sorte que l’ensemble de l’équipe doit être recherché. Pour effectuer une recherche eDiscovery du contenu d’un canal privé, effectuez une recherche sur l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure des messages).

Procédez comme suit pour identifier les fichiers et les messages d’un canal privé à inclure dans votre recherche eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Inclusion de fichiers de canal privé dans une recherche eDiscovery

Avant d’effectuer cette procédure, installez [SharePoint Online Management Shell et connectez-vous à SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)online.

1. Exécutez la commande suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés au sein de l’équipe.

    ```
    Get-SPOSite
    ```
2. Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et de l’ID du groupe d’équipe parent.

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canaux privés pertinents, où $groupID est l’ID de groupe de l’équipe.

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Inclure des messages de canal privé dans une recherche eDiscovery

Avant d’effectuer cette procédure, vérifiez que vous avez installé la [dernière version du module teams PowerShell](teams-powershell-overview.md) .

1. Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe.

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Exécutez la commande suivante pour obtenir la liste des membres du canal privé.

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans le cadre de votre requête de recherche eDiscovery.

## <a name="related-topics"></a>Voir aussi

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)