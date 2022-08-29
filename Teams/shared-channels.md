---
title: Canaux partagés dans Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez comment utiliser et gérer des canaux partagés dans Microsoft Teams.
ms.openlocfilehash: 767773d8c7f91bb290332fbd0976fb638edb2b8b
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397225"
---
# <a name="shared-channels-in-microsoft-teams"></a>Canaux partagés dans Microsoft Teams

Les canaux partagés dans Microsoft Teams créent des espaces de collaboration où vous pouvez inviter des personnes qui ne font pas partie de l'équipe. Seuls les utilisateurs qui sont propriétaires ou membres du canal partagé peuvent accéder à ce dernier. Alors que les invités (personnes disposant de comptes d'invités Azure Active Directory dans votre organisation.) ne peuvent pas être ajoutés à un canal partagé, vous pouvez inviter des personnes extérieures à votre organisation à participer à un canal partagé en utilisant Azure AD B2B direct connect.

Vous pouvez utiliser un canal partagé si vous souhaitez collaborer avec un groupe de personnes appartenant à des équipes différentes. Par exemple, les personnes des services d'ingénierie, de vente et d'assistance qui travaillent toutes sur différents aspects d'un même projet ou produit pourraient utiliser un canal partagé pour collaborer.

Seuls les membres des canaux partagés peuvent voir et participer aux canaux partagés auxquels ils sont ajoutés. Les autres membres de l'équipe à laquelle le canal partagé est connecté ne verront pas le canal.

Lorsqu'un canal partagé est créé, il est lié à l'équipe parente et ne peut pas être déplacé vers une autre équipe. En outre, les canaux partagés ne peuvent pas être convertis en canaux standard et vice versa.

