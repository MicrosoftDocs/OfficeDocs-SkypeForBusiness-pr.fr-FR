---
title: Effectuer une enquête eDiscovery sur du contenu
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
ms.openlocfilehash: 85124047c5bb894eb4eb4177fad0e0cfee53dfc3
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711768"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Mener une recherche eDiscovery de contenu dans Microsoft Teams

Les grandes entreprises sont souvent exposées à de hautes procédures juridiques qui demandent l’envoi de toutes les informations stockées électroniquement (ESI). Microsoft Teams de contenu peut être recherché et utilisé pendant les enquêtes de découverte électronique.

## <a name="overview"></a>Présentation

Toutes Microsoft Teams conversations en tête-à-tête ou de groupe sont journalées dans les boîtes aux lettres des utilisateurs respectifs. Tous les messages de canal standard sont journalés dans la boîte aux lettres du groupe représentant l’équipe. Les fichiers téléchargés dans les canaux standard sont couverts par la fonctionnalité eDiscovery pour SharePoint Online et OneDrive Entreprise.

La découverte électronique des messages et des fichiers dans des [](private-channels.md) canaux privés fonctionne différemment que dans les canaux standard. Pour en savoir plus, [voir eDiscovery des canaux privés](#ediscovery-of-private-and-shared-channels).

Il n’est Teams contenu eDiscoverable. Le tableau suivant indique les types de contenu que vous pouvez rechercher à l’aide des outils de découverte électronique Microsoft :

| Type de contenu | eDiscoverable | Remarques |
|:--- | :--- |:--- |
|Enregistrements audio | Non | |
|Contenu de la carte|Oui|Pour [plus d’informations, voir](#search-for-card-content) Rechercher le contenu d’une carte.|
|Liens de conversation | Oui | |
|Messages de conversation | Oui |Cela inclut le contenu des canaux Teams, des conversations en tête-à-tête, des conversations de groupe 1:N et des conversations avec des participants invités.  |
|Extraits de code | Non | |
|Messages modifiés | Oui | Si l’utilisateur est en attente, les versions précédentes des messages modifiés sont également conservées. |
|Emojis, GIF et autocollants | Oui | |
|Notifications de flux | Non | |
|Images en ligne | Oui | |
|Composants de boucle| Oui|Le contenu d’un composant de boucle est enregistré dans un fichier .fluid stocké dans le compte OneDrive Entreprise de l’utilisateur qui envoie le composant de boucle. Cela signifie que vous devez inclure OneDrive comme source de données lors de la recherche de contenu dans des composants de boucle. |
|Conversations de réunion par messagerie instantanée | Oui | |
|Métadonnées de <sup>réunion1</sup> | Oui |  |
|Nom du canal | Oui | |
|Messages de conversation de canal privé et partagé | Oui | |
|Devis | Oui | Le contenu cité peut faire l’l’objectif d’une recherche. Toutefois, les résultats de la recherche n’indiquent pas que le contenu a été cité. |
|Réactions (par exemple, likes, cœurs et autres réactions) | Non | |
|Objet | Oui | |
|Tableaux | Oui | |
||||

<sup>1 Métadonnées</sup> de réunion (et d’appel) inclut les informations suivantes :

- Heure de début et de fin et durée de la réunion
- Participer à une réunion et quitter des événements pour chaque participant
- VoIP joins/calls
- Jointeurs anonymes
- Jointeurs utilisateur fédérés
- Guest user joins

Voici un exemple de conversation entre des participants au cours d’une réunion.

![Conversation entre les participants dans Teams.](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

Voici un exemple de copie de conformité d’une même conversation vue dans un outil eDiscovery.

![Conversation entre les participants dans les résultats de recherche eDiscovery.](media/MeetingImConversation2.png)

Voici un exemple des métadonnées de la réunion.

  > [!div class="mx-imgBorder"]
  > ![Métadonnées de la réunion à partir de la copie de conformité.](media/conversationOption3.png)

Pour plus d’informations sur la conduite d’une investigation eDiscovery, voir Commencer [avec la découverte électronique principale](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams données s’affichent sous la la mesure d’une messagerie instantanée ou de conversations dans le Excel d’exportation eDiscovery. Vous pouvez ouvrir le fichier `.pst` dans Outlook pour afficher ces messages après les avoir exportés.

Lorsque vous affichez le fichier .pst pour l’équipe, toutes les conversations sont situées dans le dossier Conversation d’équipe sous Historique des conversations. Le titre du message contient le nom de l’équipe et le nom du canal. Par exemple, l’image ci-dessous montre un message d’Bob qui a envoyé un message au Project 7 standard de l’équipe Spécifications de fabrication.

![Capture d’écran d’un dossier Conversation d’équipe dans la boîte aux lettres d’un Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Les conversations privées dans la boîte aux lettres d’un utilisateur sont stockées dans le dossier Conversation d’équipe sous Historique des conversations.

## <a name="ediscovery-of-private-and-shared-channels"></a>Découverte électronique de canaux privés et partagés

Les copies de conformité des messages dans les canaux privés et partagés sont envoyées à différentes boîtes aux lettres selon le type de canal. Cela signifie que vous devez effectuer des recherches dans différents emplacements de boîte aux lettres en fonction du type de canal dont un utilisateur est membre.

- **Canaux privés**. Des copies de conformité sont envoyées à la boîte aux lettres de tous les membres des membres du canal privé. Cela signifie que vous devez effectuer une recherche dans la boîte aux lettres de l’utilisateur lors de la recherche de contenu dans les messages de canal privé.

- **Canaux partagés**. Les copies de conformité sont envoyées à une boîte aux lettres système associée à l’équipe parente. Étant donné que Teams ne prend pas en charge la recherche eDiscovery d’une boîte aux lettres système unique pour un canal partagé, vous devez rechercher dans la boîte aux lettres l’équipe parent (en sélectionnant le nom de la boîte aux lettres d’équipe) lors de la recherche de contenu de message dans des canaux partagés.

Chaque canal privé et partagé a son propre site SharePoint distinct du site d’équipe parent. Cela signifie que les fichiers dans les canaux privés et partagés sont stockés sur son propre site et gérés indépendamment de l’équipe parente. Cela signifie que vous devez identifier et rechercher le site spécifique associé à un canal lors de la recherche de contenu dans des fichiers et des pièces jointes de message de canal.

Utilisez les sections suivantes pour identifier le canal privé ou partagé à inclure dans votre recherche eDiscovery.

### <a name="identifying-the-members-of-a-private-channel"></a>Identification des membres d’un canal privé

Utilisez la procédure de cette section pour identifier les membres d’un canal privé et utiliser les outils eDiscovery pour rechercher du contenu dans les messages de canal privés dans la boîte aux lettres du membre.

Avant d’effectuer ces étapes, assurez-vous que vous avez installé la [dernière version Teams module PowerShell](teams-powershell-overview.md).

1. Exécutez la commande suivante pour obtenir l’ID de groupe de l’équipe qui contient les canaux partagés dans la recherche.

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > Exécutez **la cmdlet Get-Team** sans aucun paramètre pour afficher la liste des Teams dans votre organisation. La liste contient l’ID de groupe et le nom DisplayName de chaque équipe.

2. Exécutez la commande suivante pour obtenir la liste des canaux privés dans l’équipe parente. Utilisez l’ID de groupe pour l’équipe obtenue à l’étape 1.

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. Exécutez la commande suivante pour obtenir la liste des propriétaires et membres d’un canal privé spécifique.

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. Incluez les boîtes aux lettres des propriétaires et membres d’un canal privé dans votre requête de recherche [eDiscovery dans la](/microsoft-365/compliance/search-for-content-in-core-ediscovery) découverte électronique principale ou lors de l’identification et de la collecte de contenu continu dans [Advanced eDiscovery](/microsoft-365/compliance/add-custodians-to-case).

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>Identification du site SharePoint pour les canaux privés et partagés

Comme expliqué précédemment, les fichiers partagés dans les canaux privés et partagés (et les fichiers joints aux messages du canal) sont stockés dans la collection de sites associée au canal. Utilisez la procédure de cette section pour identifier l’URL du site associé à un canal privé ou partagé spécifique. Vous pouvez ensuite utiliser les outils eDiscovery pour rechercher du contenu dans le site.

Avant d’effectuer ces étapes, [installez SharePoint Online Management Shell et connectez-vous à SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Vous pouvez également exécuter l’option suivante pour obtenir la liste de toutes SharePoint collections de sites associées aux canaux partagés dans l’équipe parente.

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > La convention d’appellation de l’URL d’un site associé aux canaux privés et partagés est la suivante `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`. Par exemple, l’URL du canal partagé nommée « Collaboration partenaire », qui se trouve dans l’équipe parente « Engineer Team » de l’organisation Contoso est `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`.

2. Exécutez les commandes PowerShell suivantes pour afficher l’URL de tous SharePoint sites associés aux canaux privés et partagés dans votre organisation. La sortie du script inclut également l’ID de groupe de l’équipe parente, que vous devez exécuter pour exécuter les commandes à l’étape 3.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > SharePoint sites pour les canaux privés créés avant le 28 juin 2021 `"TEAMCHANNEL#0"` utilisent la valeur de l’ID de modèle personnalisé. Pour afficher les canaux privés créés après cette date, utilisez la valeur `"TEAMCHANNEL#1"` lors de l’exécution des deux scripts précédents. Les canaux partagés utilisent uniquement la valeur de `"TEAMCHANNEL#1"`.

3. Pour chaque équipe parent, exécutez les commandes PowerShell suivantes pour identifier les sites de canal privé et partagé, `$groupID` où se trouve l’ID de groupe de l’équipe parent.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. [Incluez](/microsoft-365/compliance/add-custodians-to-case) le site associé à un canal privé ou partagé dans votre requête de recherche [eDiscovery dans core eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) ou lors de l’identification et de la collecte de contenu inapproprié dans Advanced eDiscovery.

## <a name="search-for-content-for-guest-users"></a>Rechercher du contenu pour les utilisateurs invités

Vous pouvez utiliser les outils eDiscovery pour rechercher du contenu Teams associé aux utilisateurs invités de votre organisation. Teams contenu de conversation associé à un utilisateur invité est conservé dans un emplacement de stockage cloud et peut être recherché à l’aide de la découverte électronique. Cela inclut la recherche de contenu dans les conversations de conversation 1:1 et 1:N dans lesquelles un utilisateur invité est participant avec d’autres utilisateurs de votre organisation. Vous pouvez également rechercher des messages de canal privé dans lesquels un utilisateur invité est participant et rechercher du contenu dans les conversations invité *:* invité où seuls les participants sont des utilisateurs invités.

Pour rechercher du contenu pour les utilisateurs invités :

1. Connecter à Azure AD PowerShell. Pour obtenir des instructions, voir la section Connecter « PowerShell Azure Active Directory » dans Connecter [à Microsoft 365 PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Veillez à effectuer les étapes 1 et 2 de la rubrique précédente.

2. Une fois connecté à Azure AD PowerShell, exécutez la commande suivante pour afficher le nom d’utilisateur principal (UPN) de tous les utilisateurs invités de votre organisation. Vous devez utiliser le nom d’utilisateur utilisateur (UPN) de l’utilisateur invité lorsque vous créez la recherche à l’étape 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Au lieu d’afficher une liste de noms d’utilisateur principaux sur l’écran d’ordinateur, vous pouvez rediriger la sortie de la commande vers un fichier texte. Pour ce faire, vous pouvez l’appending `> filename.txt` à la commande précédente. Le fichier texte avec les noms d’utilisateur principaux sera enregistré dans le dossier actuel.

3. Dans une autre fenêtre Windows PowerShell, connectez-vous au PowerShell du Centre de & sécurité et conformité. Pour obtenir des instructions à ce [Connecter powerShell du Centre de conformité & sécurité](/powershell/exchange/connect-to-scc-powershell). Vous pouvez vous connecter avec ou sans utiliser l’authentification multifacteur.

4. Créez une recherche de contenu qui recherche tout le contenu (tels que les messages de conversation et les messages électroniques) dans lequel l’utilisateur invité spécifié était participant en exécutant la commande suivante.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Par exemple, pour rechercher le contenu associé à l’utilisateur invité Sara Monnais, vous devez exécuter la commande suivante.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Pour plus d’informations sur l’utilisation de PowerShell pour créer des recherches de contenu, voir [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Exécutez la commande suivante pour lancer la recherche de contenu que vous avez créée à l’étape 4 :

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Allez à [https://compliance.microsoft.com](https://compliance.microsoft.com), puis cliquez **sur Afficher la** >  **recherche allContent**.

7. Dans la liste des recherches, sélectionnez la recherche que vous avez créée à l’étape 4 pour afficher la page de survol.

8. Dans la page de survol, vous pouvez faire les choses suivantes :

   - Cliquez **sur Afficher les résultats** pour afficher les résultats de la recherche et afficher un aperçu du contenu.

   - À côté du **champ Requête** , cliquez sur **Modifier** pour modifier, puis réexécutez la recherche. Par exemple, vous pouvez ajouter une requête de recherche pour affiner les résultats.

   - Cliquez **sur Exporter les résultats** pour exporter et télécharger les résultats de recherche.

## <a name="search-for-card-content"></a>Rechercher le contenu d’une carte

Le contenu de la carte généré par les applications Teams, les conversations en deux ou deux, et les conversations 1xN sont stockés dans des boîtes aux lettres et peuvent faire l’effet d’une recherche. Une *carte est* un conteneur d’interface utilisateur pour de courts éléments de contenu. Les cartes peuvent avoir plusieurs propriétés et pièces jointes, et peuvent inclure des boutons qui peuvent déclencher des actions de carte. Pour plus d’informations, voir [Cartes](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Comme les autres Teams, l’endroit où le contenu de la carte est stocké est basé sur l’endroit où la carte a été utilisée. Le contenu des cartes utilisées dans un Teams est stocké dans la boîte aux lettres Teams groupe. Le contenu des cartes pour les conversations 1:1 et 1xN est stocké dans les boîtes aux lettres des participants à la conversation.

Pour rechercher du contenu de carte, vous pouvez utiliser les conditions `kind:microsoftteams` ou `itemclass:IPM.SkypeTeams.Message` les conditions de recherche. Lors de l’examen des résultats de la recherche, le contenu de la carte généré par des bots dans un canal Teams a la propriété de courrier Expéditeur **/** `<appname>@teams.microsoft.com``appname` Auteur, comme , où se trouve le nom de l’application qui a généré le contenu de la carte. Si le contenu de la carte a été généré par un utilisateur, la valeur **Expéditeur/Auteur** identifie l’utilisateur.

Lorsque vous affichez le contenu d’une carte dans les résultats de la recherche de contenu, celui-ci s’affiche en tant que pièce jointe du message. La pièce jointe s’appelle `appname.html`, à `appname` l’endroit où se trouve le nom de l’application qui a généré le contenu de la carte. Les captures d’écran suivantes montrent comment le contenu de la carte (pour une application nommée Asana) apparaît dans Teams dans les résultats d’une recherche.

### <a name="card-content-in-teams"></a>Contenu de la carte dans Teams

![Contenu de la carte Teams message de canal.](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>Contenu de la carte dans les résultats de recherche
  
![Même contenu de carte dans les résultats d’une recherche de contenu.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Pour afficher des images à partir du contenu de la carte dans les résultats de recherche à ce moment-là (par exemple, les cocher dans la capture d’écran précédente), vous devez être inscrit à Teams (https://teams.microsoft.com)dans un autre onglet au cours de la session de navigateur que vous utilisez pour afficher les résultats de la recherche. Dans le cas contraire, les espaces pour images s’affichent.

## <a name="related-topics"></a>Rubriques connexes

- [Microsoft 365 solutions eDiscovery](/microsoft-365/compliance/ediscovery)
- [Commencer à travailler avec core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams flux de travail dans Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
