---
title: Conduire une étude eDiscovery du contenu
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez ce que vous pouvez faire lorsque vous devez effectuer une découverte électronique, comme lorsque vous avez besoin de transmettre toutes les informations stockées électroniquement à des fins juridiques.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 53f3f1f3d8146b06b69a70dbbf7c00bdb979c43c
ms.sourcegitcommit: b6aeaa3d98c29bdc120db8ccfcb7ff2c11d246af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570823"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Mener une recherche eDiscovery de contenu dans Microsoft Teams

Les grandes entreprises sont souvent exposées à des actions juridiques à forte pénalité qui demandent la soumission de toutes les informations stockées électroniquement (ESI). Le contenu de Microsoft teams peut être recherché et utilisé lors d’investigations eDiscovery.

## <a name="overview"></a>Vue d’ensemble

Toutes les discussions de groupe et Microsoft teams 1:1 sont journalisées dans les boîtes aux lettres des utilisateurs correspondants. Tous les messages de canal standard sont journalisés dans la boîte aux lettres de groupe représentant l’équipe. Les fichiers téléchargés dans les canaux standard sont décrits sous la fonctionnalité eDiscovery pour SharePoint Online et OneDrive entreprise.

la découverte électronique des messages et fichiers dans des [canaux privés](private-channels.md) fonctionne différemment de celles des canaux standard. Pour en savoir plus, voir [découverte électronique des canaux privés](#ediscovery-of-private-channels).

Le contenu de toutes les équipes n’est pas eDiscoverable. Le tableau suivant répertorie les types de contenu qui peuvent être localisés via eDiscovery.

| Type de contenu | eDiscoverable | Remarques |
|:--- | --- |:--- |
| Messages de discussion teams | Oui |  |
| Messages de canal privé | Oui | |
| Nom du canal | Non | |
| Conversations par messagerie instantanée de réunion | Oui | |
| Métadonnées de réunion<sup>1</sup> | Oui |  |
| Messages modifiés | Oui | Si l’utilisateur est en attente, les versions précédentes des messages modifiés sont conservées. |
| Emoji, fichiers GIF, autocollants | Oui | |
| Extraits de code | Non | |
| Liens de discussion | Oui | |
| Réactions (j’aime, coeurs, etc.) | Non | |
| Images incorporées | Oui | |
| Contenu | Oui | |
| Objet | Oui | |
| Offres | Oui | Le contenu mentionné peut être recherché. Toutefois, les résultats de la recherche n’indiquent pas que le contenu a été placé entre guillemets. |
| Enregistrements audio | Non | |

<sup>1</sup> les métadonnées de réunion incluent les éléments suivants :

- Heures de début et de fin d’appel et durée
- Appel/réunion et conservation des événements pour chaque participant
- Connexion/appels VOIP
- Jointure anonyme
- Affiliation d’utilisateur fédéré
- Participation des utilisateurs invités

L’image montre un exemple de métadonnées.

> [!div class="mx-imgBorder"]
> ![L’image est du CVR les métadonnées de la réunion.](media/conversationOption3.png)

Voici un exemple de conversation par messagerie instantanée entre participants lors de la réunion.

![Conversation entre les participants dans Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversation entre participants dans les résultats de recherche eDiscovery.](media/MeetingImConversation2.png)

Pour effectuer une enquête eDiscovery avec le contenu Microsoft Teams, passez à l’étape 1 de la rubrique mise [en route de](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)Microsoft teams eDiscovery.

Les données de Microsoft teams s’affichent sous forme de messages instantanés ou de conversations dans la sortie d’exportation eDiscovery d’Excel. Vous pouvez ouvrir le `.pst` fichier dans Outlook pour afficher ces messages après l’exportation.

Lorsque vous affichez le fichier. pst de l’équipe, toutes les conversations sont conservées dans le dossier de conversation d’équipe sous historique des conversations. Le titre du message contient le nom de l’équipe et le nom du canal. Par exemple, l’image ci-dessous montre un message de Bob qui a affiché le canal Project 7 standard de l’équipe des spécifications de fabrication.

![Capture d’écran d’un dossier de discussion d’équipe dans la boîte aux lettres d’un utilisateur dans Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Les discussions privées de la boîte aux lettres d’un utilisateur sont stockées dans le dossier de discussion d’équipe sous historique des conversations.

## <a name="ediscovery-of-private-channels"></a>Découverte électronique des canaux privés

Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.

Étant donné que chaque canal privé dispose de sa propre collection de sites SharePoint séparée du site d’équipe parent, les fichiers d’un canal privé sont gérés indépendamment de l’équipe parente.

Microsoft Teams ne prend pas en charge la recherche eDiscovery d’un seul canal au sein d’une équipe, de sorte que l’ensemble de l’équipe doit être recherché. Pour effectuer une recherche eDiscovery du contenu d’un canal privé, effectuez une recherche sur l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure des messages).

Procédez comme suit pour identifier les fichiers et les messages d’un canal privé à inclure dans votre recherche eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Inclusion de fichiers de canal privé dans une recherche eDiscovery

Avant d’effectuer cette procédure, installez [SharePoint Online Management Shell et connectez-vous à SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)online.

1. Exécutez la commande suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés au sein de l’équipe.

    ```PowerShell
    Get-SPOSite
    ```

2. Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et de l’ID du groupe d’équipe parent.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canaux privés pertinents, où $groupID est l’ID de groupe de l’équipe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Inclure des messages de canal privé dans une recherche eDiscovery

Avant d’effectuer cette procédure, vérifiez que vous avez installé la [dernière version du module teams PowerShell](teams-powershell-overview.md) .

1. Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Exécutez la commande suivante pour obtenir la liste des membres du canal privé.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans le cadre de votre requête de recherche eDiscovery.

## <a name="advanced-ediscovery"></a>eDiscovery avancée

Le contenu de Microsoft teams peut également être exploré et conservé à l’aide du [flux de travail EDiscovery avancé](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20). Si eDiscovery fournit une gamme de fonctionnalités de recherche, de mise en attente et d’exportation, l’eDiscovery fournit aux administrateurs de la conformité des outils supplémentaires pour identifier les sources de données et analyser leur contenu.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Flux de travail du dépositaire de découverte avancée pour le contenu d’équipes

Les dépositaires peuvent être membres de diverses équipes. Vous pouvez capturer du contenu d’équipes pertinent pour ces dépositaires. Pour plus d’informations et des instructions sur le flux de travail de dépositaire, voir [flux de travail de découverte électronique avancé](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

Après avoir ajouté un dépositaire, cliquez sur le bouton **suivant** , puis sur le bouton **Ajouter** . Une fenêtre s’affiche et vous invite à sélectionner des emplacements supplémentaires pour afficher l’ensemble des membres du dépositaire ainsi que les emplacements des sites SharePoint correspondants pour leurs données. À partir de l’ensemble de ces sources de données et équipes, vous pouvez sélectionner le contenu que vous voulez utiliser pour la découverte électronique, puis placer cet utilisateur et toutes les sources de données que vous avez identifiées en attente.

Vous pouvez indiquer si vous souhaitez inclure le contenu Exchange, le contenu de OneDrive ou les deux. Le contenu Exchange inclut tout le contenu de l’application dans les boîtes aux lettres de l’utilisateur, tel qu’un message électronique, le contenu de l’équipe qui est stocké dans sa boîte aux lettres, etc. Le contenu OneDrive inclut non seulement le contenu de l’utilisateur, mais aussi tout le contenu de l’équipe qui est stocké dans OneDrive, par exemple, les discussions 1:1, 1 : N discussions et les fichiers partagés dans les discussions.

Vous avez également la possibilité d’associer une équipe dont le dépositaire est membre de telle sorte que les messages et les fichiers auxquels le dépositaire a accès soient inclus. De plus, les autres membres de l’équipe peuvent être associés à un dépositaire. Pour plus d’informations, reportez-vous [à ajouter des dépositaires à un cas de découverte électronique avancée](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).

> [!NOTE]
> la découverte électronique des messages et fichiers dans des [canaux privés](private-channels.md) fonctionne différemment de celles des canaux standard. Pour en savoir plus, voir [découverte électronique des canaux privés](#ediscovery-of-private-channels).

### <a name="placing-a-data-source-on-hold"></a>Mise en attente d’une source de données

S’il n’existe aucun utilisateur spécifique à désigner en tant que dépositaire, vous pouvez mettre en attente une source de données entière. Pour plus d’informations sur les conservations, voir [gérer des conservations dans Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).

Lorsque vous créez une conservation pour le contenu d’une équipe, vous pouvez choisir tous les emplacements que vous souhaitez inclure dans votre conservation. Même si les utilisateurs suppriment ou modifient du contenu, la conservation conserve les copies de toutes les versions précédentes de ce contenu.

Vous pouvez également utiliser une requête facultative pour définir des conditions pour la conservation en fonction de mots clés, d’une plage de dates, d’un auteur et de nombreux autres critères. Si vous ne spécifiez aucun mot-clé, tous les éléments de la source de données sont soumis à la conservation.

### <a name="advanced-ediscovery-searches"></a>Recherches avancées d’eDiscovery

Vous pouvez également effectuer une recherche dans le contenu d’équipes. Pour plus d’informations sur les recherches, voir [collecter des données pour un cas dans Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery). Une recherche renverra une conversation entière si un message correspond à la requête de recherche.

Lors de la création d’une requête de recherche, vous pouvez choisir des dépositaires de telle sorte que toutes les sources que vous avez déjà sélectionnées puissent effectuer une recherche. Vous pouvez également rechercher des sources non privatives de Troie telles que des sites d’équipe qui ne sont pas mappés à un utilisateur. Des requêtes facultatives sont également disponibles pour affiner votre recherche dans le contenu de l’équipe.

Une fois que vous avez créé une recherche et sélectionné celle-ci, une fenêtre s’affiche avec des informations supplémentaires et des actions que vous pouvez effectuer sur la recherche sélectionnée. Si vous cliquez sur le bouton **statistiques** , vous pouvez afficher les statistiques relatives à votre recherche, notamment les répartitions en fonction des types d’emplacements, de la source d’origine du contenu et de la présence du contenu dans une boîte aux lettres de groupe, dans la boîte aux lettres de l’utilisateur individuel ou sur un site SharePoint. Vous pouvez donc voir une répartition des sources qui participent à vos résultats de recherche. Le mode **requêtes** est également disponible pour vous permettre de voir les mots clés individuels qui participent aux résultats.

Après avoir finalisé votre recherche, vous pouvez cliquer sur le bouton **Ajouter des résultats pour réviser** , puis l’ajouter à un ensemble de révisions. Pour plus d’informations sur les ensembles de révisions, voir [gérer les ensembles de révision dans Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review sets](#review-sets-workflow) plus loin dans cet article.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Ensembles d’avis normaux et ensembles de avis de conversation

Lors de l’ajout d’une recherche à un ensemble d’avis, vous pouvez choisir parmi un ensemble d’avis standard ou un ensemble de avis de conversation.

Un ensemble d’avis normal est semblable à une exportation. Il fournit les `.msg` fichiers individuels pour le contenu d’équipes et affiche le contenu dans un affichage de base. En règle générale, vous devez utiliser une révision normale lorsque vous envisagez d’utiliser d’autres outils logiciels pour retraiter les fichiers ultérieurement.

Un ensemble de avis de conversation fournit une vue thématique et intuitive des conversations. il affiche conjointement les messages liés dans le bon ordre.

> [!div class="mx-imgBorder"]
> ![Capture d’écran du jeu de vérification de conversation](media/conversationOptions2.png)

Les fonctionnalités telles que la biffure sont disponibles dans les deux types de révisions. Pour plus d’informations sur les ensembles de révision, voir [revoir des conversations dans Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).

#### <a name="collection-options"></a>Options de collection

Lors de l’ajout d’un ensemble d’avis, plusieurs options sont disponibles en tant que cases à cocher dans la section **options de collection** de la fenêtre, y compris les options de **récupération de conversation** et les conversations d' **équipe**. Si vous activez ces options, tous les messages de teams individuels qui font partie de votre jeu de vérification seront également affichés avec des messages supplémentaires les entourant pour le contexte. Par exemple, si votre requête est spécifique et qu’un seul message est retourné par conséquent, l’activation de ces options renverra également plusieurs messages au début et à la suite du message correspondant à votre requête.

De nombreux critères logiques permettent de déterminer si des messages supplémentaires fournissent un contexte aux messages correspondant à votre requête. Par exemple, pour le contenu d’une équipe, l’activation de ces options récupère le message parent et tous les messages enfants en raison de la façon dont les messages sont thématiques.

Les horodatages du message sont également vérifiés. Si un message correspond à votre requête, les messages qui le précèdent au-dessus de 4 heures ou qui le suivent dans une plage de 4 heures sont considérés comme faisant partie de la conversation et sont également inclus dans les résultats.

Si vous devez être certain de savoir quels messages contextuels seront renvoyés en incluant des correspondances à votre requête de recherche, il est inutile d’utiliser ces options. Vous pouvez collecter tout le contenu ou bien augmenter la plage de dates de votre recherche afin que d’autres messages soient renvoyés comme résultat de votre requête.

### <a name="review-sets-workflow"></a>Révision-définir le flux de travail

Vous pouvez afficher les jeux de vérification existants ou en créer de nouveaux en cliquant sur l’onglet **révision** . Pour plus d’informations sur les ensembles de révision, voir [gérer les ensembles de révision dans Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).

En plus des documents, vous pouvez ajouter des messages électroniques, des équipes, des messages Yammer et d’autres contenus à votre ensemble d’avis. Dans un ensemble d’avis, vous pouvez également effectuer les opérations que vous pouvez effectuer dans d’autres contextes, telles que la recherche de contenu et la création de requêtes personnalisées. Ces opérations s’appliquent uniquement aux éléments qui ont été ajoutés à l’ensemble d’avis.

Le bouton **gérer les ensembles de révisions** fournit des options supplémentaires telles que l’analyse, le rapport de synthèse, le nombre de jeux de charges qui ont été ajoutés, etc.

Pour accéder aux visualisations et graphiques de vos données, cliquez sur le mode d’affichage profil de recherche de **résultats individuels** \> **Search profile view** dans le coin supérieur droit. Vous pouvez cliquer sur des pentaèdres dans ces graphiques pour sélectionner le type de contenu que vous souhaitez interroger. Par exemple, vous pouvez choisir d’interroger uniquement le contenu d’une équipe. Vous pouvez également enregistrer ces requêtes de la même manière que les requêtes que vous rédigez manuellement.

#### <a name="summary-view-text-view-and-annotate-view"></a>Affichage de synthèse, affichage texte et affichage annoter

Si vous cliquez sur une conversation de teams dans l’ensemble d’avis, elle affiche la **vue de synthèse**, qui permet d’afficher l’intégralité d’une conversation d’équipe dans la liste des messages avec lesquels vous pouvez interagir individuellement. Cliquez sur la flèche vers le bas à droite du message pour afficher un menu contextuel qui vous permet d’afficher les détails du message ou de télécharger le `.msg` fichier individuel. Cliquez sur Détails du message pour afficher le résumé des métadonnées ou les métadonnées complètes du message.

Pour télécharger un fichier PDF, cliquez sur le bouton Télécharger dans le coin supérieur droit de l’affichage de synthèse.

Cliquez sur l’onglet **affichage de texte** pour afficher une vue de texte brut du texte extrait de la conversation Teams. Ce contenu en texte brut est approprié pour l’exportation et vous pouvez l’utiliser facilement à l’aide d’autres outils logiciels.

Cliquez sur l’onglet du **mode annotation** pour accéder aux fonctionnalités d’annotation. Cet onglet affiche le contenu dans un format qui ressemble à une conversation d’équipe, mais il existe également d’autres options de modification. Vous pouvez utiliser un outil crayon pour prendre des notes, dessiner sur le message ou effectuer des rayures fines pour les fins de rédaction. Il existe également un outil de **biffure de zone** que vous pouvez utiliser pour dessiner un rectangle qui entoure le cadre de la zone et le marque comme ayant été rédigé.

Voici un exemple de fichier biffé pour la conversation thématique entre les utilisateurs.

> [!div class="mx-imgBorder"]
> ![Capture d’écran d’un fichier biffé](media/RedactedFileExample.png)

En bas de l’onglet **affichage d’annotation** figure le bouton **balise documents** qui affiche le panneau balisage. Dans ce panneau, vous pouvez appliquer un indicateur à tous les messages de la conversation Teams. Vous pouvez étiqueter une conversation comme réactif ou sans réponse, privilégié ou ne pas être privilégié, si elle contient des « éléments intéressants », si elle doit être incluse dans l’exportation et si elle a besoin d’une analyse approfondie. Vous pouvez également gérer et appliquer d’autres balises personnalisées.

#### <a name="action-menu"></a>Menu d’action

Dans la fenêtre réviser les jeux, vous pouvez exporter le contenu en cliquant sur exportation d' **action** \> **Export**. De nombreuses options sont disponibles lors de l’exportation.

Pour exporter un fichier qui contient toutes les métadonnées de tous les messages Teams, activez la case à cocher **charger le fichier** . Pour inclure dans votre fichier toutes les balises que vous avez appliquées au contenu, activez la case à cocher **balises** .

Utilisez l’option **fichiers natifs** pour exporter des fichiers au format natif. Vous pouvez choisir d’exporter une conversation sous la forme d’un fichier ou de tous les messages d’une conversation dans leurs propres fichiers.

L’option **fichiers texte** vous permet d’enregistrer les versions de texte brut. Pour plus d’informations sur la façon d’obtenir une vue de texte brut des conversations d’équipes dans l’ensemble de révisions, voir [vue récapitulative, vue de texte et mode annotation](#summary-view-text-view-and-annotate-view) au-dessus.

Si vous avez appliqué des Redactions au contenu, comme décrit dans la section synthèse de l’affichage de [synthèse, texte et annoter](#summary-view-text-view-and-annotate-view) ci-dessus, vous pouvez sélectionner l’option remplacer les formats **natifs avec des** fichiers PDF convertis pour remplacer les fichiers natifs contenant des copies converties au format PDF.

Vous pouvez choisir d’exporter vers un conteneur de stockage d’objets BLOB Azure fourni par Microsoft ou vous pouvez fournir votre propre conteneur de stockage BLOB Azure.

Lorsque vous êtes prêt à commencer le processus d’exportation, cliquez sur le bouton **Exporter** . Pour plus d’informations sur la façon d’accéder au conteneur de stockage BLOB Azure et de télécharger le contenu exporté une fois l’exportation terminée, voir [Télécharger des tâches d’exportation](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) .

> [!NOTE]
> L’exportation peut prendre un certain temps. Pour effectuer le suivi de l’état du processus d’exportation, quittez l’onglet **révision** , puis cliquez sur l’onglet **exportations** .

## <a name="related-topics"></a>Voir aussi

- [eDiscovery dans Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