[Comparer les canaux partagés avec d’autres types de canaux](/microsoftteams/teams-channels-overview#channel-feature-comparison).

## <a name="getting-started-with-shared-channels"></a>Prise en main des canaux partagés

Les canaux partagés sont activés par défaut dans Teams. Vous pouvez choisir si les gens peuvent créer des canaux partagés, s'ils peuvent les partager avec des personnes extérieures à votre organisation, et s'ils peuvent participer à des canaux partagés externes en [créant une stratégie de canal](/MicrosoftTeams/teams-policies).

Si vous prévoyez de partager des canaux avec des personnes extérieures à votre organisation, lisez [Planifier la collaboration externe](/microsoft-365/solutions/plan-external-collaboration) pour connaître les considérations importantes en matière de planification.

Le partage de canaux avec des personnes extérieures à votre organisation nécessite également que vous configuriez des paramètres d'accès inter-locataires dans Azure AD. Chaque organisation avec laquelle vous souhaitez partager des canaux doit également compléter cette configuration. Voir [Collaborer avec des participants externes dans un canal](/microsoft-365/solutions/collaborate-teams-direct-connect) pour plus de détails.

## <a name="shared-channel-creation"></a>Création d’un canal partagé

Seuls les propriétaires d’équipe peuvent créer un canal partagé. Les membres de l’équipe et les invités ne peuvent pas les créer. La possibilité de créer des canaux privés peut être gérée au niveau de l’équipe et au niveau de l’organisation. Utilisez des [stratégies](teams-policies.md) pour contrôler les utilisateurs de votre organisation autorisés à créer des canaux privés.

La personne qui crée un canal partagé devient le propriétaire du canal partagé et seul le propriétaire du canal partagé peut directement ajouter ou supprimer des personnes de celui-ci. (Vous pouvez ajouter plus d'un propriétaire si vous le souhaitez.) Un propriétaire de canal partagé peut ajouter n'importe qui de l'organisation à un canal partagé qu'il a créé. Les membres d'un canal partagé disposent d'un espace de conversation sécurisé, et lorsque de nouveaux membres sont ajoutés, ils peuvent voir toutes les conversations (même les anciennes) de ce canal partagé.

Les propriétaires d'équipe peuvent voir les noms de tous les canaux partagés dans leur équipe et peuvent également supprimer tout canal partagé dans l'équipe. Les propriétaires d'équipe ne peuvent pas voir les fichiers dans un canal partagé ou les conversations et la liste des membres d'un canal partagé à moins qu'ils ne soient membres de ce canal partagé.

Les membres de l'équipe ne peuvent voir que les canaux partagés auxquels ils ont été ajoutés.

Le clonage d'une équipe ne clonera pas les canaux partagés associés.

## <a name="shared-channel-deletion"></a>Suppression des canaux partagés

Le canal partagé supprimé peut être restauré dans les 30 jours suivant sa suppression. Lorsqu'un canal partagé supprimé est restauré, toutes les adhésions précédentes (partage individuel et par équipe) seront restaurées.

Les équipes supprimées peuvent être restaurées dans les 30 jours suivant leur suppression. Lorsqu’une équipe est supprimée, tous les canaux partagés sont également supprimés. Lorsqu'une équipe supprimée est restaurée, tous les canaux partagés sont également restaurés, ainsi que toutes les relations de partage.

Lorsqu'une équipe est archivée, le partage individuel reste intact, mais le partage avec des équipes autres que l'équipe mère est supprimé. Lorsque l'équipe archivée est désarchivée, tous les canaux partagés seront restaurés avec un partage individuel uniquement.

## <a name="adding-and-removing-owners-and-members"></a>Ajouter et supprimer des propriétaires et des membres

Un propriétaire de canal partagé ne peut pas être supprimé par le client Teams s'il est le dernier propriétaire d'un ou plusieurs canaux partagés.

Si le dernier propriétaire du canal partagé quitte votre organisation ou s'il est supprimé du groupe Microsoft 365 associé à l'équipe, un membre du canal partagé est automatiquement promu propriétaire du canal partagé. Pensez à ajouter plus d'un propriétaire pour éviter cette situation.

> [!NOTE]
> Les participants externes doivent être ajoutés à l’aide de leur UPN, plutôt que de leur adresse e-mail, si les deux ne correspondent pas dans Azure Active Directory.

## <a name="channel-owner-settings"></a>Paramètres du propriétaire du canal

Chaque canal partagé possède ses propres paramètres que le propriétaire du canal peut gérer, y compris la possibilité d'ajouter et de supprimer des membres, d'ajouter des onglets et d'effectuer des @mentionnements pour l'ensemble du canal. Ces paramètres sont indépendants de ceux de l’équipe parente. Lorsqu'un canal partagé est créé, il hérite des paramètres de l'équipe parente, après quoi ses paramètres peuvent être modifiés indépendamment de ceux de l'équipe parente.

Le propriétaire du canal partagé peut cliquer sur **Gérer le canal**, puis utiliser les onglets **Membres** et **Paramètres** pour ajouter ou supprimer des membres et modifier les paramètres.

## <a name="shared-channel-owner-and-member-actions"></a>Propriétaire de canal privé et actions des membres

Le tableau suivant décrit les actions que les propriétaires, les membres et les invités peuvent effectuer dans les canaux privés.

|Action  |Propriétaire d’une équipe|Membre de l’équipe|Invité de l’équipe|Propriétaire d’un canal partagé|Membre d’un canal partagé|Participant externe à un canal partagé|
|---------|---------|---------|---------|---------|---------|---------|
|Créer un canal partagé|Contrôlée par l’administrateur|Contrôlée par l’administrateur et le propriétaire de l’équipe|Non|N/A|Non|Non|
|Supprimer un canal partagé|Oui|Non|Non|Oui|Non|Non|
|Quitter un canal partagé|N/A|N/A|S/O|Oui, à moins qu’il ne soit le dernier propriétaire|Oui|Oui|
|Modifier un canal partagé|Non|N/A|N/A|Oui|Non|Non|
|Restaurer un canal privé supprimé|Oui|Non|Non|Oui|Non|Non|
|Ajouter des membres|Non|N/A|N/A|Oui|Non|Non|
|Modifier les paramètres|Non|N/A|N/A|Oui|Non|Non|
|Gérer les onglets et les applications|Non|N/A|N/A|Oui, les applications doivent être installées pour l’équipe|Contrôlé par le propriétaire du canal|Non|

## <a name="shared-channel-sharepoint-sites"></a>Sites SharePoint de canal partagé

Chaque canal partagé a [son propre site SharePoint](/SharePoint/teams-connected-sites). Le site séparé doit garantir que l'accès aux fichiers du canal partagé est limité aux seuls membres du canal partagé. Ces sites sont créées avec une bibliothèque de documents par défaut, et peuvent être facilement améliorés et transformés en site complet via l’[interface de gestion de site](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Chaque site est créé dans la même zone géographique que le site de l’équipe parente. Ces sites légers ont un ID de modèle personnalisé, « TEAMCHANNEL#1 », pour simplifier la gestion via PowerShell et l’API Graph. 

Un site de canal partagé hérite de l’étiquette de confidentialité de l’équipe parente. Il en va de même si le canal est partagé directement avec une autre équipe.

> [!NOTE]
> Seules les personnes disposant d’autorisations de propriétaire ou de membre dans le canal auront accès au contenu du site de canal partagé. Les membres de l’équipe parente et les administrateurs n’auront pas accès, sauf s’ils sont également membres du canal.

L'adhésion au propriétaire du site et aux groupes de membres est synchronisée avec l'adhésion au canal partagé. Les autorisations de site pour un site de canal partagé ne peuvent pas être gérées indépendamment par SharePoint. 

Teams gère le cycle de vie du site de canal partagé. Si le site est supprimé en dehors de Teams, il est restauré automatiquement dans les quatre heures, pour autant que le canal partagé soit toujours actif. Si le site est définitivement supprimé, un nouveau site est provisionné pour le canal partagé.

Si un canal partagé ou une équipe contenant un canal partagé est restauré, les sites sont restaurés avec lui. Si un canal partagé ou une équipe contenant un canal partagé est restauré, les sites sont restaurés avec lui.

## <a name="shared-channel-messages"></a>Messages de canal partagé

Les messages du canal partagé sont stockés dans une boîte aux lettres système dédiée associée au canal partagé plutôt que dans la boîte aux lettres du groupe.

Pour plus d'informations sur l'exécution d'une recherche eDiscovery pour les messages des canaux partagés, voir [Effectuer une recherche eDiscovery du contenu dans Microsoft Teams](ediscovery-investigation.md).

## <a name="considerations-around-file-access-in-shared-channels"></a>Éléments à prendre en compte concernant l’accès aux fichiers dans les canaux privés

Les fichiers, dossiers et blocs-notes OneNote d'un canal partagé peuvent être partagés avec des personnes extérieures au canal en utilisant [le partage de fichiers SharePoint standard](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c).

Si un utilisateur se voit accorder l'accès à un fichier, un dossier ou un bloc-notes dans un canal partagé via SharePoint, le fait de retirer l'utilisateur de l'équipe ou du canal partagé ne supprimera pas l'accès de l'utilisateur au fichier, au dossier ou au bloc-notes.

Si un bloc-notes existant est ajouté comme onglet à un canal partagé, l'accès au canal partagé n'est pas modifié et le bloc-notes conserve ses autorisations existantes.

## <a name="resources-for-your-users"></a>Ressources pour vos utilisateurs

Les articles suivants peuvent être utiles aux utilisateurs de votre organisation lorsqu'ils utilisent des canaux partagés.

[Créer un canal partagé dans Teams](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Partager un canal avec des personnes dans Teams](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[Partager un canal avec une équipe](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[Pourquoi utiliser un canal partagé et d’autres types de canaux dans Teams ?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Invités et canaux partagés dans Teams](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Rôles partagés de propriétaire et de membre du canal dans Teams](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels"></a>Limites pour les canaux partagés

Le tableau suivant décrit le nombre maximal de canaux et de membres.

|Maximum...|Valeur|Remarques|
|:---------|:----|:----|
|Membres d’une équipe|25 000|Inclut tous les utilisateurs de l’équipe et dirige les membres dans les canaux partagés.|
|Canaux partagés par équipe|200|Hébergé et partagé avec l’équipe. (Inclut les canaux supprimés pendant leur fenêtre de récupération de 30 jours.)|
|Teams un canal peut être partagé avec|50|Exclusion de l’équipe parente|
|Membres dans un canal partagé|5 000 membres directs, y compris jusqu’à 50 équipes. (Chaque équipe avec laquelle le canal est partagé compte comme un membre aux fins de cette limite).|Les mises à jour en temps réel ne sont disponibles que pour 25 000 utilisateurs à la fois et seuls 25 000 utilisateurs apparaîtront dans la liste des chaînes.|

Les limitations suivantes s’appliquent également :

- Seuls les comptes professionnels ou scolaires Azure AD sont pris en charge pour les participants externes.

- Les canaux partagés supportent les onglets à l’exception de Stream, Planner et Forms.

- Les bots, connecteurs et extensions de message ne sont pas pris en charge.

- Lorsque vous créez une équipe à partir d’une équipe existante, les canaux privés de l’équipe existante ne seront pas copiés.

- Pour l’instant, les notifications des canaux privés ne sont pas incluses dans les messages électroniques d’activité manqués.

- Les canaux partagés ne sont pas pris en charge dans les équipes de classe.

## <a name="supported-apps-in-shared-channels"></a>Applications prises en charge dans les canaux partagés

Pour plus d’informations sur la préparation de votre application pour les canaux partagés, consultez [Comment ouvrir votre application à la collaboration inter-organisationnelle avec Microsoft Teams Connect](https://mybuild.microsoft.com/sessions/4d84d73c-08de-4f56-990b-2a73b2037df1).

Les applications suivantes sont prises en charge pour une utilisation dans des canaux partagés. 

- Activité
- Adobe Acrobat Sign
- Asana
- Calendrier
- Calendar Pro
- Appel
- Conversation
- Code by Vivani
- Conceptboard
- Excel
- FileBrowser
- Fichiers
- Flipgrid
- Freehand by InVision
- HeyTaco
- Jira Cloud
- Kahoot!
- Listes
- Lucidchart
- Lumio
- MeisterTask
- MindMeister
- Mindomo
- Miro
- Monday.com
- MURAL
- Nearpod
- OneNote
- fichier PDF ;
- Pear Deck
- PowerPoint
- Priority Matrix
- Quicklinks
- Quizlet
- Saved
- Scrum-Poker
- Rechercher
- Microsoft Office SharePoint Online
- SharePoint Pages
- Slido
- Smartsheet
- SurveyMonkey
- Tasks in a Box
- Teams Manager
- TeamViewer
- Travail d’équipe
- Testportal
- TrackingTime
- Trello
- Vevox
- Visio
- VSTS
- Wakelet
- Web
- Wooclap
- Mot
- YouTube
- Zendesk
- Zoho Projects

## <a name="related-topics"></a>Rubriques connexes

[Vue d’ensemble de la connexion directe B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurer les paramètres d’accès entre locataires pour la connexion directe B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Présentation des équipes et des canaux dans Teams](teams-channels-overview.md)

[Canaux privés dans Microsoft Teams](/microsoftteams/private-channels)
