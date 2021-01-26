---
title: Effectuer une enquête de découverte électronique sur du contenu
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
description: Découvrez ce que vous devez faire lorsque vous devez effectuer une eDiscovery, par exemple, lorsque vous devez envoyer toutes les informations stockées électroniquement pour les procédures légales.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980458"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Mener une recherche eDiscovery de contenu dans Microsoft Teams

Les grandes entreprises sont souvent exposées à de importantes procédures légales de demande de soumission de toutes les informations stockées électroniquement (ESI). Le contenu de Microsoft Teams peut être recherché et utilisé pendant les enquêtes de découverte électronique.

## <a name="overview"></a>Vue d’ensemble

Toutes les conversations microsoft Teams 1:1 ou de groupe sont journalées dans les boîtes aux lettres des utilisateurs respectifs. Tous les messages de canal standard sont journalés dans la boîte aux lettres du groupe représentant l’équipe. Les fichiers téléchargés dans les canaux standard sont couverts par la fonctionnalité eDiscovery pour SharePoint Online et OneDrive Entreprise.

La découverte électronique des messages [](private-channels.md) et des fichiers dans des canaux privés fonctionne différemment que dans les canaux standard. Pour en savoir plus, [voir eDiscovery des canaux privés.](#ediscovery-of-private-channels)

Il n’est pas possible d’eDiscoverable tout le contenu de Teams. Le tableau suivant indique les types de contenu que vous pouvez rechercher à l’aide des outils de découverte électronique Microsoft :

| Type de contenu | eDiscoverable | Remarques |
|:--- | :--- |:--- |
|Enregistrements audio | Non | |
|Contenu de la carte|Oui|Pour [plus d’informations, voir](#search-for-card-content) Rechercher le contenu de la carte.|
|Liens de conversation | Oui | |
|Messages de conversation | Oui |Cela inclut le contenu dans les canaux Teams, les conversations 1:1, les conversations de groupe 1:N et les conversations avec les participants de l’utilisateur invité.  |
|Extraits de code | Non | |
|Messages modifiés | Oui | Si l’utilisateur est en attente, les versions précédentes des messages modifiés sont également conservées. |
|Emojis, GIF et autocollants | Oui | |
|Images en ligne | Oui | |
|Conversations de réunion par messagerie instantanée | Oui | |
|Métadonnées<sup>de réunion 1</sup> | Oui |  |
|Nom du canal | Non | |
|Messages de canal privé | Oui | |
|Devis | Oui | Le contenu cité peut faire l’l’objectif d’une recherche. Toutefois, les résultats de la recherche n’indiquent pas que le contenu a été cité. |
|Réactions (par exemple, j’aime, cœurs et autres réactions) | Non | |
|Objet | Oui | |
|Tableaux | Oui | |
|||

<sup>1 Métadonnées</sup> de réunion (et d’appel) inclut les informations suivantes :

- Heure de début et de fin et durée de la réunion
- Participer à une réunion et quitter des événements pour chaque participant
- VoIP join/calls
- Rejoindre une équipe anonyme
- Rejoindre un utilisateur fédéré
- Rejoindre un utilisateur invité

  L’image montre un exemple de métadonnées de réunion.

  > [!div class="mx-imgBorder"]
  > ![Image des métadonnées de réunion des enregistrements CVR.](media/conversationOption3.png)

Voici un exemple de conversation par messagerie instantanée entre des participants au cours de la réunion.

![Conversation entre les participants dans Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversation entre les participants dans les résultats de recherche eDiscovery.](media/MeetingImConversation2.png)

Pour plus d’informations sur la conduite d’une investigation eDiscovery, voir Commencer à travailler avec la découverte [électronique principale.](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)

Les données de Microsoft Teams s’afficheront en tant que messagerie instantanée ou conversations dans la sortie d’exportation d’Excel eDiscovery. Vous pouvez ouvrir le `.pst` fichier dans Outlook pour afficher ces messages après les avoir exportés.

Lorsque vous affichez le fichier .pst pour l’équipe, toutes les conversations sont conservées dans le dossier Conversation d’équipe sous Historique des conversations. Le titre du message contient le nom de l’équipe et le nom du canal. Par exemple, l’image ci-dessous montre un message d’Bob qui a envoyé un message au canal Project 7 standard de l’équipe Spécifications de fabrication.

![Capture d’écran d’un dossier conversation d’équipe dans la boîte aux lettres d’un utilisateur dans Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Les conversations privées dans la boîte aux lettres d’un utilisateur sont stockées dans le dossier Conversation d’équipe sous Historique des conversations.

## <a name="ediscovery-of-private-channels"></a>Découverte électronique de canaux privés

Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.

Chaque canal privé possède son propre site SharePoint distinct du site d’équipe parent, les fichiers d’un canal privé sont gérés indépendamment de l’équipe parente.

Teams ne prend pas en charge la recherche eDiscovery sur un seul canal au sein d’une équipe, aussi toute l’équipe doit-elle être recherché. Pour effectuer une recherche eDiscovery de contenu dans un canal privé, effectuez une recherche dans l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure les messages).

Pour identifier les fichiers et messages d’un canal privé à inclure dans votre recherche eDiscovery, utilisez les étapes suivantes.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Inclure des fichiers de canal privé dans une recherche eDiscovery

Avant d’effectuer ces étapes, installez [SharePoint Online Management Shell et connectez-vous à SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Exécutez la suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés de l’équipe.

    ```PowerShell
    Get-SPOSite
    ```

2. Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et à l’ID du groupe d’équipe parent.

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

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Inclure les messages de canal privé dans une recherche eDiscovery

Avant d’effectuer ces étapes, assurez-vous que vous avez installé la dernière version du [module Teams PowerShell.](teams-powershell-overview.md)

1. Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Exécutez la commande suivante pour obtenir la liste des membres d’un canal privé.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans votre requête de recherche [eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Rechercher du contenu pour les utilisateurs invités

Vous pouvez utiliser les outils eDiscovery pour rechercher du contenu Teams lié aux utilisateurs invités de votre organisation. Le contenu des discussions Teams associé à un utilisateur invité est conservé dans un emplacement de stockage cloud et peut être recherché à l’aide de la découverte électronique. Cela inclut la recherche de contenu dans les conversations de conversation 1:1 et 1:N dans lesquelles un utilisateur invité est participant avec d’autres utilisateurs de votre organisation. Vous pouvez également rechercher des messages de canal privé dans lesquels un utilisateur invité est participant et rechercher du contenu dans les conversations *invité:invité* où les seuls participants sont des utilisateurs invités.

Pour rechercher du contenu pour les utilisateurs invités :

1. Connectez-vous à Azure AD PowerShell. Pour obtenir des instructions, voir la section « Se connecter avec Azure Active Directory PowerShell » dans Se connecter à [Microsoft 365 avec PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Veillez à effectuer les étapes 1 et 2 de la rubrique précédente.

2. Une fois que vous êtes connecté à Azure AD PowerShell, exécutez la commande suivante pour afficher le nom d’utilisateur principal (UPN) de tous les utilisateurs invités de votre organisation. Vous devez utiliser le nom d’utilisateur utilisateur (UPN) de l’utilisateur invité lorsque vous créez la recherche à l’étape 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Au lieu d’afficher une liste de noms d’utilisateur principaux sur l’écran d’ordinateur, vous pouvez rediriger la sortie de la commande vers un fichier texte. Pour ce faire, vous pouvez l’appending `> filename.txt` à la commande précédente. Le fichier texte avec les noms d’utilisateur principaux est enregistré dans le dossier actuel.

3. Dans une autre fenêtre Windows PowerShell, connectez-vous au PowerShell du Centre de & sécurité et conformité. Pour obtenir des instructions, [voir Se connecter au Centre de & conformité PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Vous pouvez vous connecter avec ou sans utiliser l’authentification multifacteur.

4. Créez une recherche de contenu qui recherche tout le contenu (tels que les messages de conversation et les messages électroniques) dans lequel l’utilisateur invité spécifié était participant en exécutant la commande suivante.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Par exemple, pour rechercher le contenu associé à l’utilisateur invité Sara Monnais, vous devez exécuter la commande suivante.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Pour plus d’informations sur l’utilisation de PowerShell pour créer des recherches de contenu, voir [New-ComplianceSearch.](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

5. Exécutez la commande suivante pour lancer la recherche de contenu que vous avez créée à l’étape 4 :

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Allez [https://compliance.microsoft.com](https://compliance.microsoft.com) à, puis cliquez sur **Afficher toute la recherche** de  >  **contenu.**

7. Dans la liste des recherches, sélectionnez la recherche que vous avez créée à l’étape 4 pour afficher la page de survol.

8. Dans la page de survol, vous pouvez faire les choses suivantes :

   - Cliquez **sur Afficher les résultats** pour afficher les résultats de la recherche et afficher un aperçu du contenu.

   - À côté du **champ Requête,** cliquez sur **Modifier** pour modifier, puis réexécutez la recherche. Par exemple, vous pouvez ajouter une requête de recherche pour affiner les résultats.

   - Cliquez **sur Exporter les résultats** pour exporter et télécharger les résultats de recherche.

## <a name="search-for-card-content"></a>Rechercher le contenu d’une carte

Le contenu de la carte généré par les applications dans les canaux Teams, les conversations en tête-à-tête et les conversations 1xN sont stockés dans les boîtes aux lettres et peuvent faire l’effet d’une recherche. Une *carte est* un conteneur d’interface utilisateur pour de courts éléments de contenu. Les cartes peuvent avoir plusieurs propriétés et pièces jointes, et peuvent inclure des boutons qui peuvent déclencher des actions de carte. Pour plus d’informations, voir [Cartes](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Comme tout autre contenu de Teams, où le contenu de la carte est stocké est basé sur l’endroit où la carte a été utilisée. Le contenu des cartes utilisées dans un canal Teams est stocké dans la boîte aux lettres du groupe Teams. Le contenu des cartes pour les conversations 1:1 et 1xN est stocké dans les boîtes aux lettres des participants à la conversation.

Pour rechercher du contenu de carte, vous pouvez utiliser les `kind:microsoftteams` conditions ou les conditions de `itemclass:IPM.SkypeTeams.Message` recherche. Lors de la révision des résultats de la recherche, le contenu de la carte généré par des bots dans un canal Teams a la propriété de courrier **Expéditeur/Auteur** en tant que , où se trouve le nom de l’application qui a généré le contenu de la `<appname>@teams.microsoft.com` `appname` carte. Si le contenu de la carte a été généré par un utilisateur, la valeur **Expéditeur/Auteur** identifie l’utilisateur.

Lorsque vous affichez le contenu d’une carte dans les résultats de la recherche de contenu, celui-ci s’affiche en tant que pièce jointe du message. La pièce jointe s’appelle , à l’endroit où se trouve le nom de `appname.html` l’application qui a généré le contenu de la `appname` carte. Les captures d’écran suivantes montrent comment le contenu de la carte (pour une application nommée Asana) apparaît dans Teams et dans les résultats d’une recherche.

**Contenu de la carte dans Teams**

![Contenu de la carte dans le message du canal Teams](media/CardContentTeams.png)

**Contenu de la carte dans les résultats de la recherche**
  
![Même contenu de carte dans les résultats d’une recherche de contenu](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Pour afficher des images à partir du contenu de la carte dans les résultats de recherche à ce moment-là (par exemple, les cocher dans la capture d’écran précédente), vous devez être inscrit à Teams (dans un onglet différent au cours de la session de navigateur que vous utilisez pour afficher les résultats de la https://teams.microsoft.com) recherche. Dans le cas contraire, les espaces pour image s’affichent.

## <a name="advanced-ediscovery"></a>eDiscovery avancée

Certains contenus Microsoft Teams peuvent également être recherchés et conservés à l’aide du flux de [travail eDiscovery avancé.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) Bien qu’eDiscovery propose une gamme de fonctionnalités de recherche, de mise en attente et d’exportation, advanced eDiscovery offre aux administrateurs de conformité d’autres outils pour identifier les sources de données et analyser leur contenu.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Flux de travail de flux de travail de découverte électronique avancée pour le contenu de Teams

Les tuteurs peuvent être membres de diverses équipes. Vous pouvez capturer le contenu de Teams qui est pertinent pour ces administrateurs. Pour obtenir des instructions sur le flux de travail de flux de travail de flux de travail, voir Ajouter des administrateurs à un cas de découverte [électronique avancée.](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)

Après avoir ajouté un groupe de travail, cliquez sur **le bouton** Suivant, puis sur **le bouton** Ajouter. Une fenêtre s’affiche pour vous inviter à sélectionner d’autres emplacements, ce qui vous indique tous les membres de l’organisation et les emplacements de site SharePoint correspondants pour leurs données. Dans toutes ces équipes et sources de données, vous pouvez choisir le contenu que vous voulez utiliser pour la découverte électronique, puis mettre cet utilisateur et toutes les sources de données que vous avez identifiées en attente.

Vous pouvez choisir d’inclure le contenu Exchange, le contenu OneDrive ou les deux. Le contenu Exchange inclut tout le contenu de l’application dans les boîtes aux lettres de l’utilisateur, tel que son courrier électronique, le contenu de Teams stocké dans sa boîte aux lettres, etc. Le contenu de OneDrive inclut non seulement le contenu de l’utilisateur, mais également tout le contenu de Teams stocké dans OneDrive, tel que les conversations 1:1, les conversations 1:N et les fichiers partagés dans les conversations.

Vous avez également la possibilité d’associer toute équipe dont l’administrateur est membre, de sorte que les messages de conversation de canal et les fichiers à qui le groupe a accès soient inclus. En outre, toute autre équipe peut être associée à un groupe de travail.

> [!NOTE]
> La découverte électronique des messages [](private-channels.md) et des fichiers dans des canaux privés fonctionne différemment que dans les canaux standard. Pour en savoir plus, [voir eDiscovery des canaux privés.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Mise en attente d’une source de données

S’il n’existe aucun utilisateur spécifique à désigner comme tuteur, vous pouvez mettre en attente une source de données entière. Pour plus d’informations sur les conserves, voir Gérer les [cours dans Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)

Lors de la création d’une attente pour le contenu de Teams, vous pouvez choisir tous les emplacements que vous souhaitez inclure dans votre attente. Même si des utilisateurs sont en train de supprimer ou de modifier du contenu, la attente conserve des copies de toutes les versions précédentes de ce contenu.

Vous pouvez également utiliser une requête facultative pour définir les conditions de la mise en attente en fonction de mots clés, plage de dates, auteur et de nombreux autres critères. Si vous ne spécifiez aucun mot clé, tous les données de cette source de données seront soumis à la attente.

### <a name="advanced-ediscovery-searches"></a>Recherches eDiscovery avancées

Il est également possible d’effectuer une recherche dans le contenu de Teams. Pour plus d’informations sur les recherches, voir Collecter des données pour [un cas dans Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery) Une recherche retourne une conversation entière si un seul message correspond à la requête de recherche.

Lorsque vous créez une requête de recherche, vous pouvez choisir les administrateurs de sorte que toutes les sources que vous avez déjà sélectionnées soient recherchés. Vous pouvez également rechercher des sources non inexistantes, telles qu’un site Teams qui n’est pas mappé à un utilisateur. Des requêtes facultatives sont également disponibles pour affiner votre recherche dans le contenu de Teams.

Une fois que vous avez créé et sélectionné une recherche, une fenêtre affiche des détails et actions supplémentaires que vous pouvez effectuer sur la recherche sélectionnée. Si vous  cliquez sur le bouton Statistiques, vous pouvez afficher les statistiques relatives à votre recherche, notamment les répartitions en fonction des types d’emplacements, la source d’origine du contenu et si le contenu est situé dans une boîte aux lettres de groupe, dans la boîte aux lettres utilisateur individuelle ou sur un site SharePoint. Par conséquent, vous pouvez voir une répartition des sources qui contribuent à vos résultats de recherche. Un affichage **Requêtes** est également disponible pour vous aider à voir les mots clés individuels qui contribuent à vos résultats.

Après avoir finaliser votre recherche, vous pouvez cliquer sur le bouton Ajouter des résultats pour réviser le jeu et l’ajouter à un jeu de révisions.  Pour plus d’informations sur les ensembles de révision, voir Gérer les jeux de révisions dans le flux de travail Ensembles de révisions et [Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) [plus](#review-sets-workflow) loin dans cet article.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Jeux de révisions et jeux de révisions de conversations normaux

Lors de l’ajout d’une recherche à un ensemble de révisions, vous avez le choix entre un jeu de révisions normal ou un jeu de révisions de conversation.

Un ensemble de révisions normal est semblable à une exportation . Il fournit les fichiers individuels pour le contenu de Teams et le `.msg` présente dans une vue de base. En règle générale, vous utilisez un ensemble de révisions normal lorsque vous envisagez d’utiliser d’autres outils logiciels pour rétraiter les fichiers ultérieurement.

Un ensemble de révisions de conversations offre un affichage plus intuitif et à thread des conversations. affiche les messages connexes dans l’ordre approprié.

> [!div class="mx-imgBorder"]
> ![Capture d’écran du jeu de révisions de conversation](media/conversationOptions2.png)

Des fonctionnalités telles que la redaction sont disponibles dans les deux types de jeux de révisions. Pour plus d’informations sur les ensembles de révision, voir [Passer en revue les conversations dans la découverte électronique avancée.](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Options de collection

Lors de l’ajout à un jeu de révisions, plusieurs options sont  disponibles sous la section **Options** de collection de la fenêtre, y compris Options de récupération des conversations et **Conversations Teams.** Si vous activez ces options, tous les messages Teams individuels faisant partie de votre jeu de révisions seront également affichés avec des messages supplémentaires autour d’eux pour leur contexte. Par exemple, si votre requête est spécifique et qu’un seul message est renvoyé par conséquent, l’activation de ces options retournera également plusieurs messages qui surviennent et suivent le message qui correspond à votre requête.

De nombreux critères logiques permettent de déterminer si d’autres messages fournissent du contexte aux messages qui correspondent à votre requête. Par exemple, pour le contenu de Teams, l’activation de ces options permet de récupérer le message parent et tous les messages enfants en raison de la façon dont les messages sont threadés.

L’horodament des messages est également coché. Si un message correspond à votre requête, les messages voisins qui le précèdent sur une période de 4 heures ou qui le suivent sur une période de 4 heures sont considérés comme faisant partie de la conversation et sont également inclus dans les résultats.

Si vous devez être certain des messages contextuels qui seront renvoyés avec des correspondances à votre requête de recherche, vous n’avez pas besoin d’utiliser ces options. Vous pouvez collecter tout le contenu ou élargir la plage de dates de votre recherche afin de faire en sorte que davantage de messages soient renvoyés à la suite de votre requête.

### <a name="review-sets-workflow"></a>Passer en revue les ensembles de flux de travail

Vous pouvez afficher les ensembles de révision existants ou en créer de nouveaux en cliquant sur l’onglet **Ensembles de** révisions. Pour plus d’informations sur les ensembles de révision, voir Gérer les jeux [de révisions dans Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)

En plus des documents, vous pouvez ajouter des e-mails, des messages Teams, des Yammer et d’autres contenus à votre jeu de révisions. Dans un ensemble de révisions, vous pouvez également effectuer bon nombre des opérations que vous pouvez effectuer dans d’autres contextes, tels que la recherche de contenu et la création de requêtes personnalisées. Ces opérations s’appliquent uniquement aux éléments qui ont été ajoutés au jeu de révisions.

Le **bouton Gérer les jeux** de révision fournit des options supplémentaires, telles que l’analyse, les rapports de synthèse, le nombre de jeux de chargements ajoutés, etc.

Pour accéder aux visualisations et graphiques de vos données, cliquez sur **Vue** de profil de recherche de résultats \>  individuels dans le coin supérieur droit. Vous pouvez cliquer sur des coins dans ces graphiques pour sélectionner de manière interactive le type de contenu à interroger. Par exemple, vous pouvez choisir d’interroger uniquement le contenu de Teams. Vous pouvez également enregistrer ces requêtes tout comme vous le feriez pour les requêtes que vous écrivez manuellement.

#### <a name="summary-view-text-view-and-annotate-view"></a>Vue de synthèse, vue de texte et affichage d’annoter

Si vous cliquez sur une conversation Teams dans le jeu de révisions, elle affiche la vue de **synthèse,** qui affiche une conversation Teams entière sous la la mesure des messages avec lesquels vous pouvez interagir individuellement. Cliquez sur la flèche vers le bas à droite d’un message pour afficher un menu contextur qui vous permet d’afficher les détails du message ou de télécharger le fichier `.msg` individuel. Cliquez sur les détails du message pour afficher un résumé des métadonnées ou des métadonnées complètes du message.

Pour télécharger un fichier PDF, cliquez sur le bouton de téléchargement dans le coin supérieur droit de l’affichage de résumé.

Cliquez sur **l’onglet Affichage** de texte pour afficher une vue en texte intégral du texte extrait de la conversation Teams. Ce contenu en texte simple convient à l’exportation et vous pouvez l’utiliser facilement à l’aide d’autres outils logiciels.

Cliquez sur **l’onglet Affichage d’annotation** pour accéder aux fonctionnalités d’annotation. Cet onglet affiche le contenu dans un format qui ressemble à une conversation Teams, mais il existe également des options supplémentaires pour la modification. Vous pouvez utiliser un crayon pour prendre des notes, dessiner sur un message ou recommencer à zéro à des fins d’redaction. Vous pouvez également utiliser un outil de **redaction** de zone pour dessiner un rectangle qui noircit la zone et la marque comme « Rouge ».

Voici un exemple de fichier rouge pour une conversation à thread entre des utilisateurs.

> [!div class="mx-imgBorder"]
> ![Capture d’écran d’un fichier redessé](media/RedactedFileExample.png)

En bas de l’onglet Affichage **d’annoter** se trouve le bouton **Baliser des documents,** qui affiche le panneau de marquage. Dans ce panneau, vous pouvez appliquer une balise à tous les messages au sein de la conversation Teams. Vous pouvez étiqueter une conversation comme réactive ou non réactive, privilégié ou non privilégié, qu’elle contient des « éléments intéressants », qu’elle doit être incluse dans l’exportation et qu’elle doit être approfondi. Vous pouvez également gérer et appliquer d’autres balises personnalisables.

#### <a name="action-menu"></a>Menu Action

Dans la fenêtre des jeux de révision, vous pouvez exporter le contenu en cliquant sur **Action** \> **Export.** De nombreuses options sont disponibles lors de l’exportation.

Pour exporter un fichier qui contient toutes les métadonnées de tous les messages Teams, cochez la case Charger **le** fichier. Pour inclure dans votre fichier les balises que vous  avez appliquées au contenu, cochez la case Balises.

Utilisez **l’option Fichiers natifs** pour exporter des fichiers dans leur format natif. Vous pouvez choisir d’exporter une conversation comme un seul fichier ou tous les messages de conversation individuels dans leurs propres fichiers distincts.

**L’option Fichiers texte** vous permet d’enregistrer des versions de contenu en texte texte intégral. Pour plus d’informations sur l’obtention d’un affichage en texte intégral des conversations Teams dans le jeu de révisions, consultez l’affichage Résumé, l’affichage texte et [l’affichage d’annoter](#summary-view-text-view-and-annotate-view) ci-dessus.

Si vous avez appliqué des redactions au contenu comme décrit dans la section Résumé, Texte et [Annoter](#summary-view-text-view-and-annotate-view) ci-dessus, vous pouvez sélectionner l’option Remplacer les **redéplacats natifs** par les fichiers PDF convertis pour remplacer les fichiers natifs par des copies converties au format PDF.

Vous pouvez choisir d’exporter vers un conteneur de stockage d’objets blob Azure fourni par Microsoft ou vous pouvez fournir votre propre conteneur de stockage Blob Azure.

Lorsque vous êtes prêt à commencer le processus d’exportation, cliquez sur **le bouton** Exporter. Pour [plus d’informations](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) sur la façon d’accéder au conteneur de stockage blob Azure et de télécharger votre contenu exporté une fois l’exportation terminée, voir Télécharger les tâches d’exportation.

> [!NOTE]
> L’exportation peut prendre une période prolongée. Pour suivre l’état du processus d’exportation, quittez l’onglet **Ensembles** de révision, puis cliquez sur **l’onglet** Exportations.

## <a name="related-topics"></a>Voir aussi

- [eDiscovery dans Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
